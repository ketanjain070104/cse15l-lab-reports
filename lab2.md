# **LAB REPORT 2**
This report covers the guide to creation of a new server, my fix to a bug discussed in lab 3 and my experience and something new I learnt in these past 2 labs.
## **Part 1**
The implementation of the described web server was somewhat similar to the Server.java and NumberServer.java file given to us in lab 2. I made some changes to these files, keeping most of the code similar. The code for the server looks as follows:
```
# StringServer.java
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    String input = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return input;
        }
        else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    input = input + "\n" + parameters[1];
                    return input;
                }
            }
            return "404 Not Found!";
        }
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
```
# Server.java
// A simple web server using Java's built-in HttpServer

// Examples from https://dzone.com/articles/simple-http-server-in-java were useful references

import java.io.IOException;
import java.io.OutputStream;
import java.net.InetSocketAddress;
import java.net.URI;

import com.sun.net.httpserver.HttpExchange;
import com.sun.net.httpserver.HttpHandler;
import com.sun.net.httpserver.HttpServer;

interface URLHandler {
    String handleRequest(URI url);
}

class ServerHttpHandler implements HttpHandler {
    URLHandler handler;
    ServerHttpHandler(URLHandler handler) {
      this.handler = handler;
    }
    public void handle(final HttpExchange exchange) throws IOException {
        // form return body after being handled by program
        try {
            String ret = handler.handleRequest(exchange.getRequestURI());
            // form the return string and write it on the browser
            exchange.sendResponseHeaders(200, ret.getBytes().length);
            OutputStream os = exchange.getResponseBody();
            os.write(ret.getBytes());
            os.close();
        } catch(Exception e) {
            String response = e.toString();
            exchange.sendResponseHeaders(500, response.getBytes().length);
            OutputStream os = exchange.getResponseBody();
            os.write(response.getBytes());
            os.close();
        }
    }
}

public class Server {
    public static void start(int port, URLHandler handler) throws IOException {
        HttpServer server = HttpServer.create(new InetSocketAddress(port), 0);

        //create request entrypoint
        server.createContext("/", new ServerHttpHandler(handler));

        //start the server
        server.start();
        System.out.println("Server Started! Visit http://localhost:" + port + " to visit.");
    }
}
```
The code for StringServer.java is quite similar to NumberServer.java and the code for Server.java is the same. The code gives the following input.
![Image](Screenshot (21).png)
When the URL `http://localhost:9000/add-message?s=Hello` is inputted, the handleRequest method in StringServer.java is called. It takes arguement 'url' of type 'URL' and returns a string array containing query in the url, split into two parts i.e. 'command' and 'string to be added' respectfully. This modifies of the global variable input to "Hello".
![Image](Screenshot (22).png)
When the URL `http://localhost:9000/add-message?s=How%20are%20you?` is inputted, the handleRequest method in StringServer.java is called again. It does the same thing as discussed above, i.e., it modifies the global variable input from "Hello" to "Hello /n How are you?". All these method calls are recorded in the terminal.
![Image](Screenshot (23).png)

## **Part 2**
I took a bug in reversed() method of lab 3. One such instance is 
```
@Test
public void testReversed_2(){
int[] input1 = {1, 2, 3, 4};
int[] ary = ArrayExamples.reversed(input1);
assertArrayEquals(new int[]{4, 3, 2, 1}, ary);
}
```
The buggy code, however, produced correct outputs for certain inputs
```
@Test
public void testReversed_1(){
int[] input1 = { };
assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
}
```
**Symptom**
The working case worked because it was an empty array list, so it passed as the reversed array would also be empty. However, in the case of the buggy test, the code failed because it was simply copying the numbers into the new array list rather than reversing the order.


**Fix**
```
#Before
static int[] reversed(int[] arr){
   int[] newArray = new int[arr.length];
   for(int i = 0; i < arr.length; i += 1){
     arr[i] = newArray[arr.length - i - 1];
   }
   return arr;
}
```
```
#After
static int[] reversed(int[] arr){
   int[] newArray = new int[arr.length];
   for(int i = 0; i < arr.length; i += 1){
     newArray[i] = arr[arr.length - i - 1];
   }
   return newArray;
}
```
![Image](Screenshot (25).png)
It seems that the problem was that the method was not editing the created array list. By replacing arr and newArray, the reversed method creates a new array list and copies elements into that list in reverse order.

## **Part 3**
I learnt how to work with GitHub desktop and how to push changes made to a git repository. I also learnt how to create a clone of the repository locally and then via GitHub Desktop, use VS Code to make changes to the code. These changes can be pushed onto the master file directly through the desktop app.
