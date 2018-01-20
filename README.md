# 2018_Coding_Journal
A repository coding journal to keep track of my coding, learning, and progress throughout the year of 2018 and beyond.

<strong>01/08/2018 ES2015 review </strong> </br>
starting the year with some treehouse review of ES2015 review I have been using ES2015 in my code for sometime however feel its important to start the year somewhere, also its a module I have to finish in the Fullstack Javascript track so I started with let and const. I'll finish the module and post some musings into a repository in the morning. 

<strong>01/09/2018 Project Work pair programming </strong> </br>
Worked this evening doing a bit of pair programming with a mentor revisited a long ignored project you can see changes in the commit here [Todo_React_Redux](https://github.com/whiletrace/Todo_Redux_React/tree/api) Through some debugging we were able to fix a breaking error, in my logging module. the issue concerned variable scope. Current fix is that I moved the variable that held the value of the filepath for the logs to the Outer scope where the codebase that handles log creation and sync could access the variable. project needs refactor for a more elegant solution, as well as fix linting errors, finish crud models, and controlers and write tests are next steps.

<strong>01/14/2018 Project </strong> </br>
Today I finished writing the remaining crud models for the api and begain the controller logic in the routes, I am having some challenges, I am able to connect to the database, I am able to output the dummy data from the db to the console, however there is an issue currently between my  models and controller that interfaces with that model, The route works, and I can get a json object from the route when tested in Postman, however its outputting an empty object. I will wait until I get data outputting from the controllers properly before I commit current changes.

<strong>01/15/2018 project sensing the environment  </strong> </br>
After some hiatus met with a portion of the team that i was working with on the project. We got some work done looks like we are going through a hardware change and will be switching from the teensy hardware platform to the rasberry pi platform due to some advantages for bandwith in transferring data. To transfer data it was decided to use sftp for the time being though I was excited about using a websocket server which I do have a basic a implementation of now and is able to recieve data from a romote address. the difficulty is that will be recieving a stream of data and that once a certain amount of data that data needs to be written to a file . this evening I have done some basic research and have found that node streams may be a good solution to help accomplish this, I am interested in tinkering with that technology some more and get a simple working solution, however currently it seems that sftp is what the team feels is a good solution so be it. So a couple of the team members will be working on getting the hardware transferred to the pi platform and working on the transfer protocals. I will be working on setting up a server that can that data and write as well as helping to set up a couple of db tables which will be populated with that data which will include location, createing a restful api. and integrating google maps with pins that correspond to that data. So as a prototype I suggested that we use sqlite then as the project and amount of data grows we can go to something more robust such as postgresql that was agreed. Glad I will have some hands on this but excited for this project.  

<strong>01/17/2018 Project api  </strong> </br>
so excited after some debugging made easier by the logging modules and a bit of research, I have the first of my controllers working and outputting the correct json, all through this process I have been referencing Node.js WebdevelopmentThird edition by David Herron/ as well as other research, though my use case is a bit different than his and I have had to adapt the patterns he uses to meet my use case. The main difference is in the view layer, for the book he is using a template engine to render the view, In my implentation my view layer is a React frontend that is going to consume the api. Also the data shape is a bit different so my db schemas vary from his. Through referencing his book i have learned much including a better understanding of what and how to implement the mvc pattern how to connect to a db through the use of a model layer how sql queries are executed through the models. The use and execution of promises, and also how the controller/ routes interact with the the models. I need to do a bit more logic in the read controller route for the output to be exactly what I want so ill wait to commit when that is finished, but this is a awesome step and it feels good.

<strong>01/19/2018 Project api  </strong> </br>
Well I did a bit more work on the my read and corresponding controller when I initially got the data outputting from my db the route was outputting a single json object or a todo. What I needed the data shape to be is an array of objects each object being a todo with three key value pairs. to test my assumption that this was not occuring I reinitialized my db and inserted a new row of dummy data. as I thought my data at the endpoint was incomplete. I have been thinking about this problem for a couple of days and was wondering where I should put this logic to accomplish the desired result either in the controller on the route or in the model. It made logical sense to do this in the model. I know I had to take each resulting row from the db and push that row to an array. So I researched arrays on MDN and looked for applicable methods. and was working out the problem first as a use case then a bit on paper, A bit of the same logic was initialized in my test model which is for development purposes only, I needed to get resulting rows from the db and place them into an array of objects. I am using a Constructor pattern to create the objects from the db query results. My solution was to initialize an empty array called todos this I used the forEach method on each resulting row from the sql query, pushed them to the todos array, and then let the promise resolve with todos as an argument. At first I was unsure why rows.forEach(function(){}) worked. The answer is sqlite3. database methods. for my read model I used their method db.all which takes a signature callback function(err, rows) {} rows returns an array. Neat!
