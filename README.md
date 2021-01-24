# GoodReadsGraph
## Build a Graph Database of Good Reads book data to recommend novel novels to users:
### In the screenshot below, I entered _Neuromancer_ and got Ann Leckie's _Ancillary Mercy_. 
![](https://github.com/franckjay/GoodReadsGraph/blob/master/ReactApp/src/ReactApp.png)


### To run back-end:
* Activate your virtual environment in a python terminal
* Start flask server:
* `$ export FLASK_APP=api` 
* `$ flask run`
* Should be running on `localhost:5000`. You can test your API with `Postman`

### To run front-end (first-time only) in a new terminal:
No idea if there is a better way to do this, but:
* Follow Node installation instructions [here]("https://www.youtube.com/watch?v=06pWsB_hoD4&t=233s")
* Build a new React app folder (_do not call it_ `ReactApp/`):
* `$ npx create-react-app {FOO}`
* `$ npm start`
* This will start the app with all of the basic components needed
* The React App should show up on localhost:3000
* Copy+Replace all of the files in `ReactApp/` to your `{FOO}/` directory (e.g., `App.js`, `components/`)

### If you already did the first-time front-end build:
* `$ npm start`
* Anytime you edit/save any files inside the directory, the App on the local host will update
* Need to debug? Right click on your apps web page: `Inspect -> Console Tab` will show you what is up


TODO: Add a conda environment `.yml` file for the Flask dependencies

-------------------------------------------------------------------------

How to run\
<u>Terminal 1</u>\
The following steps are required only once after you have checked out the code.\
$ npx create-react-app gwr

Copy all the files from the ReactApp folder and paste them in gwr folder

<u>Terminal 2</u>
$ export FLASK_APP=api
$ flask run

Let the flask app complete building the graph and be ready to serve web requests. That is, wait until you see the following line at the prompt:\
\* Running on htpp://127.0.0.1:5000/ (Press CTRL+C to quit)

Then, go to Terminal 1

<u>Terminal 1</u>
$ cd gwr
$ npm start

Errors:
1. ./src/index.js\
Module not found: Can't resolve 'semantic-ui-css/semantic.min.css'\
Solution:\
$ yarn add semantic-ui-css

2. Error: [BABEL] /mnt/e/Code/Python/Flask Applications/GoodReadsGraph/gwr/src/index.js: Cannot find module '@babel/helper-builder-react-jsx'
Solution:\
$ yarn add @babel/helper-builder-react-jsx

3. return jsonify({"image_url": ouput_URL}), 200\
NameError: name 'ouput_URL' is not defined\
Solution:\
api/app.py\
Line 58: change ouput_URL to output_URL\
Make the same change in lines 46 and 47.

For some reason, the book recommendation does not appear unless you refresh the page.\
That is, Enter 'Neuromancer' in the input text field and click Add.\
In the text field, you will see 'We found your favorite book!'.\
Then, refresh the webpage (F5 or Ctrl-R) and the recommended book will appear below the Add button.
