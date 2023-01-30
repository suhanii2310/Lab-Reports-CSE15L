# Week1 Lab Report
## Part 1- Creating a web server(StringServer)

**Step 1**
We will use two files for this
- Server.java
- StringServer.java
The code for StringServer.java is given below

`
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
`
`

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
`
- This code keeps track of a single string that gets added to by the incoming requests and then concatenates a new line (\n) after the string and stores all the strings added so far.
- To run this code we wil use the commands
- `javac Server.java StringServer.java`
- `java StringServer 4000`
- After compiling and running the code we will be shown the following message-
       `Server Started! Visit http://localhost:4000 to visit.`
- In your browser, visit "http://localhost:4000". The page displayed should look like this


![13397028-3711-4719-B32C-08C6941E5431](https://user-images.githubusercontent.com/122580828/215579612-2a8d3c8c-65ce-4715-b0b7-865d76882e0d.jpeg)








