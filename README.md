Hacknight
=========

Talk for Illini Hackers Hacknight #02. 

We're going to learn how to pull images from Instagram and make a timeline with them.

###Instructions:
These are kind of long. Try to bear with me!

- Go to http://www.instagram.com/developer/

- Register a new application by clicking on "Register a new Application"

- You should now see a page that says, "Manage Client". Go ahead and click on "Register a new Client"

- Give your application a name and description. Fill in the *website* and *OAuth redirect_url* field with **http://localhost/**

- "Disable implicit OAuth" will be checked by default. **Uncheck it.** This is what will let us pull images from Instagram without actually logging in to the service.

- Finish up by filling in the Captcha and clicking on "Register". You should now be redirected to a page where your registered clients are displayed, along with their Client ID and Client Secret.

- Modify the following link so that CLIENT-ID and REDIRECT-URI are replaced with your client ID and redirect URI:  https://instagram.com/oauth/authorize/?client_id=CLIENT-ID&redirect-uri=REDIRECT-URI&response_type=token
By the  end of it, you should have something like this - https://instagram.com/oauth/authorize/?client_id=74c005533c7c4b959a51b&redirect-uri=http://localhost&response_type=token

- Copy the link with your client ID, paste it into your browser and hit enter. It'll show you something like this - http://i.imgur.com/rPzMOeO.png

- Click on "Authorize", and you should be redirected. Pay attention to the URL! You'll see something like this - http://i.imgur.com/fJrYrIY.png

- SAVE THAT URL! At least the part after 'access_token='. You'll need it later for making requests to the Instagram API.

####Woot! You can now ask Instagram for images. Let's do a quick rundown on how we're going to do this...
We're going to send Instagram a GET request with some parameters – Your access token, and other ones like _tag_, _user_, _media type_, _recent_ and so on. We're going to do this with JavaScript, and when Instagram's API responds with the data, we parse it and append it to our page. Then comes the fun part - CSS!

