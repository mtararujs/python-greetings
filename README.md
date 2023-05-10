# python-greetings
Really simple pythong application for study purposes and usage of it in CI/CD pipelines. 

To start and use this application:

1. Install the required package using `pip install -r requirements.txt
`
2. Open a terminal or command prompt in the directory where app.py is located
Start the application by running `pm2 start app.py --name myapp -- --port <port_number>`, replacing `<port_number>` with the port number you want to run the server on and `myapp` with a name of your choice for the process.
3. Open a web browser or a tool like curl and visit `http://localhost:<port_number>/greetings`, replacing `<port_number>` with the same port number specified when starting the application. You should see a JSON response like {"greeting": "Hello from Python App!"}.
