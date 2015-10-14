#Project setup
This document explains how to get set up if you need to do some work on a project.

###Getting the files
The following steps need to be taken in order to pull down all the required files from the git repository:
- Clone the repository to your machine
- If you've already cloned, ensure you've pulled down all changes

###Navigate to the project directory
- Navigate to the project directory by typing the following onto the command line: `cd `, followed by the directory path of the project you're working on. 
- This can be done quickly by typing `cd `, and then by dragging the directory into terminal to automatically insert the directory path.

>####WINDOWS USERS
You will need to install git for some of the following processes, this is available to download and install from [here](https://git-scm.com/download/win)

###Using NPM/Bower

>####WINDOWS USERS
>The next stage requires Node.js to be installed, as it doesn't come as standard with Windows. If you're not sure whether it's installed, type `node -v` onto the command line. If you get a version number back, this confirms Node.js is installed. A good guide can be found [here](http://blog.teamtreehouse.com/install-node-js-npm-windows).
>
>Python will also need to be installed as this doesn't come as standard. If you're not sure whether it's installed, type `pythonquit()` onto the command line. If you get an error back, this confirms python is **not** installed. This can be downloaded from [here](http://www.python.org/downloads/). **You must download version 2.7.10, as 3.5 will not work**. You **must** check the box which reads `add python.exe to PATH`. This allows you to run python commands from the command line.
>

In order to install/update the plugins required to process all files, the following commands need to be run:

- Type the following into terminal/command prompt: `npm install`. This installs/updates all project dependencies listed inside `package.json`. This creates a `node_modules` directory.

- Now type `npm install bower`. Bower is a framework manager used to make sure all 3rd party libraries and frameworks are up to date.

- Now that bower's installed, you *may* need to bower as a system environment variable in order to run bower commands from the command line. This can be done by typing `npm config get prefix`. Now copy the result and go to the following: Control Panel > search for 'environment' > Edit environment variables for your account > Paste the result into the 'PATH' variable.

- Type the following into terminal/command prompt: `bower install`.  The necessary libraries (with versions) are kept inside `bower.json`. This creates a `bower_components` directory.

- Finally, Type the following into terminal/command prompt:`npm install -g grunt-cli`. This is the grunt command line interface which is required to use grunt.

###Grunt
From the command line, type `grunt`. This will run a series of tasks which will process/concatenate/minify all necessary files in the repository. The tasks are logged inside `Gruntfile.js`. Once grunt has finished, the last line you will see on the command line is `Waiting...`. This shows that grunt is listening for changes. Any changes made inside the project which require compilation/minification/copying/processing will be heard by grunt and the necessary tasks carried out.

###Running a local server
`Gruntfile.js` creates a `dist` (distribution) directory, and only the files necessary for production are moved into here. The project can be previewed by firing up a local server.

- Open a new terminal command prompt windown and navigate to the `dist` directory by typing the following onto the command line: `cd`, then a space, then the directory path of the project you're working on, followed by `/dist`.  
- For example, `cd Users/developer/Projects/ACCA-X/dist`
- Then type `python -m SimpleHTTPServer` to fire up a server from the above directory. The default port is `8000`, but this can be changed by adding a space followed by a different number.
- Go to a browser and navigate to `http://localhost:8000/`. Providing there's an index file at the root of `dist`, you'll be able to preview the project from here.

###Things to note
- Files should only be updated inside the `dev` directory, as the `dist` directory is rebuilt each time the grunt process runs.
- `Gruntfile.js` is configured so that any connected html files will automatically refresh on save of a scss/js file - provided that the LiveReload plugin has been added as an extension to your browser.