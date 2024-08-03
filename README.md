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
    
