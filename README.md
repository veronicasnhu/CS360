# CS360: Android Weight Tracking App

Developed for SNHU CS 360 using Java, XML, SQLite, multiple activities, progress tracking, weight history, and optional SMS goal notifications.

## Briefly summarize the requirements and goals of the app you developed. What user needs was this app designed to address?

For this project, I developed a weight tracking app that lets users create an account, set a goal weight, log their weight, monitor their progress, and review previous entries. The main goal was to give users a simple way to keep their weight information organized without adding a lot of unrelated health or fitness features.

I wanted the user to be able to open the app and quickly understand where they currently stand and what they need to do next. The app saves account information, goal settings, SMS settings, and weight entries so users do not lose their information when the app is closed. I also included an optional SMS notification that can alert the user when they reach their goal weight.

## What screens and features were necessary to support user needs and produce a user centered UI for the app? How did your UI designs keep users in mind? Why were your designs successful?

The final app includes a Login screen, Home screen, Weight History screen, and SMS Settings screen. Each screen has a specific purpose instead of trying to fit every feature into one layout.

The Home screen changed the most throughout the design process. I reorganized it so the information a user would probably want to see first is easier to find. The final Home screen shows the current weight, progress toward the goal, a place to log a new weight, and the goal settings. I also added a recent entries option so users can quickly check their latest weights without opening the full history every time.

The progress section was also made more useful by showing the progress percentage and a written update instead of relying only on a progress bar. The Weight History screen gives users a complete view of their saved entries in a grid and lets them add, edit, or delete individual records.

I kept the layout and navigation simple by using clear labels, familiar controls, and separate sections for related information. I think the design was successful because users can see the most important information quickly while still having access to more detailed history and settings when they need them.

## How did you approach the process of coding your app? What techniques or strategies did you use? How could those techniques or strategies be applied in the future?

I approached the coding process by getting one part of the app working before moving on to the next. I started with account creation and login, then connected the other activities using intents. I passed the logged in user ID between activities so each screen could work with the correct user and their saved information.

I used SQLite to store user accounts, goal weights, SMS settings, and weight entries. I created separate database methods for the actions the app needed, such as adding a weight, getting the latest weight, updating an entry, deleting an entry, and loading the full history. This made it easier to connect each button or action in the interface to the correct database operation.

Working one feature at a time made troubleshooting much easier. If something stopped working, I could usually trace it back to the part I had just changed instead of trying to search through the entire project. I would use the same approach again because it gives me a clearer way to build larger applications without losing track of how the different parts connect.

## How did you test to ensure your code was functional? Why is this process important, and what did it reveal?

I tested the app throughout development using the Android Emulator instead of waiting until everything was finished. I tested both new account creation and existing account login, then closed and reopened the app to make sure the saved information was still available.

I also tested setting and changing the goal weight, logging new weights, editing and deleting entries, viewing recent entries, and checking the full Weight History grid. After making changes in Weight History, I returned to the Home screen to make sure the current weight and progress information updated correctly.

The SMS feature needed its own testing because the app has to respond differently depending on the user’s permission choice. I tested the feature with permission granted and confirmed that the goal notification was triggered. I also denied the permission and made sure the rest of the app continued working normally.

Testing was important because some problems only became obvious when I actually moved through the app like a user. A screen could look correct on its own but still have a problem when data was changed somewhere else in the app.

## Consider the full app design and development process from initial planning to finalization. Where did you have to innovate to overcome a challenge?

One of the bigger challenges was keeping information consistent between the Home and Weight History screens. A user can add or edit a weight from Weight History, but the Home screen still needs to show the correct current weight and recalculate progress when the user returns. I handled this by reloading the saved information when the Home screen becomes active again instead of continuing to display values that may have changed.

The SMS feature also took more troubleshooting than I expected. I originally had the goal notification working when a weight was logged from the Home screen, but then realized a user could also reach their goal by adding a weight through Weight History. I had to make sure both paths used the same goal logic and triggered the notification correctly.

That was a good example of how the app changed from separate screens into one complete application. The individual features were working, but I still had to think about how an action on one screen affected the rest of the app.

## In what specific component of your mobile app were you particularly successful in demonstrating your knowledge, skills, and experience?

I think I was most successful with the database portion of the app and how it connects the different screens together. The database stores the user account, goal weight, SMS settings, and weight history, so most of the app depends on that information being saved and retrieved correctly.

Users can create, view, edit, and delete weight records, and those changes are reflected throughout the application. The Home screen uses the saved data to show the current weight and calculate progress, while the Weight History screen uses the same data to display and manage the full list of entries.

This part of the project brought together a lot of what I learned in CS 360. I used multiple activities and intents, XML layouts and Android widgets, persistent data with SQLite, user input, runtime permissions, and emulator testing in one working application. Seeing those pieces work together was the strongest part of the project for me.
