---
id:card_edventuresapp
title:EdVentures App Integration
---

## Summary
In order to integrate with an EdVenturesApp service, you need to set up a firebase.json file in your top level `thorium` folder. 

First, you need to set up your firebase instance with the following collections:

1. Awards
2. AwayMissions
3. News
4. Page
5. Ranks
6. Roles
7. Simulators
8. Users

Best way to see what the setup for these collections are, is to look in the types specified [here](https://github.com/Thorium-Sim/thorium/blob/develop/server/classes/FirebaseManager.ts)

Naming conventions are that capitalized words are part of a document, and `id` is the document name. Example: FirebaseAwards -> `id` = id of the document, where `Name` is a field on that document. 

### Page

Because we wanted the page to be as generic as possible, you need to include the Page collection, which includes the logo of the app, as well as the text that will be shown on the user's card. It is broken up into the following documents. 

1. Logo -> src: string. This is the url of the app icon. You can have it be a url or base64 encoded. 
2. Text -> Awards, Email Heading, Email Not Found, Heading, Subheading: all strings. They make up the text on the page. If you don't have them, you won't have a page. 

### firebase.json

After you have your db set up, you should be ready to integrate. First you need to generate admin-service level credentials. 

Best way to do that is to follow the tutorial on the firebase website [here](https://firebase.google.com/docs/admin/setup#initialize_the_sdk_in_non-google_environments).

Once you have those, put the generated JSON into a file titled `firebase.json`, and insert that at the top level of your thorium folder. 

Restart the server, and you should see that you are now connected to EVA!