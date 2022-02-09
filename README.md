# http-and-db-emulation

This is to demonstrate how the express server handles http requests from users, and then accessing json files on the server to emulate accessing data on a database.

To get this project running locally, first, have these installed:
- node.js (check the website for info if not yet installed)
- express (run the code below once node is installed)
- nodemon (optional; having this makes development easier)

## Installing express via node package manager (npm) and using express

Once you have verified that node is installed, run this:

```
npm install express -g
```

Note: The -g flag is to install express globally / system-wide

```
express --no-view simple-db-emulation
```

This runs the express engine which generates everything that makes up a barebone express app.<br>

Notes: <br>

The --no-view flag is to generate the app without a view engine<br>
simple-db-emulation is just the name of the app in this case. It can be anything <br>

## cd & npm install

Now switch to the new directory created i.e. the name of the app, and install the dependencies required to run the app. E.g.

```
cd simple-db-emulation
npm install
```

OPTIONAL: also install nodemon and add codes specified further below to the package.json.

<br>

What nodemon does is is automatically relods the server everytime any file with the expensions specied in the -e flag is saved, so we don't have to kill and rerun the process manually.

```
npm install nodemon
```

After successful installation, open your package.json, locate these lines (initially it won't contain "dev": "...):

```javascript
"scripts": {
    "start": "node ./bin/www", //Add a comma at the end of this line
    "dev": "nodemon -e html,js,css ./bin/www" //Add this entire line
  },
```

Note: Remove the comments. Comments aren't allowed in .json files
<br>
Now save the file and test the app by running:

```
npm run dev
```

The above code runs the dev script specified in package.json
<br>
To run without nodemon (not recommended):

```
npm start
```

## app.listen()

Now, go to the app.js file and at the end of it but before "module.exports == app", add this:

```javascript
app.listen(8080, ()=>{
    console.log("listeniing at port:8080")
})
```

Save the file. The string "listening at port:8080" will appear on the console.

<br>

Now you can open up a browser and load http://localhost:8080

<br>

The index.html file in public folder will be served and rendered