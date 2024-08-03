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
    a. " render_template " command is used to import the templates.
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
    
