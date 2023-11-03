# Lab Report 2

## Part 1
Below is the screenshot of my code.


<img width="743" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/d6237b15-14b4-4ae0-aa95-fe82615581da">
<img width="433" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/cc21069b-355a-445d-9e70-3029edbd14a9">
<img width="518" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/2533f2b3-583f-448a-9b9b-7ad89297fa94">

For each of the two screenshots, describe:

1. Which methods in your code are called?
2. What are the relevant arguments to those methods, and the values of any relevant fields of the class?
3. How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
By values, we mean specific Strings, ints, URIs, and so on. "abc" is a value, 456 is a value, new URI("http://...") is a value, and so on.)

### First screenshot: 
1. The main() and handleRequest() methods are called.
2. The main() method takes the request as a String[] argument and the handleRequest() method takes a URI object as an argument. There are two fields in the Handler class. One is `num` representing the number of requests so far and the other one is the String `output` representing the message shown on the page. `num` is initialized with the value 0 because at the beginning there is no request. `output` is initialized as an empty string because with no request, there shouldn't be any message on the page.
3. After the first request `/add-message?s=Hello`, `num` is incremented to 1 because the first request occurred. And `output` is changed to `1. Hello` to show the message on the page. Also the argument `url` is changed to the URL `https://localhost2310/add-message?s=Hello`.

### Second screenshot:
1. The main() and handleRequest() methods are called.
2. The main() method takes the request as a String[] argument and the handleRequest() method takes a URI object as an argument. There are two fields in the Handler class. One is `num` representing the number of requests so far and the other one is the String `output` representing the message shown on the page. `num` is initialized with the value 0 because at the beginning there is no request. But after the first request, `num` is incremented to 1. `output` is initialized as an empty string because with no request, there shouldn't be any message on the page. But after the first request, `output` is changed to `1. Hello`.
3. After the second request `/add-message?s=How are you`, `num` is incremented to 2 because the second request was sent int and `output` is changed to `1. Hello\n2. How are you`. Also the argument `url` is changed to the URL `https://localhost2310/add-message?s=How are you`.

## Part 2
Using the command line, show with ls and take screenshots of:

1. The path to the private key for your SSH key for logging into ieng6 (on your computer or on the home directory of the lab computer)

<img width="765" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/15e98fdc-ea94-490d-a86e-5004b0637085">

2. The path to the public key for your SSH key for logging into ieng6 (within your account on ieng6)
<img width="440" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/ff987de9-960e-4f60-a6b0-ebbc28dac21d">

3. A terminal interaction where you log into ieng6 with your course-specific account without being asked for a password.
<img width="782" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/55801474-437c-4a44-ae58-4f1be0fde187">

## Part 3
In a couple of sentences, describe something you learned from lab in week 2 or 3 that you didn’t know before.

It is really cool that we can connect to a computer in the CSE basement remotely by using the `ssh` command followed by our course-specific account to establish a connection between the client and the server. We can enter commands on our client computer but run those commands on the remote server. Also it is really cool that we can write a java program to start a web server and change the content showed on the web if the url entered is changed. It is interesting to know how the web server works under the hood and implement the StringServer.java
