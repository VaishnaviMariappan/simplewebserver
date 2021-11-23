# Developing a Simple Webserver
## AIM:
To develop a simple webserver to display top five programming languages.

## DESIGN STEPS:
### Step 1: 
HTML content creation
### Step 2:
Design of webserver workflow
### Step 3:
Implementation using Python code
### Step 4:
Serving the HTML pages.
### Step 5:
Testing the webserver

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1>TOP FIVE PROGRAMMING LANGUAGES</h1>
<h2>1)C++</h2>
C++ is a computer programming language based on C.The C++ programming language was developed by Bjarne Stroustrup at Bell Labs in the 1980s, and was originally named "C with classes".
The language was planned as an improvement on the C programming language, adding features based on object-oriented programming. C++ is portable and can be used to develop applications that can be adapted to multiple platforms.
C++ is fun and easy to learn!. C++ is mainly used in Games, GUI based applications, Database Software, Operating Systems, Browsers Mozilla Firefox.
<h2>2)PYTHON</h2>
Python is an open source programming language that was made to be easy-to-read and powerful. A Dutch programmer named Guido van Rossum made Python in 1991.
Python is an interpreted language. Interpreted languages do not need to be compiled to run.
It is a high-level language.Python drew inspiration from other programming languages like C, C++, Java, Perl, and Lisp.
Python is often used for Web development, Scientific programming, Desktop GUIs applications, Network programming, Game programming.
<h2>3)C</h2>
C is a high-level and general-purpose programming language that is ideal for developing firmware or portable applications.
Originally intended for writing system software, C was developed at Bell Labs by Dennis Ritchie for the Unix Operating System in the early 1970s.
Ranked among the most widely used languages, C has a compiler for most computer systems and has influenced many popular languages – notably C++.C is highly portable and is used for scripting system applications which form a major part of Windows, UNIX, and Linux operating system. 
C can efficiently work on enterprise applications, games, graphics, and applications requiring calculations, etc.
<h2>4)JAVA</h2>
Java is the name of a programming language created by Sun Microsystems.Java is an object oriented languages that produces software for multiple platforms.Java runs on many different operating systems, including Android. Java is commonly used to teach students how to program as a first language, but is still also used by professionals.
 When a programmer writes a Java application, the compiled code (known as bytecode) runs on most operating systems (OS), including Windows, Linux and Mac OS. 
Applications of Java Programming Language are Gaming Applications, Big Data Technologies, Distributed Applications, Cloud-based Applications, IoT Applications.
<h2>5)JAVASCRIPT</h2>
JavaScript is a lightweight, cross-platform, and interpreted scripting language. It is well-known for the development of web pages, many non-browser environments also use it.
JavaScript is a programming language commonly used in web development. It was originally developed by Netscape as a means to add dynamic and interactive elements to websites. For example, a JavaScript function may check a web form before it is submitted to make sure all the required fields have been filled out.
JavaScript is a flexible and powerful programming language that is implemented consistently by various web browsers. Along with HTML and CSS, it's a core component of web technology. While HTML is responsible for structure and CSS is responsible for style, JavaScript provides interactivity to web pages in the browser.

</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8080)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```


## OUTPUT:
### CLIENT SIDE OUTPUT:
![CLIENTSIDEOUTPUT](./Clientside.png)

### SERVER SIDE OUTPUT:
![SERVERSIDEOUTPUT](./Serverside1.png)
![SERVERSIDEOUTPUT](./Serverside2.png)

## RESULT:
Thus, a simple webserver is created to display top five programming languages.
