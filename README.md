# Flask Setup and Tutorial

## 1. Set-Up:

1. Install Python in the system.
2. Make a local folder in the disk (e.g., Flask Project).
3. Open the folder in the command prompt by typing `cmd` in the address bar.
4. Install virtual environment in the folder:
    ```sh
    pip install virtualenv
    ```
5. Create a virtual environment folder:
    ```sh
    virtualenv env
    ```
6. Activate the virtual environment by navigating to scripts:
    ```sh
    cd env
    cd scripts
    activate
    ```
7. Navigate back to the main folder:
    ```sh
    cd ..
    ```
8. Install Flask in the virtual environment:
    ```sh
    pip install Flask
    ```
9. Check if Flask is successfully installed:
    ```py
    python
    import flask
    flask.__version__
    ```
    To exit, press `ctrl + Z`.

## 2. Project Creation In Flask:

1. Create a new Python file for Flask:
    ```sh
    app.py.
    ```
2. Basic flask code to start the flask app:
    ```sh
    from flask import Flask
    
    app = Flask(__name__)
    @app.route("/")
    def hello_world():
       return "<p>Hello, World!</p>"
    ```
3. Run the Flask app to check if it's working:
    ```sh
    flask --app app run
    ```
4. Terminate the server in the cmd:
    ```sh
    Ctrl + C
    ```
## 3. Utilization of the Basic Web Components:

1. Creating the basic folder to start:
    ```sh
    static and templates
    ```
2. Properties of the folders created:
    ```sh
    a. Static folder is public in nature.
    b. Templates folder is private in nature.
    c. All the web components are created in the templates folder.(html, css, js)
    ```
3. Importing the and Using of teh templates folder:
    ```sh
    a. " from flask import Flask, render_template " command is used to import the templates.
    b. We use the return function to show the templates folder during the app run.
    c. return render_template('index.html')
    d. We can also use multiple html files by adding the route.
    e. @app.route("/name of the route")
    ```
4. Dyanmaically updating the preview during the production:
    ```sh
    app.run(debug=True){ for real time changes}
    ```
5. Passing of Variables to the html file:
    ```sh
    a. Firstly in the app.py:
       variable="Rahul"
       return render_template('index.html', name=variable)
    b. Then to display it in the html file:
       {{name}} inside any tag
    ```
## 4. Utilization of the Static folder:

1. Using the jinja(url_for):
    ```sh
    Normal way:
    <img src=”static/img_name.png”>
    using the jinja:
    <img src="{{ url_for('static', filename='img_name.png') }}">
                                OR
    <link href="{{ url_for('static', filename='css/main.css') }}" rel="stylesheet">
    ```
2. Using the jinja(for loop):
    ```sh
    <ul>
    {% for user in users %}
       <li><a href="{{ user.url }}">{{ user.username }}</a></li>
    {% endfor %}
    </ul>
    ```
## 5. Template Inheritance in jinja:

1. Base html file format for the Inheritance:
    ```sh
    <!DOCTYPE html>
    <html lang="en">
    <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>HTML Page</title>
    </head>
   {% block body %} {% endblock %}
   </html>
    ```
2. All the Inheritating classes:
    ```sh
    {% extends "Base.html" %}
    {% block body %}
    <body>
         <!-- All content here -->
    </body>
    {% endblock %}
    ```
3. For further reference on the jinja read the documentation: https://jinja.palletsprojects.com/en/2.11.x/templates/

## 6. Connecting the Database Using Flask and Python:

1. Downloading the Xampp Application and Setting it up:
    https://www.apachefriends.org/download.html
    ```sh
    a. Keep the admin and the password default
    b. Default Admin will be "root"
    c. Default password will be "blank"
    ```
2. Starting the Xampp Control panel:
    ```sh
    a. Start the "Apache".
    b. Start the "MySQl".
    c. Everything should turn green over the apche and mysql.
    d. If Something goes wrong then check ( Task Manager>>Details and check the PID).
    e. End task armsvc.exe and everything should be fine.
    ```
4. Opening the database in the browser:
   http://localhost/phpmyadmin/

## 7. Creating the Database Using Flask and Python:

1. Create a new Database:
    ```sh
    a. Go to http://localhost/phpmyadmin/ link, you will see a interface.
    b. Click on “New” to create a database
    c. Write your database name
    d. Create the database
    ```
2. Create a new Table in the database:
    ```sh
    a. Click on “Create”.
    b. Fill the table according to need.
    c. A_I section for thr primary key. A_I stands for Auto Incrementation. It means it will automatically increment value so that there is no repetition.
    ```
 
   
