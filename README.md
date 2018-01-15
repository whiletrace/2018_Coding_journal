# 2018_Coding_Journal
A repository coding journal to keep track of my coding, learning, and progress throughout the year of 2018 and beyond.

<strong>01/08/2018 ES2015 review </strong> </br>
starting the year with some treehouse review of ES2015 review I have been using ES2015 in my code for sometime however feel its important to start the year somewhere, also its a module I have to finish in the Fullstack Javascript track so I started with let and const. I'll finish the module and post some musings into a repository in the morning. 

<strong>01/09/2018 Project Work pair programming </strong> </br>
Worked this evening doing a bit of pair programming with a mentor revisited a long ignored project you can see changes in the commit here [Todo_React_Redux](https://github.com/whiletrace/Todo_Redux_React/tree/api) Through some debugging we were able to fix a breaking error, in my logging module. the issue concerned variable scope. Current fix is that I moved the variable that held the value of the filepath for the logs to the Outer scope where the codebase that handles log creation and sync could access the variable. project needs refactor for a more elegant solution, as well as fix linting errors, finish crud models, and controlers and write tests are next steps.

<strong>01/14/2018 Project </strong> </br>
Today I finished writing the remaining crud models for the api and begain the controller logic in the routes, I am having some challenges, I am able to connect to the database, I am able to output the dummy data from the db to the console, however there is an issue currently between my  models and controller that interfaces with that model, The route works, and I can get a json object from the route when tested in Postman, however its outputting an empty object. I will wait until I get data outputting from the controllers properly before I commit current changes.
