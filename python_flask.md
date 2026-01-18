# Introduction to Web development using Flask**

Flask is a lightweight and flexible web framework for python . It's designed to make getting started with **web development** quick and easy, while still being powerful enough to build complex web applications. It is an API of Python that allows us to build web applications.

It was developed by Armin Ronacher. Flask's framework is more explicit than **Django's framework** and is also easier to learn because it has less base code to implement a simple web application. Flask Python is based on the WSGI(Web Server Gateway Interface) toolkit and Jinja2 template engine.

**Advantages of Flask**

- Flask is a **lightweight** backend framework with minimal dependencies.

- Flask is **easy to learn** because its simple and intuitive API makes it easy to learn and use for beginners.

- Flask is a **flexible** **Framework** because it allows you to customize and extend the framework to suit your needs easily.

- Flask can be used with **any database** like:- SQL and NoSQL and with **any Frontend Technology** such as **React** or **Angular**

- Flask is **great for small to medium projects** that do not require the complexity of a large framework.



**Getting Started With Flask**

Python3 is required for the installation of the Python Web Framework Flask. You can start by importing Flask from the Flask Python package on any Python IDE. For installation on any environment, you can execute the command "**pip install flask**" on your terminal. Let's look at an example of a basic flask app.

```python

from flask import Flask     
app = Flask(__name__)   # Flask constructor 
  
# A decorator used to tell the application 
# which URL is associated function 
@app.route('/')       
def hello(): 
    return 'HELLO'
  
if __name__=='__main__': 
   app.run(debug=True)
```

**Explanation:**

- **Flask(__name__):** Creates the Flask app.
- **@app.route('/'):** Defines the home route (/).
- **def hello():** creates a function that is bound with '**/**' route and returns "HELLO" when the root page is accessed.
- **app.run(debug=True):** runs the app in debug mode. It ensure that app is not need to restart manually if any changes are made in code.

**Build Flask Routes in Python**

Web frameworks provide routing technique so that user can remember the URLs. It is useful to access the web page directly without navigating from the Home page. It is done through the following route() decorator, to bind the URL to a function.
```python
# decorator to route URL 
@app.route(‘/hello’) 

# binding to the function of route 
def hello_world():     
    return ‘hello world’
```

**Explanation:** If a user visits **http://localhost:5000/hello** URL, the output of the **hello_world() **function will be rendered in the browser.

One alternate way of doing this is by using "**add_url_rule()"** function of an application object, it can also be used to bind URL with the function similar to the above example.
```python
def hello_world():
    return ‘hello world’
  
app.add_url_rule(‘/’, ‘hello’, hello_world)
```

**Variables in Flask**

Variables in flask are used to build a URL dynamically by adding the variable parts to the rule parameter. It is passed as keyword argument. Here's an example.

**from** **flask** **import** Flask
```python
from flask import Flask 
app = Flask(__name__) 

@app.route('/hello/<name>') 
def hello_name(name): 
    return 'Hello %s!' % name 

if __name__ == '__main__': 
    app.run(debug = True)

```
**Explanation:** parameter of **route**() decorator contains the variable part attached to the URL '**/hello**' as an argument. Hence, if URL like "**http://localhost:5000/hello/ashim"** is entered then "ashim" will be passed to the **hello**() function as an argument.

Besides the default string type, Flask also supports int, float, and path (which allows slashes for directories). Flask's URL rules use **Werkzeug’s **routing module, ensuring unique URLs following Apache's conventions. Here's an example.

```python
from flask import Flask 

app = Flask(__name__) 

@app.route('/blog/<int:postID>')
def show_blog(postID): 
    return 'Blog Number %d' % postID  

@app.route('/rev/<float:revNo>')
def revision(revNo): 
    return 'Revision Number %f' % revNo  

if __name__ == '__main__': 
    app.run(debug=True)
```


**http://127.0.0.1:5000/blog/555**

**http://127.0.0.1:5000/rev/1.1**



**Explanation:**

- **/blog/555** captures 555 as an integer and returns "Blog Number 555".

- **/rev/1.1** captures 1.1 as a float and returns "Revision Number 1.100000" (default float format).

**Build a URL in Flask**

Dynamic Building of the URL for a specific function is done using **url_for()**function. The function accepts the name of the function as first argument, and one or more keyword arguments. See this example

```python
from flask import Flask, redirect, url_for
app = Flask(__name__)


@app.route('/admin')  # decorator for route(argument) function
def hello_admin():  # binding to hello_admin call
    return 'Hello Admin'


@app.route('/guest/<guest>')
def hello_guest(guest):  # binding to hello_guest call
    return 'Hello %s as Guest' % guest


@app.route('/user/<name>')
def hello_user(name):
    if name == 'admin':  # dynamic binding of URL to function
        return redirect(url_for('hello_admin'))
    else:
        return redirect(url_for('hello_guest', guest=name))


if __name__ == '__main__':
    app.run(debug=True)
```
- To test this, save the above code and run through python shell and then open browser and enter the following URLs-

**http://localhost:5000/user/admin**

Admin

**http://localhost:5000/user/ABC**

guest/ABC

**Explanation:**
The above code has a function named user(name), accepts the value through input URL. It checks that the received argument matches the 'admin' argument or not. If it matches, then the function hello_admin() is called else the hello_guest() is called.

**HTTP method are provided by Flask**
Python Web Framework Flask support various HTTP protocols for data retrieval from the specified URL, these can be defined as:-

| Method | Description |
|:------:|:-----------|
| GET    | Sends data to the server via URL parameters. Data is visible in the URL and not encrypted. |
| HEAD   | Similar to GET but only retrieves the headers, not the body of the response. |
| POST   | Sends form data to the server in the request body. Data is not cached and can include sensitive information. |
| PUT    | Replaces the current representation of the target resource at the given URL. |
| DELETE | Deletes the target resource identified by the URL. |
