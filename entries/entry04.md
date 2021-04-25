# Entry 4
##### 4/25/2021

After beginning to work on my Project again, I realized that my Realtime Firebase Access had expired. To fix that I had to change the rules so that I could use the 
Realtime Database again. I'm currently still working on repl.it but I do plan on changing to github by the next time I make another entry. At this point in time
I have a goal in mind and I'm working towards it.

I am currently in Step 5 of the Engineer Design Process. I currently know my plan in the future, in this blog post I will be talking about how I created a login function for
the user. Next, I'm looking to allow the user to input and grab information and after that I play to make the User Interface better.

Last Time I talked about using the Realtime Database in order to get data and now I have tried the [Aucthenication Feature](https://firebase.google.com/docs/auth). 
This feature allows the user to login, currently I am only using the [google login](https://firebase.google.com/docs/auth/web/google-signin) but I have plans to add more options.
I ran into many errors while trying to Authenicate the User, and this [video](https://www.youtube.com/watch?v=Dbq6yr9XKX8)
helped me fix it. The problem was that my domain wasn't added to my Firebase yet. I found this out by using this code:
```catch Errors
.catch(e=>{
  console.log(e)
```
This code prints errors that occur when my code doesn't work and with this I found out that I needed to add my domain first. The video also helped me make a logout tool. 
To login using google first I had to set up a few things. First I had to add the code that allowed me to use the Authenticator:
```
 <script src="https://www.gstatic.com/firebasejs/8.2.5/firebase-auth.js"></script>
```
This line of code contains all the functions needed to use the authenicator. Then I had to add the Google Auth Provider since I am using google as the login tool.
```
var provider = new firebase.auth.GoogleAuthProvider();
```
The code above adds Google as a Authorization Provider which means users can now login using google. Then I made the login and logout.
Login:
```
function googleLogin(){
firebase.auth().signInWithPopup(provider);
};
```
Logout:
```
function logout(){
  firebase.auth().signOut();
};
```
I used a onclick function on a button in order to trigger the code. With the login you can also use signInWithRedirect but I decided to stick with a pop up for now.

The skills I used are **debugging** and **Learning from My Mistakes**. Last time I didn't put in the Realtime Database code so the database didn't work but this time
II learned from my mistakes and added the Authenization code. I also learned to debug when my code was printing out a error I had fixed it by adding my domain.

[Previous](entry03.md) | [Next](entry05.md)

[Home](../README.md)