<a  href="https://pingback.com/"><p  align="center"><img  src="https://media-exp1.licdn.com/dms/image/C4E16AQHrluCFxvATBQ/profile-displaybackgroundimage-shrink_350_1400/0/1623436459015?e=1648080000&v=beta&t=4qNa36w_JoJyNVAL7uAba6zonkJiJwy3-fYfWAm8hCo"></p></a>


# Nodejs Challenge

  Hey, thanks for your interest in working with us. Before we continue your application we need to check if you can handle some skills.
  We know that's boring and it sucks, but it allows us to create a team that really can collaborate. 
  
  So if you are here, we need to check some of your skills ok? Let's do It!

# What are we looking for?

First, we need you to know that you have a domain of Javascript and Nodejs. It's important to remember that our entire culture is based on Clean Code, so, be aware that we will expect that your code is well written and well documented, ok?
  
   You must use Nodejs 12+ for this challenge. You are not allowed to use Nextjs as a framework. 
   
   - ** Database **
    You must use MongoDb or Postgres (Postgres is better) with some ORM.
    
   - ** Docker - Not Required **
     It would be great if you use Docker and Docker-compose for running your application. 
     Docker-compose should contain the build of the application and the DB.
     
   - **Tests**
      You must implement some tests in your application. Those tests should run when the command ```npm test``` is prompted. We recommend you to use jest. (Be free to use whatever you like).
      
# Your Goal

 **TTS API**</br>
Your goal is to build a simple API that will provide CRUD for a Post object. The user should be able to create an object that holds: title, sub-title and text. And then should be able to read, update or delete this object. The user should also be able to get the text as audio. (The application must request an external API to transform text in audio, store the audio file, and if requested return the audio).

The application must have a simple authentication system.

We want to see how you structure your code and the solutions you use to each challenge you will face.

# External API

 For converting text to audio (TTS) you must use https://www.voicerss.org/ API. Be aware that the documentation for using this API is provided in the link and that you should create a free account to receive an API key to use it. (Please, do not share your API key with us, create an env variable named TTS_KEY that will hold the key, we are going to use our individual key in tests).
 
 # Routes
 
 Your Api should have at least the following Routes:
 
  - ```POST /user/``` -> Create user
  - ```GET /users/``` -> Get all users (only for users that are admin)
  - ```EDIT /user/:id/``` -> Edit user, only the user itself use this route

  - ```POST /text/``` -> Create a text object
  - ```PUT /text/:id/``` -> Edit a text object
  - ```GET /text/:id/``` -> Get text object
  - ```GET /user/:id/texts/``` -> Get all text objects from an given user
  - ```DELETE /text/:id/``` -> Delete text object

  - ```POST /text/:id/audio/``` -> Request TTS
  - ```GET /text/:id/audio/``` -> Get the audio file if its already converted, if its not it must run POST method.
  - ```PUT /text/:id/audio/``` -> Force new TTS conversion

# Entities

 Your application must have at least the following entities:
 
 ```
 |--------- Users ---------|
 | ID: UUIDV4              |
 | NAME: STRING            |
 | EMAIL: STRING           |
 | PSW: STRING             | 
 | ISADMIN: BOOLEAN        |
 |-------------------------|
 ```
 ```
 |--------- Posts ----------|
 | ID: UUIDV4               |
 | TITLE: STRING            |
 | SUBTITLE: STRING         |
 | TEXT: TEXT(255)          |
 | USERID: REFERENCE(UUIDV4)|
 |--------------------------|
 ```
 ```
 |--------- Audios ---------|
 | ID: UUIDV4               |
 | URL: STRING              |
 | POSTID: REFERENCE(UUIDV4)|
 | USERID: REFERENCE(UUIDV4)|
 |--------------------------|
 ```
 All entities must have CREATEDAT(DATE) and UPDATEDAT(DATE) as attributes. 
 
# Web Interface
 
  It's not required to build a front-end interface for the purposes of this test. It will be well received if you deliver some web interface, though.
  
# How to apply your code
  When your task is done please create a repo inside your Github account, this repo must be public. Send the repo URL via e-mail to tech@getpingback.com.
  
# How your code will be reviewed.
 
  The application should run with npm run server command or docker-compose up --build command. TTS_KEY shoud be an env file so we can use our key.
  
  The application code will be reviewed keeping the following criterias:

 - Functionality
 - Project Structure
 - Maintainability
 - Use of best practices
 - Domain of Javascript

--- 
© 2021 Pingback International. Please do not share or use this test without Pingback's permission. This work is protected by copyrights held by Pingback International. The project can't be duplicated or used (even small parts of it) without the prior consent of Pingback International.

