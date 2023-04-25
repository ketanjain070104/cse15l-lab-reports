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
I chose a bug from ListExamples.java. The error in the code is that the method filter doesnt operate correctly all the time. A particular instance is 
```
@Test
    public void testFilterManyCorrect(){
        List<String> str1 = new ArrayList<>();
        str1.add("apple");
        str1.add("somelongstring");
        str1.add("somelongstring2");
        str1.add("somelongstring3");
        str1.add("tinystring");       
        
        List<String> str2 = new ArrayList<>();
        str2.add("somelongstring");
        str2.add("somelongstring2");
        str2.add("somelongstring3");
        assertEquals(str2, ListExamples.filter(str1, new lengthGraterThan()));
    }
```
The code returns the correct output, despite being buggy, for some inputs
```
@Test
    public void testFilterNoCorrect(){
        List<String> str1 = new ArrayList<>();
        str1.add("apple");
        str1.add("tinystring");       
        
        List<String> str2 = new ArrayList<>();

        assertEquals(str2, ListExamples.filter(str1, new lengthGraterThan()));
    }
```
**Symptom**


The order of the output filter is in reverse order of what it should be.

**Fix**
```
# Before
static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(0,s);
      }
    }
    return result;
  }
```
```
# After
static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(s);
      }
    }
    return result;
  }
```
The function was adding elements at index '0' rather than adding them at the end of the list whihc was reversing the order of output as it should have been.

## **Part 3**
I learnt how to work with GitHub desktop and how to push changes made to a git repository. I also learnt how to create a clone of the repository locally and then via GitHub Desktop, use VS Code to make changes to the code. These changes can be pushed onto the master file directly through the desktop app.
