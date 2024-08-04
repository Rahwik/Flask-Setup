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
## 8. Flask SQLAlchemy and inputing data to Database:

1. Install flask-sqlalchemy in the system.
   ```sh
    pip install flask-sqlalchemy
    or
    pip install flask_sqlalchemy
    ```
2. Import this module in the python file.
   ```sh
   from flask_sqlalchemy import SQLAlchemy
   ```
3. To connect with the database first we have to give database’s address.
   ```sh
   app.config['SQLALCHEMY_DATABASE_URI'] = 'mysql://username:password@localhost/db_name'
   ```
4. If do not set the user or the password during the installtion of the xammp the default values are:
    ```sh
    username: root
    password: BLANK
    db_name: is the database name which we have setup
    app.config['SQLALCHEMY_DATABASE_URI'] = 'mysql://root:@localhost/DATABASENAME'
    It should look shomething like this once configured.
    ```
6. Importing the class and object from the sqlalchemy and to do so we have to make a variable:
    ```sh
    db = SQLAlchemy(app)
    ```
7. Once we have connected to the database we need to access the table in the python file:
    ```sh
    class Contacts(db.Model):
       sno = db.Column(db.Integer, primary_key=True)
       name = db.Column(db.String(80), nullable=False)
       phone_num = db.Column(db.String(12), nullable=False)
       msg = db.Column(db.String(120), nullable=False)
       date = db.Column(db.String(12), nullable=True)
       email = db.Column(db.String(20), nullable=False)
    ```
## 9. POST request in contact form:

1. Basic structure of a post request:
    ```sh
    @app.route("/contact", methods = ['GET', 'POST'])
    def contact():
        return render_template('index.html')
    ```
5. Implementation of the POST method:
    ```sh
    @app.route("/contact", methods = ['GET', 'POST'])
    def contact():
       if(request.method=='POST'):
            '''Fetch data and add it to the database'''
       return render_template('index.html')
    ```
6. Fetch data from the form and send to the database:
    ```sh
    a. First add name attribute to the html:
       <input name="email" type="email" placeholder="Email Address">
    b. We use the name attribute to locate the data from the form and send to data base:
       @app.route("/contact", methods = ['GET', 'POST'])
       def contact():
          if(request.method=='POST'):
            '''Add entry to the database'''
             name = request.form.get('name')
             email = request.form.get('email')
             phone = request.form.get('phone')
             message = request.form.get('message')
             entry = Contacts(name=name, phone_num = phone, msg = message, date= 
             datetime.now(),email = email )
             db.session.add(entry)
             db.session.commit()
        return render_template('contact.html')
    c. Now to we need to add method and action in te html file, like this:
       <form name="sentMessage" action = "/contact" method="post" novalidate>
    ```
7. After everything the main.py file should look something like this :
   ```sh
   from flask import Flask, render_template, request
   from flask_sqlalchemy import SQLAlchemy
   from datetime import datetime

   app = Flask(__name__)
   app.config['SQLALCHEMY_DATABASE_URI'] = 'mysql://root:@localhost/codingthunder'
   db = SQLAlchemy(app)


   class Contacts(db.Model):
      sno = db.Column(db.Integer, primary_key=True)
      name = db.Column(db.String(80), nullable=False)
      phone_num = db.Column(db.String(12), nullable=False)
      msg = db.Column(db.String(120), nullable=False)
      date = db.Column(db.String(12), nullable=True)
      email = db.Column(db.String(20), nullable=False)

   @app.route("/", methods = ['GET', 'POST'])
   def contact():
      if(request.method=='POST'):
        '''Add entry to the database'''
        name = request.form.get('name')
        email = request.form.get('email')
        phone = request.form.get('phone')
        message = request.form.get('message')
        entry = Contacts(name=name, phone_num = phone, msg = message, date= datetime.now(),email = email )
        db.session.add(entry)
        db.session.commit()
    return render_template('contact.html')


   app.run(debug=True)
   ```
## 10. Making Parameters Configurable in Flask:

1. We will configure the Paramerters using the config.json .
2. Firtsly we will create a config.json in the project directory.
3. In the json file we will implement the configurationa s follows:
   ```sh
   {
    "params": {
        "websitename": "Flask-Project"
    }
   }
   ```
4. In the main.py file we will import the json file as follows:
    ```sh
    import json
    with open('config.json', 'r') as c:
        params = json.load(c)["params"]
    ```
5. Now we can simply use the json file to pass the parameters as we pass the variables:
    ```sh
    params['websitename']
    ```
6. Passing the json file to html to implement the configuration:
    ```sh
    @app.route("/")
    def home():
        return render_template('index.html', params=params)
    ```
7. Implementing the json parameter in the HTML:
    ```sh
    <h1>{{params['websitename']}}</h1>
    ```
8. We can do the same for the links and any other variables that are needed:
    ```sh
    pip install Flask
    ```
9. In order to redirect the form data to the mail we can use te following code to so:
    ```py
    mail.send_message('New message from ' + name,
                          sender=email,
                          recipients = [params['gmail-user']],
                          body = message + "\n" + phone
                          )
    ```
    The above code is added to the if condition of the POST and GET class.



   
