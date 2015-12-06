## GoogleHackFairID 2015 : Firebase Introduction

### Prerequisite :
* Installed `Node.js` and `npm` (Installed Node.js also installs npm)

### Setup :
* Install Firebase command line tools via npm :
	
		npm install -g firebase-tools

* Initialize firebase project with command :

		firebase init

	Fill everything in question (Firebase name must unique)

* If Firebase has initialized, you will get `firebase.json` and `directory public root`

### Working with Firebase project :
* Create `index.html` in your `directory public root`
* Intall Firebase JS library

		<script type="text/javascript" src='https://cdn.firebase.com/js/client/2.2.1/firebase.js'></script>

* Access your realtime database, your database reference should be `http://[projectname].firebaseio.com` witch this project like :

		var firebaseUrl = "https://arip-h.firebaseio.com";
		var myFirebase = new Firebase(firebaseUrl);

* Write data / object

		var myData = {
			username : "Arip Hidayat",
			message : "Hallo Firebase !",
			date : Date.now()
		};
	
		myFirebase.set(myData);

* Apply callback function (example) : 

		myFirebase.on('child_changed', function(snapshot) {
			console.log(snapshot.val());
		});