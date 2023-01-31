# Week 2 Lab Report

## Part 1- Creating a web server(StringServer)


To create a web server called "StringServer" we will use two files-
- Server.java
- StringServer.java

The code for StringServer.java is given below
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    String str = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            if (str.isEmpty()){
                return "String is empty.No message added yet.";
            }
            else{
                return str;
            }
        }
        if (url.getPath().contains("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
                str+=parameters[1]+"\n";
                return str;
            }
        }
        return "404 Not Found!";
    }
}


class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```


- This code keeps track of a single string that gets added to by the incoming requests and then concatenates a new line (\n) after the string and stores all the strings added so far.
- To run this code we wil use the commands
- `javac Server.java StringServer.java`
- `java StringServer 4000`
- After compiling and running the code we will be shown the following message-
       `Server Started! Visit http://localhost:4000 to visit.`
- In your browser, visit "http://localhost:4000". The page displayed should look like this


![13397028-3711-4719-B32C-08C6941E5431](https://user-images.githubusercontent.com/122580828/215579612-2a8d3c8c-65ce-4715-b0b7-865d76882e0d.jpeg)

- This message was displayed because handleRequest method was called. It checks the first if condition which then checks the nested if condition to check if the string str is empty or not. Since the string str was empty `String is empty.No message added yet.` was displayed.

- Now we will use the query "/add-message" to see how the server responds to it.



![3D5F4CBA-2225-48E6-85FE-DB72D78F15F0](https://user-images.githubusercontent.com/122580828/215591939-aa6e9fba-c74c-4d87-89a7-d9a0817cb844.jpeg)
![9FC324E3-4153-4CE8-8595-E6856D7B8DFE](https://user-images.githubusercontent.com/122580828/215591942-a2c3b245-e185-418a-8a4e-7ae6e8bbb346.jpeg)
![A8844D2E-72B7-4E84-9BE7-7FC4C58737A5](https://user-images.githubusercontent.com/122580828/215591943-434f9f2e-6acb-45c9-8f4c-5c597135cb70.jpeg)

- We can observe in the first image that when we succeed the url with "/add-message?s=Hello", the server displays hello.
- This happens because, when we type the above url it calls handleRequest method with the url as the parameter. It goes throught the if condition which checks if the url contains "/add-message". If the condition is true, it creates a string array parameters which is made by splitting the string with regex "=". It then checks if the first element of the array is "s". If the condition is true it concatenates the string to variable str(which in this case was "") and returns the string. If any of the conditions are false then it will display "404 Not Found".
- Next, when we add "Hi", it displays Hello and Hi both but in different lines.
- This is because when we added "Hello" to str it also added a new line such that the next time we add "Hi" it is displayed in the next line.
- The code works in a similar way when the url is succeeded by "/add-message?s=I am Suhani".




## Part 2- Bugs

For this part I chose the file **"ArrayExamples.java"**
```
public class ArrayExamples {

  
  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }

  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }

  // Averages the numbers in the array (takes the mean), but leaves out the
  // lowest number when calculating. Returns 0 if there are no elements or just
  // 1 element in the array
  static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
      if(num != lowest) { sum += num; }
    }
    return sum / (arr.length - 1);
  }


}
```

The tests for this file were-
```
import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
	@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}


  @Test
  public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }


  @Test
  public void testMyReverseInPlace(){
    int[] input1= { 10, 11, 12};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{12,11,10},input1);
  }
}
```
- The last test had a failure-inducing input because it didn't pass the test.
- We will look at the ReverseInPlace method and the bugs in it.
- In testMyReverseInPlace, the list entered is {10,11,12) which should have the output {12,11,10} when reversed but instead it displays 12 at index[2] instead of 10.
- This might be because this bug copies the first half of the list to the second half instead of exchanging them.

Symptom-

![D1322C88-0693-41AB-8A79-E497A63CF0F0](https://user-images.githubusercontent.com/122580828/215614937-506c7a6a-58ee-4cf5-ac8b-d089138ef811.jpeg)

- We can also see an input that doesn't result in a failure even if the code is wrong. This input has a list with only one element and hence it wouldn't matter whether the first half and second half are being exchanged or not.

Symptom-

![1B08744A-7725-421E-9666-EC4E04E92846](https://user-images.githubusercontent.com/122580828/215615620-fcd5032d-4327-4ccb-9717-aa8161b6b318.jpeg)

To fix this bug we need to change the method a bit

```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; i += 1) {
      int temp=arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length-i-1]=temp;
    }
  }
```
The following changes were made to fix the bugs-
1. We changed the range of i from `i<arr.length` to `i<arr.length/2`.
2. We created a new temporary variable "temp" by adding `int temp=arr[i];`.
3. We added the line `arr[arr.length-i-1]=temp;` so that we can assign elements to two indexes in the array in one iteration.
Here we store the first half in a temporary variable and copy the second half to the first half simultaneously and then copy the temporary variable to the second half of the list.

Making these changes will fix the bugs and all the tests will pass.

![AF80943C-C0C9-411F-8851-C9044C3E16C5](https://user-images.githubusercontent.com/122580828/215619560-34131fb1-f735-49eb-a434-2b89e3705d4a.jpeg)



## Part 3- What I Learnt

In week 2, I learnt something new which was how to create my own server and running it using a url. Learning about ports(specific port that the web server runs on) and local host(the computer we are on) which are parts of the url was really intriguing to me.
It was fascinating, when we connected our computers to the remote computer and we could see each other's changes(made to everyone's own seperate servers) on our own computers.

In week 3, we were introduced to bugs. Even though I was familiar with what bugs are, it was interesting to know how some inputs do not result in a failure even when there are bugs in the program while some inputs do.
