---
datePublished: '2017-03-23T15:15:22.832Z'
sourcePath: _posts/2016-12-06-becoming-a-developer-on-google-play-tips-tricks-things-y.md
inFeed: true
hasPage: true
author: []
via: {}
dateModified: '2017-03-23T15:15:22.504Z'
title: 'Becoming a Developer on Google Play - Tips, Tricks, Things You Need!'
publisher: {}
description: >-
  I recently became a developer on Google Play because I want to sell my games.
  Now, although my games are far from complete, they offer a glimpse of what
  could be possible in the future as I continue developing. Read on to learn
  about my experience so far and some tips for any aspiring developers who know
  what to expect.
starred: false
datePublishedOriginal: '2016-12-19T15:23:55.059Z'
url: becoming-a-developer-on-google-play-tips-tricks-things-y/index.html
_type: Article

---
# Becoming a Developer on Google Play - Tips, Tricks, Things You Need!

I recently became a developer on Google Play because I want to sell my games. Now, although my games are far from complete, they offer a glimpse of what could be possible in the future as I continue developing. Read on to learn about my experience so far and some tips for any aspiring developers who know what to expect.

---

To date, this project has cost me around £100 so far. I started a long time ago when I was a student (studying something unrelated), to program in Adobe Flash, actually, long ago enough that it was called Macromedia Flash. At first of course, you start with the basics: get some sort of interactivity to happen on your screen! \[requires adobe flash to view\]

[My First Flash Game][0]

You have to start at the start. Coding in basic on the Sinclair ZX Spectrum 48k when I was a child helped me connect with the high level languages used in Flash.

Next I thought I would need to figure out how to work with the numbers, so made this: \[requires adobe flash to view\]

[My Flash Calculator][1]

This helped understand how to code arithmetic and using "if else" statements to check if the user had chosen an operator such as add, subtract, etc.

A bit of experience in the bag, I started a project from scratch and after many hours I had a working experience system commonly found in RPG games: \[requires adobe flash to view\]

[My Flash Experience Calculator][2]

Lots of interactive buttons and editable text fields to see how your growing experience as a player affects your attributes. Adding stat points to your traits directly affects your overall character statistics, even showing you which traits like LUK and STR affect which traits like Health or Evasion.

That done, I took a hiatus from developing for several years, as I saw the phasing out of Flash as a platform and the introduction of html5\. This was a bit of a blow, since much time spent learning is really down to figuring out the software you work with, so I was going to have to explore different solutions.

Some random time later, I decided to try Construct 2, as the way you build your program has remarkable similarities to Flash. In fact, they make it even easier, so I was developing in no time at all. I bought a license to Construct 2 and started really getting in to it.

Since I have a couple of alpha games in development, I decided to become a developer on Google Play, with a view to actually seeing a financial return on my hobby at some point. Now this is where things start to get interesting.  
Once you have signed up as a Developer, you are invited to simply upload your "apk" file and then a few assets like pictures and descriptions afterwards.  
You can start closed or open alpha and beta testing versions, and invite testers to try out your latest offerings.

## First major problems to overcome: Creating a signing key for your app and "zipaligning" your app using zipalign.

Google play will simply not allow you to upload an unkeyed apk. In Construct 2, you can export your app to "Cordova" platform, which then allows you to upload a .zip of those files to a free apk creator (My favourite being Cocoon.io). You will then have the option of adding a key for the project you have uploaded to Cocoon. The question is, how do you create this fabled key?  
I struggled for some time with this, but there is help out there. I am going to offer my own step by step, as some of the instructions online simply are not crystal clear enough for such a bespoke operation. What we will be doing here is first generating a .jks key file, then applying that as a key to our Cocoon.io project so that we can generate and download a signed apk of our app.

First, make sure you have Java installed. Get it [here][3]

Now, you must also have installed the [Google Android SDK][4]

Next, because of a bug, you are going to have to manually find the "zipalign" exe that was installed with Android SDK. Try searching zipalign in your file explorer, after you have entered your Username Folder (C:\\Users\\You) for example.

Once found, copy that file and paste it into the Android SDK installation folder, default location is C:\\Program Files\\Android\\Android Studio\\

Now we have easy access to that zipalign process, we can access it through the console later on.

Ok, first we create a .jks key file using command line:

1. Bring up your task manager.
2. File\>Run new task
3. Tick "Create this task with administrative privileges"
4. Enter "cmd" (without the "")
5. In the new console window (usually black), enter the following: **cd C:\\Program Files\\Java\\jre1.8.0\_91\\bin**
  * If that path doesn't exist, you need to find your java install path. Enter this: **java -verbose**
  * A long list of logged actions appears. Look at the first few to get an idea of where your java installation is. Single out, select and copy the path, which will look something like: \[Loaded java.util.ResourceBundle$1 from_**C:\\Program Files\\Java\\jre1.8.0\_91\\**_lib\\rt.jar\]\[Loaded java.util.ResourceBundle$1 from C:\\Program Files\\Java\\jre1.8.0\_91\\lib\\rt.jar\]
  * Look at that Bold area, you just grabbed your install path! Just add "bin\\" on to the end of that path and you are good to go.
  * The final command you enter in to the console should look like this (the install path may look a bit different): _**cd C:\\Program Files\\Java\\jre1.8.0\_91\\bin\\**_
6. Having done this, your operating directory will change. Now you can access the java features you need to create your fabled .jks file.
7. Enter this command: **keytool -genkey -v -keystore my-release-key.jks -keyalg RSA -keysize 2048 -validity 10000 -alias app**
8. Follow the instructions carefully. Everything you are asked for is up to you to enter correctly and all you need to do is dream up the credentials it asks for. Take a note pad and write down your chosen credentials for this as you will need them later.
9. The console will ask you to confirm correct details. If you see \[Storing my-release-key.jks\] then you have been successful.
10. Log in to Cocoon.io and click on your project settings button
![Cocoon settings button](https://the-grid-user-content.s3-us-west-2.amazonaws.com/53993ebe-d5c2-4815-a86a-294d124bcb45.jpg)

1. On the next page, further down you will spot the "Signing" menu. Click Android in our case, and choose "Add a key..." from the drop down list.
2. You are presented with fields to enter the credentials that allow Cocoon to access your generated .jks license key file. Refer to your notepad notes if you forgot the credentials you entered back on step 8\.
3. Choose your my-release-key.jks file (probably inside your java directory unless you specified another address in the command line back on step 7\. Click ADD.
4. On the next page, further down you will spot the "Signing" menu. Click Android in our case, and choose "Add a key..." from the drop down list.
5. You are presented with fields to enter the credentials that allow Cocoon to access your generated .jks license key file. Refer to your notepad notes if you forgot the credentials you entered back on step 8\.
6. Choose your my-release-key.jks file (probably inside your java directory unless you specified another address in the command line back on step 7\. Click ADD.
![](https://s3-us-west-2.amazonaws.com/the-grid-img/p/fdd11dd63a1d0ff08999e22515467a3dd68a6835.jpg)

1. Once that has uploaded, go back to the top of the page and press the Compile button.
![yours app into an apk installer for Google Play and Android](https://the-grid-user-content.s3-us-west-2.amazonaws.com/8d1f8194-3aa0-4cab-a4e6-60dbd1e00258.jpg)

1. Cocoon will begin compiling your apk file using the jks key to sign it. You can twiddle your thumbs for a minute.
![Zipalign and then upload to Google Play](https://the-grid-user-content.s3-us-west-2.amazonaws.com/77c454fa-d38e-4299-b350-2cccf8eb4525.jpg)

1. Once it is done, you can just click the Android bot to download your apk. It will come in a zipped file.
![Next step will be zipaligning](https://the-grid-user-content.s3-us-west-2.amazonaws.com/d63cf0f7-2e42-42bb-a5dd-fbe4d5387284.jpg)

### If you need to Zipalign your file:

You'll know if you need to zipalign your apk file, because Google Play Developer Console will give you an error code after you upload your apk file to them. The error will be " You uploaded an APK that is not zip aligned. You will need to run a zip align tool on your APK and upload it again."  
So, let's do it.

1. Bring up your task manager.
2. File\>Run new task
3. Tick "Create this task with administrative privileges"
4. Enter "cmd" (without the "")
5. Working in the console window again, change your working directory with this command: **cd C:\\Program Files\\Android\\Android Studio\\**
6. Now, we need to execute the zipalign command, telling the process where our target apk is, and where we want it to put the new zipaligned file. First let me give an example, then I will explain which parts you need to change.
  * zipalign -v 4 C:\\Users\\Me\\Desktop\\Game\\android-release.apk C:\\Users\\Me\\Desktop\\Game\\android-release-ready.apkWhat is going on here is that we are telling zipalign to -v verbose (log all output) in 4 byte mode (32bit) the target apk that we want to zipalign (copy the path to your apk) and where to put the finished zipaligned apk (choose a file path and filename for your apk so you can easily find it.)
7. Hitting enter after you correctly pointed zipalign to your apk will start zipalign and show you the log of progress as it completes.
  * If you get an error, your path to zipalign may be wrong. Check back to the top of this article to see if you installed Android SDK and located the zipalign executable properly. You may also have entered a target path for your apk that does not exist. Double check everything.
8. All being well, you now have a zipaligned apk to upload to Google Play Developer Console.

There were other potential issues that were easier to overcome, I may cover those in a separate article.  
Thanks for reading! I hope this helped, and please leave feedback if you can.
[PJCS on Facebook][5]

[0]: http://www.phillipjohnson.org.uk/firstflashgame/htmlver.html "My first flash game"
[1]: http://www.phillipjohnson.org.uk/firstflashcalculator/htmlver.html "Flash Calculator by Phillip Johnson"
[2]: http://www.phillipjohnson.org.uk/flashexperiencecalculator/htmlver.html "Flash Experience Calculator by Phillip Johnson"
[3]: https://www.java.com/en/ "Here"
[4]: https://developer.android.com/studio/index.html "Android SDK"
[5]: https://www.facebook.com/PhillipJohnsonConsultancy/