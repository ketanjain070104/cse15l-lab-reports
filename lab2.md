# **LAB REPORT 2**
This report covers the guide to creation of a new server, my fix to a bug discussed in lab 3 and my experience and something new I learnt in these past 2 labs.
## **Part 1**
The implementation of the described web server was somewhat similar to the Server.java and NumberServer.java file given to us in lab 2. I made some changes to these files, keeping most of the code similar. The code for the server looks as follows.
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
