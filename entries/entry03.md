# Entry 3
##### 2/21/2021

At this point I have completely setting up Firebase and started testing it in repl. Feel free to take a look at my [repl](https://repl.it/@ShenghaoDong/Testing-Firebase).
I do plan on moving my work to github in the near future when I'm done experimenting with more things. I will include the link to the github in future blog posts. 
My schedule for working on this project has been a mess and I hope to fix it and take neccesary steps to improve what I currently have.
I have too many ideas and I don't know where I should start or end and my goal is to make a plan regarding this issue. 

Currently I am in Step 4 of the Engineer Design Process. I want to make a website where I can track what I need to do daily in certain games since it gets hard when I'm trying to keep 
track of school work as well. The idea I have in mind currently is to allow the user to store information about what they have to do each day and be able to delete as well. If possible 
I also want to make templates for certain games to make this easier!

The tool I am currently using is Firebase and I plan to continue using this tool. The current feature I have been using is the [Realtime Database](https://firebase.google.com/docs/database).
This allows me to capture the users data in real time. When first starting Firebase, they provide you with a code snippet in the general section of Project Settings and the code should look
something like this:

```JS Snippet
<!-- The core Firebase JS SDK is always required and must be listed first -->
<script src="https://www.gstatic.com/firebasejs/8.2.9/firebase-app.js"></script>

<!-- TODO: Add SDKs for Firebase products that you want to use
     https://firebase.google.com/docs/web/setup#available-libraries -->
<script src="https://www.gstatic.com/firebasejs/8.2.9/firebase-analytics.js"></script>

<script>
  // Your web app's Firebase configuration
  // For Firebase JS SDK v7.20.0 and later, measurementId is optional
  var firebaseConfig = {
    apiKey: "AIzaSyBN8QJ1WXLM60mSdJL2LH2Fvdy0pnkPNXU",
    authDomain: "fir-test-731e2.firebaseapp.com",
    databaseURL: "https://fir-test-731e2.firebaseio.com",
    projectId: "fir-test-731e2",
    storageBucket: "fir-test-731e2.appspot.com",
    messagingSenderId: "505488697880",
    appId: "1:505488697880:web:66f4f512a5eee62f47316d",
    measurementId: "G-ENBHQ6JMS5"
  };
  // Initialize Firebase
  firebase.initializeApp(firebaseConfig);
  firebase.analytics();
</script>
```
Without this code Firebase will not be able to function. 

The skills I learned were **debugging** and **finding the solution**, when first starting firebase I watched a [video](https://www.youtube.com/watch?v=-UOkri_WNWQ) on how to take in data
from the user. This was my first experience with the tool and I wasn't very sure about how to start but the video's instructions were very clear. Upon completion I was awaited with a error
so I began to look for a solution. After looking at the comments I realized I needed another line of code for it to function and that code being:

```JS Snippet
<script src="https://www.gstatic.com/firebasejs/8.2.5/firebase-database.js"></script>
```
Without this it was not possible for me to access the database.
The video itself told me how to allow the user to input information into the database and with the help of some HTML it ended up working as intended.
```JS Snippet
function writeData(){
    firebase.database().ref("User").set({
    name: document.getElementById("nameField").value,
    age: document.getElementById("ageField").value
  });
}
```
This line of code calls the Firebase database and inserts the data of the user into the database. This code was accompanied by this HTML:
```HTML Snippet
<input type = "text" placeholder = "Name" id = "nameField">
<input type = "text" placeholder = "Age" id = "ageField">
<button onclick ="writeData()">Submit</button>
```
The HTML allowed users to input information in a box. In this case the website was asking for their name and age.

[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)