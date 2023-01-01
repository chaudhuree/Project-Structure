## Mern Folder Structure

1.  backend front end separate file -- loosey couple
2.  backend front end together

> **backend front end separate file**

frontend floder name **client-side**
backend floder name **server-side**

---- **_clean up file folder after create-react-app_**
src(folder) directory -->

    assets--> a.css(folder) b.img(folder)
    helper--> different codes
    components
    pages
    backEndServices--> backend api related codes
    app.js
    index.js

> backend -->

server-side(folder) directory -->
_run command in server-side_

```
	npm-init --y
	npm i express
```

then create this directory in server-side folder

    index.js
    app.js
    src(folder) -->
    	controller(folder)
    	helper(folder)
    	model(folder)
    	routes(folder)

> dependencies install for client :

```
npm i
react-bootstrap bootstrap
react-router-dom
axios
cogo-toast/react-tostify
momentjs
react-icon
sweetAlert2/react-bootstrap-sweetalert
cleavejs
recharts
localforage
react-code-input
react-excel-file
export-from-json
htmlparser
html-to-image
react tooltip
react window
```

> dependencies install for server

```
body-parser
cors
dotenv
express mongo sanitize
rate limit
helmet
hpp
jwt
nodemon
xss clean
mongoose
```

> **backend front end together**

mernstack(folder) -->
run this command

```
	npm init --y
	install necessary packages for backend
```

create this file folder below

    src(folder)
    	conroller(folder)
    	helper(folder)
    	router(folder)
    	model(folder)
    app.js
    index.js
    client(folder)=>
    run this command in client folder cd client
    npx create-react-app .
    install necessary packages (up)
    	src(folder) directory-->
    		assets(folder)--> a.css(folder) b.img(folder)
    		helper(folder)--> different codes
    		component(folder)
    		page(folder)
    		app.js
    		index.js

🌟🌟combine font end and backend together

```
cd client
	npm run build
```

client(folder) ==> package.json--> add this line
```
"proxy": "http://localhost:5000"
```

now for server side==>
in app.js before backend routing add this line,

    	//Database
    		connect database
    		mongoose.connect related codes....

    	// Managing Front End Routing
    	app.use(express.static('client/build'))
    	app.get("*",function (req,res){

req.sendFile(path.resolve(\_\_dirname, 'client', 'build', 'index.html'))
})

    	// Managing BackEnd API Routing
    	app.use("/api/v1",router)
