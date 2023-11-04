## Benjamin Nhan, 
## CSE15L
## Lab Report 3
## Week 4
---
## P1
Provide:

**A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)**

```
	@Test 
	public void testReverseInPlaceBetterTest() {
    int[] inputT2 = { 2,4,6,8,10,12 };
    ArrayExamples.reverseInPlace(inputT2);
    assertArrayEquals(new int[]{12,10,8,6,4,2}, inputT2);
	}

```


**An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)**

```
	@Test 
	public void testReverseInPlaceAlwaysRightButWrong() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}
```

**The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)**
![Image](p3inputR3.png)

**The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
Briefly describe why the fix addresses the issue.**

```
  //before/old version of reverseInPlace
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

```
  //new version of reverseInPlace
  static void reverseInPlace(int[] arr) {
    int[] test = new int[arr.length];

    for(int i = 0; i < arr.length; i += 1) {
      test[i] = arr[arr.length - i-1];
    }
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = test[i];
    }
  }
```
The issue with the code was because when we would try to move the value at the right end of the array to the left, it would replace the values of the same array we were taking from. This is very wrong so to fix it, I made a temporary test array and moved the reverse in another array. Therefore the values didn't clash and I made another for loop to move the correct values from the temp array into the formal one. The error can be seen in the output where they expeceted a 6 but saw a 8 because the next iteration after the half, the right end of the values never got swapped.

## P2

I chose `less` and according to google, it "shows a file's contents one screen at a time". When I used less, I got to see the terminal get replaced by the file text and you couldn't leave until you had your 45 rewards points I wanted to use. This also takes over the terminal until you click q. Here are 4 different command line options or alternate ways to use the command `less`

***1) -p (pattern)***

technical/ directory code :

```
less -p use technical/biomed/
Output:
technical/biomed is a directory
```
The code here isn't useful because it only states that /biomed is a directory and doesn't do anything to it. even if you move the code into a .txt by adding `> tested.txt`, it will still output "is a directory" I found -p in https://man7.org/linux/man-pages/man1/less.1.html 

technical/ .txt code :

```
less -p use technical/biomed/1471-2180-2-35.txt
Output:
 Background
        Mounting concerns about drug-resistant pathogenic
        bacteria [ 1 2 3 ] have rekindled interest in alternative
        treatments of bacterial infections. Prominent among these
        alternatives is phage therapy, the use of bacteriophages to
        kill or otherwise control the bacterial populations in
        infected hosts. The use of bacteriophage for the treatment
        of bacterial infections is an old idea [ 4 ] that not only
        caught the imagination of at least one novelist [ 5 ] it
        was practiced with sporadic successes worldwide in the
        1920s and 1930s. However, following the development of
        antibiotics in the 1940s, the use of phages to treat and
        prevent infections disappeared from so-called Western
        Medicine, but it did survive in the former Soviet Union. A
        rekindled interest in phage therapy over the past decade
        has inspired historical reviews, increased our awareness of
        a substantial body of phage therapy work from Eastern
        Europe [ 6 7 8 ] , resulted in the West's "discovery" of
        the Eliava Institute (a one-time vast and thriving phage
        therapy research and production facility in Tiblisi,
        Georgia [ 9 ] ), and motivated the formation of companies
        developing phage therapy (Biophage Inc. of Montreal,
        Canada; Exponential Biotherapies Inc. of Port Washington,
        NY; Intralytix of Baltimore, MD). In recent years this
        renewed interest in phage therapy has been displayed in
        articles in the popular press, (e.g., Kuchment 2001,
        Superbug Killers, News Week, Dec. 17, 2001 50-51) and, of
        course, reviews and discussions on the internet,
        http://www.phage.org;
        http://www.evergreen.edu/user/T4/PhageTherapy/Phagethea.html.
```
The code `-p` finds a pattern inside the .txt file "use" because I chose that pattern to be searched. So in the terminal, we actually see the word "use" be highlighted throughout the text which is helpful for doing research and finding keywords. I found -p in https://man7.org/linux/man-pages/man1/less.1.html


***2) -o (filename)***

technical/ directory code :

```
less technical/biomed/ | less -o tested.txt
Output:
Warning: "tested.txt" exists; Overwrite, Append, Don't log, or Quit? 
Overwrite, Append, Don't log, or Quit? (Type "O", "A", "D" or "Q") 
```
The code here isn't useful because it only states that /biomed is a directory and doesn't do anything to it. even if you move the code into a .txt by adding `> tested.txt`, it will still output "is a directory" I found it in `man less` in the terminal

technical/ .txt code :

```
less technical/biomed/1471-2180-2-35.txt | less -o tested.txt
Output:
Background
        Mounting concerns about drug-resistant pathogenic
        bacteria [ 1 2 3 ] have rekindled interest in alternative
        treatments of bacterial infections. Prominent among these
        alternatives is phage therapy, the use of bacteriophages to
        kill or otherwise control the bacterial populations in
        infected hosts. The use of bacteriophage for the treatment
        of bacterial infections is an old idea [ 4 ] that not only
        caught the imagination of at least one novelist [ 5 ] it
        was practiced with sporadic successes worldwide in the
        1920s and 1930s. However, following the development of
        antibiotics in the 1940s, the use of phages to treat and
        prevent infections disappeared from so-called Western
        Medicine, but it did survive in the former Soviet Union....

```
This code o moves the text file to a file I created called tested.txt. I found it in `man less` in the terminal

***3) -N ***

technical/ directory code :

```
less -N technical/biomed/
Output:             
technical/biomed/ is a directory
```
The code here isn't useful because it only states that /biomed is a directory and doesn't do anything to it. even if you move the code into a .txt by adding `> tested.txt`, it will still output "is a directory" I found it in https://man7.org/linux/man-pages/man1/less.1.html after searching up less command-line options on google

technical/ .txt code :

```
less -N technical/biomed/1471-2180-2-35.txt
output:
  1 
      2   
      3     
      4       
      5         Background
      6         Mounting concerns about drug-resistant pathogenic
      7         bacteria [ 1 2 3 ] have rekindled interest in alternative
      8         treatments of bacterial infections. Prominent among these
      9         alternatives is phage therapy, the use of bacteriophages to
     10         kill or otherwise control the bacterial populations in
     11         infected hosts. The use of bacteriophage for the treatment
     12         of bacterial infections is an old idea [ 4 ] that not only
     13         caught the imagination of at least one novelist [ 5 ] it
     14         was practiced with sporadic successes worldwide in the
     15         1920s and 1930s. However, following the development of
     16         antibiotics in the 1940s, the use of phages to treat and
     17         prevent infections disappeared from so-called Western
     18         Medicine, but it did survive in the former Soviet Union. A
     19         rekindled interest in phage therapy over the past decade
     20         has inspired historical reviews, increased our awareness of
     21         a substantial body of phage therapy work from Eastern
     22         Europe [ 6 7 8 ] , resulted in the West's "discovery" of
     23         the Eliava Institute (a one-time vast and thriving phage
     24         therapy research and production facility in Tiblisi,
     25         Georgia [ 9 ] ), and motivated the formation of companies
     26         developing phage therapy (Biophage Inc. of Montreal,
     27         Canada; Exponential Biotherapies
```
The code -N makes each line an iteration so it just counts the total number of lines in the file. This is helpful just to keep count of your file line number. I found it in https://man7.org/linux/man-pages/man1/less.1.html after searching up less command-line options on google


***4) -e ***

technical/ directory code :

```
less -e technical/biomed/
Output:                         
technical/biomed/ is a directory
```
The code here isn't useful because it only states that /biomed is a directory and doesn't do anything to it. even if you move the code into a .txt by adding `> tested.txt`, it will still output "is a directory" I found it in https://man7.org/linux/man-pages/man1/less.1.html after searching up less command-line options on google

technical/ .txt code :

```
less -e technical/biomed/1471-2180-2-35.txt
output:
Background
        Mounting concerns about drug-resistant pathogenic
        bacteria [ 1 2 3 ] have rekindled interest in alternative
        treatments of bacterial infections. Prominent among these
        alternatives is phage therapy, the use of bacteriophages to
        kill or otherwise control the bacterial populations in
        infected hosts. The use of bacteriophage for the treatment
        of bacterial infections is an old idea [ 4 ] that not only
        caught the imagination of at least one novelist [ 5 ] it
        was practiced with sporadic successes worldwide in the
        1920s and 1930s. However, following the development of
        antibiotics in the 1940s, the use of phages to treat and
        prevent infections disappeared from so-called Western
        Medicine, but it did survive in the former Soviet Union. A
        rekindled interest in phage therapy over the past decade
        has inspired historical reviews, increased our awareness of
        a substantial body of phage therapy work from Eastern
        Europe [ 6 7 8 ] , resulted in the West's "discovery" of
        the Eliava Institute (a one-time vast and thriving phage
        therapy research and production facility in Tiblisi,
        Georgia [ 9 ] ), and motivated the formation of companies
        developing phage therapy (Biophage Inc. of Montreal,
        Canada; Exponential Biotherapies Inc. of Port Washington,
        NY; Intralytix of Baltimore, MD). In recent years this
        renewed interest in phage therapy has been displayed in
        articles in the popular press, (e.g., Kuchment 2001,
        Superbug Killers, News Week, Dec. 17, 2001 50-51) and, of
        course, reviews and discussions on the internet,
```
The code -e exits the terminal page when you scroll all the way to the bottom of the file as if to say you are done so there is no need for you to stay on the page. I found it in https://man7.org/linux/man-pages/man1/less.1.html after searching up less command-line options on google
