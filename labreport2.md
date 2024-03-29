# Lab Report 2 <br/>
January 29, 2024 <br/>
Creating a Chat Server: <br/>
We are using the `/add-message` query within the url to generate a username and message within the website.

---

Chat Server:
```
import java.io.IOException;
import java.net.URI;


class Handler implements URLHandler {
    String mainThread = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/add-message")) {
            String[] addParameters = url.getQuery().split("&");
            String[] parameter1 = addParameters[0].split("=");
            String[] parameter2 = addParameters[1].split("=");
            if(parameter1[0] == s && parameter2[0] == user) {
                mainThread += parameter2[1] + ": " + parameter1[1] + "\n";
                return mainThread;
            }
            return "Incorrect Query!";
        }
    }
}

class ChatServer {
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
`/add-message` examples: <br/>
<br/>
![Adding Messages](./Screenshots/addMessageExample2.png) <br/>
* The `/add-message` command references the `handle request` method
* It takes in an input of a url. The input here is "https://0-0-0-0-1212-5c7o9m6ioc4leds0r7eh4hrdj8.us.edusercontent.com/add-message?s=Hello&user=jpolitz".
* Then, we take the query of that link and seperate it into multiple parts in order to find the user and the message, parameters 1 and 2 respectively. In this case, those arguments are "user=jpolitz" and "s=Hello".
* Then, we need to seperate the identifier `s=` and `user=` with the field information. We seperate these parts of the query apart, but then need to check that we recieved the correct identifiers before we return the ChatServer message.
* Afterwards, we concatenate those two strings together in order to print out a message in the form of <user>: <message>(jpolitz: Hello).
* The values changed are the values within `parameter1`, `parameter2`, and `mainThread`. Parameters 1 and 2 get replaced, while `mainThread` keeps getting added onto. The class field for this input is the URL, but we only need to use the query. In this case, the query is `add-message?s=Hello&user=jpolitz`

---

`/add-message` examples: <br/>
<br/>
![Adding Messages](./Screenshots/addMessageExample1.png)
* The `/add-message` command references the `handle request` method
* It takes in an input of a url. The input here is "https://0-0-0-0-1212-5c7o9m6ioc4leds0r7eh4hrdj8.us.edusercontent.com/add-message?s=How%20are%20you&user=yash".
*  Next, we take the query of that link and seperate it into multiple parts in order to find the user and the message, parameters 1 and 2 respectively. In this case, those parguments are `user=yash` and `s=How%20are%20you`. The `%20` is the way in which we write spaces within URLs.
*  Then, we need to seperate the identifier `s=` and `user=` with the field information. We seperate these parts of the query apart, but then need to check that we recieved the correct identifiers before we return the ChatServer message.
* Afterwards, we concatenate those two strigns together in order to print out a message in the form of <user>: <message>(yash: how are you). In this case, the url query cannot handle spaces within it so it adds + signs between each of the words, making it look like this(yash: how+are+you).
* The values changed are the values within `parameter1`, `parameter2`, and `mainThread`. Parameters 1 and 2 get replaced, while `mainThread` keeps getting added onto. The class field for this input is the URL, but we only need to use the query. In this case, the query is `add-message?s=How%20are%20you&user=yash`

---

This is the absolute path to the public key: <br/>

![Public Directory](./Screenshots/PublicLocation.png)

---

This is the absolute path to the private key in the ieng6 system: <br/>

![Private Directory](./Screenshots/PrivateLocation.png)

---

I have logged in to the ieng6 system without requiring a password: <br/>

![No Password Needed](./Screenshots/NoPassword)

---

In weeks 2 and 3 I learned many new things that I didn't know before, but one of the biggest ones was the different elements of a url link, and how we can manipulate them to change a website. I thought that it was really interesting that we can use a url query as an input for our code, and how each element of the url has its own importance within the search. For both `ChatServer` and `SearchEngine` we used the query to append to lists and create text based websites that can be updated by th euser simply by typing in a different URL, which I thought was really cool.

