# Week1 Lab Report
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


- Now we will use the query "/add-message" to see how the server responds to it.



![3D5F4CBA-2225-48E6-85FE-DB72D78F15F0](https://user-images.githubusercontent.com/122580828/215591939-aa6e9fba-c74c-4d87-89a7-d9a0817cb844.jpeg)
![9FC324E3-4153-4CE8-8595-E6856D7B8DFE](https://user-images.githubusercontent.com/122580828/215591942-a2c3b245-e185-418a-8a4e-7ae6e8bbb346.jpeg)
![A8844D2E-72B7-4E84-9BE7-7FC4C58737A5](https://user-images.githubusercontent.com/122580828/215591943-434f9f2e-6acb-45c9-8f4c-5c597135cb70.jpeg)

- We can observe in the first image that when we succeed the url with "/add-message?s=Hello", the server displays hello.
- This happens because, when we type the above url it calls handleRequest method with the url as the parameter. It goes throught the if condition which checks if the url contains "/add-message". If the condition is true, it creates a string array parameter which is made by splitting the string wiht regex "=". It then checks if the first element of the array is "s". If the condition is true it concatenates the string to variable str(which in this case was "") and returns the string. If any of the conditions are false then it will display "404 Not Found".
- Next, when we add "Hi", it displays Hello and Hi both but in different lines.
- This is because when we added "Hello" to str it also added a new line such that the next time we add "Hi" it is displayed in the next line.
- The code works in a similar way when the url is succeeded by "/add-message?s=I am Suhani".


## Part 2- Bugs


