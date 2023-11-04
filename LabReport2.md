## Benjamin Nhan, 
## CSE15L
## Lab Report 2
---
##P1
**String Server code**
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    String word = "";
    int num=0;
///add-message?s=<string>
    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return "current list:" +"\n" +word;
        } else {
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    num++;
                    return word += "\n" + num + ": " + parameters[1];
                }
            }
            return "404 Not Found!";
        }
    }
}
```
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
///You missed mentioning the arguments that were passed to the methods that were called. Please include that!
**/add-message?s=....**
![Image](/Screenshot_2023-10-22_at_5.19.30_PM.png)
The server is already started so we use `StringServer` and the method is `main`. The other method would be `handleRequest` in the `Handler` class. The relevant arguement to the method handleRequest is called url which has a class type of URI. The url in the image calls the `handlersRequest function` and the input includes `path/add-message`. Then we get the query from the "?" and the 0th parameter being "s" = the string "piggy". In this image, I clicked `/add-message` 3 times and attached 3 different values to the parameter `s` which the last input happened to contain "piggy"
Specifically, we use the `String[] parameters` to start a list and the new word would represent `parameter[1]` because when we return word, there is a  "\n" that indents. `num++` is to increment the list to keep increasing so list doesn't say "1.". We also used the 0th parameter to check if it was equal to "s".
If we add a word which means we use ?s=, then we use the return line `word+= "\n"+num+ ": " + parameters[1]` which translates to (current position of the list)#: "".
The variable that holds the the string list changes after every url input because it has to continually add words onto it only if we do `/add-message`.


![Image](/Screenshot_2023-10-22_at_5.28.38_PM.png)
This url calls the `path/add-message` in the `handlersRequest` function which is the second if statement. Then we get the query from the "?" and the 0th parameter being `"s" = the string "ice cream"`.  One change here is in the url, we see the space changed into "%20"
Specifically, we use the `String[]` parameter to start a list and the new word would represent parameter[1]. `num++` is to increment the list to keep increasing so the words don't all stack onto 1 row. 
If we add a word which means we use `?s=`, then we use the return line `word+= "\n"+um+ ": " + parameters[1]` which translates to (current position of the list)#: "".
The only change here is the String that is being input into the website.

##P2

**Path to Private key on the computer**

![Image](image.png)

**Path to Public key while logged into ieng6**
![Image](image1.png)

**Terminal interaction of logging in without the password**
![Image](image3.png)

##P3

From week 2 or 3, I've learned how to read the URL and how `paths/queries/` and reading the code for creating those paths to access some add or increment codes to work in the browser. Query being the `?` and anything after will be sifted throught the code to check whether or not that is the correct input to activate the if statement to do whatever the code wanted
I also learned how to edit the `NumberServer` to adopt into `StringServer `and use lists to make a list of words. 
