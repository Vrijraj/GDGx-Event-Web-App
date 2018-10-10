# GDG[x] Event Web App
<p align="center">
<img width="800px" src="https://devfest18-jalandhar.firebaseapp.com/assets/img/brand.jpg">
</p>
Standard Web App for GDG[X] Event. <br>
[Demo](https://devfest18-test.firebaseapp.com) <br>
Version: 1.0.2

## Overview

GDG[X] Event Web App is the conference website template that helps you to set conference website with registration, speakers and schedule management in a few minutes.

The template is created by [GDG Jalandhar](https://meetup.com/GDG-Jalandhar/) team experience of running meetups.

## Features
| Feature | Description |
|---|---|
| **Fast and optimized** | 100/100 PWA on Lighthouse |
| **Works offline** | Can works offline |
| **Mobile first** | Mobo Friendly Web app can be installed as a native app on your phone |
| **SEO optimized** | Index all content and get to the top in search results |
| **Speakers and schedule management** | Keep and update all information in the JSON File |
| **Registration** | Attendees can register for the event using Firebase Realtime Database |


## Getting Started
1. [Fork repository](https://github.com/Vrijraj/gdgx-event-web-app/fork) and clone it locally
2. Setup Environment
   * Install Firebase CLI: `npm i -g firebase-tools` or `yarn global add firebase-tools`
3. Create [Firebase account](https://console.firebase.google.com) and login into [Firebase CLI](https://firebase.google.com/docs/cli/): `firebase login`
4. Create a new Directory in your Local Machine.
5. Open Terminal/CMD/Powershell in your dir.
6. Now type `firebase login` command in your Terminal/CMD/Powershell. 
7. Type `firebase init`.
8. Select the project by using the arrow keys.
9. Then Select the `Firebase Hosting` by using Spacebar and arrow key.
10. Click `No` for Single page web app.
11. Type `Public`.
12. Some by default file will be created successfully.
13. Move the cloned source file in `public` dir.
14. Update [Firebase Web Setup & Basic Info](/index.html), [Venue Map](/views/attending.html), [manifest.json](/manifest.json) and [Resources](/data)
15. Update Firebase.json file
    ```js 
    {
      "hosting": {
        "public": "public",
        "rewrites": [ {
          "source": "**",
          "destination": "/index.html"
        } ],
        "ignore": [
          "firebase.json",
          "**/.*",
          "**/node_modules/**"
        ]
      }
    }
    ```
16. Update the Firebase Real-Time Database Rules
    ```js
      {
        "rules": {
          "data": {
            "$uid": {
              ".write":"$uid === auth.uid",
              ".read": "$uid === auth.uid"
            },

          }
        }
      }
    ```
17. Enable the `Google SignIn` provider in `Firebase Auth`.
18. Run locally
   * `firebase serve` or `npm run serve` or `yarn serve` 
19. Build and deploy
   * `firebase deploy` or `npm run deploy` or `yarn deploy`


## Technology Stack

* [AngularJS](http://angularjs.org/)
* [Bootstrap](http://getbootstrap.com/)
* [Firebase](http://angularjs.org/)
* [Service Worker & PWA](https://pwafire.org/)
* [Material Design Bootstrap](https://mdbootstrap.com/)

### View Website Built with Project 

| Community Name | Event Name | Web App Link | 
| --- | --- | --- | 
| GDG Jalandhar | GDG DevFest'18 | [View Now](https://devfest.gdgjalandhar.com) |





Project is published under the [MIT license](/LICENSE.md).  
Feel free to clone and modify repo as you want, but don't forget to add reference to authors :)
