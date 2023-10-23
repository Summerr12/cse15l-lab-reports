## Benjamin Nhan, 
## CSE15L
---
##P1
**String Server code**
![Image](Screenshot_2023-10-22_at_5.23.57_PM.png)

**/add-message?s=....**
![Image](/Screenshot_2023-10-22_at_5.19.30_PM.png)
This url calls the path/add-message in the handlersRequest function which is the second if statement. Then we get the query from the "?" and the 0th parameter being "s" = the string "piggy. 
Specifically, we use the String[] parameter to start a list and the new word would represent parameter[1]. num++ is to increment the list to keep increasing so the words don't all stack onto 1 row. 
If we add a word which means we use ?s=, then we use the return line word+= "\n"+um+ ": " + parameters[1] which translates to (current position of the list)#: "".


![Image](/Screenshot_2023-10-22_at_5.28.38_PM.png)
This url calls the path/add-message in the handlersRequest function which is the second if statement. Then we get the query from the "?" and the 0th parameter being "s" = the string "ice cream".  One change here is in the url, we see the space changed into "%20"
Specifically, we use the String[] parameter to start a list and the new word would represent parameter[1]. num++ is to increment the list to keep increasing so the words don't all stack onto 1 row. 
If we add a word which means we use ?s=, then we use the return line word+= "\n"+um+ ": " + parameters[1] which translates to (current position of the list)#: "".
The only change here is the String that is being input into the website.

##P2

**Path to Private key on the computer**

![Image](image.png)

**Path to Public key while logged into ieng6**
![Image](image1.png)

**Terminal interaction of logging in without the password**
![Image](image3.png)

##P3

From week 2 or 3, i've learned how to read the URL and how paths/queries/ and reading the code for creating those paths to access some add or increment codes to work in the browser. Query being the ? and anything after will be sifted throught the code to check whether or not that is the correct input to activate the if statement to do whatever the code wanted
I also learned how to edit the NumberServer to adopt into StringServer and use lists to make a list of words. 
