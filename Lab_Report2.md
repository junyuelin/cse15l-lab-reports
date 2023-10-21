Below is the screenshot of my code.


<img width="743" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/d6237b15-14b4-4ae0-aa95-fe82615581da">
<img width="433" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/cc21069b-355a-445d-9e70-3029edbd14a9">
<img width="518" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/2533f2b3-583f-448a-9b9b-7ad89297fa94">

For each of the two screenshots, describe:

1. Which methods in your code are called?
2. What are the relevant arguments to those methods, and the values of any relevant fields of the class?
3. How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
By values, we mean specific Strings, ints, URIs, and so on. "abc" is a value, 456 is a value, new URI("http://...") is a value, and so on.)

First screenshot: 
1. The main() and handleRequest() methods are called.
2. The main() method takes the request as a String[] argument and the handleRequest() method takes a URI object as an argument. There are two fields in the Handler class. One is `num` representing the number of requests so far and the other one is the String `output` representing the message shown on the page. `num` is initialized with the value 0 because at the beginning there is no request. `output` is initialized as an empty string because with no request, there shouldn't be any message on the page.
3. After the first request `/add-message?s=Hello`, `num` is incremented to 1 because the first request occurred. And `output` is changed 
