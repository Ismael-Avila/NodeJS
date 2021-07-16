# Ristorante-confusion server-side


# Overview
This project is the second part as part of my Full Stack Web Development Specialization I'm taking from COURSERA. In this respository,  I bring you the
business logic of the web page I'm developing to a fictional restaurant called "Ristorante-confusion" using modern technologies that are governing in
software industry, in this case mongoDB, express and node.js. At the momment I'm still coding this second part but I bring you enough code and examples to
understand how this three tools interacts together to build suitable resquests and responses from the server-side

# Requirements
Before to run this repository you must to have installed the next packages to a proper operation of the code.
1. Node.js: https://nodejs.org/en/download/
1. Express: https://expressjs.com/en/starter/installing.html
1. Postman: https://www.youtube.com/watch?v=9ZZdl4CQbCg

# Running application
To execute the files contained in this repository, follow the next steps.

1. Download the project into a folder or directory of your choice by typing in a window or linux terminal the next command:
`sudo git clone https://github.com/Ismael-Avila/NodeJS.git`
1. Download the required node modules to make working the application by typing:
`sudo npm install`
1. After you've intalled the required packages, create a folder named "MongoDB"  and inside of it, create another folder called data. Following, open a terminal
inside the folder "MongoDB" and copy this command into it: `mongod --dbpath=data --bind_ip 127.0.0.1`. This command is going to set up our database, set the data
folder as the place to locate our database and set the ip where is going to litsen our connection to our database in this case locally.
1. Inside the root or NodeJs folder, open a command terminal and initialize our application with the command:
`npm start`. With this we have set up our Express server.
1. Finally, open your postman program.

# Information about the endpoints.
In this project, there are three important endpoints and inside one of them there are others:
1. Dishes
- root: `localhost:3000/dishes`
- `localhost:3000/dishes/dishId`
- `localhost:3000/dishes/dishId/comments`
- `localhost:3000/dishes/dishId/comments/commentId`
2. Promotions
- root: `localhost:3000/promotions`
- `localhost:3000/promotions/promoId`
3. Leaders
- root: `localhost:3000/leaders`
- `localhost:3000/promotions/leaderId`

To interact with one of them with your postman program first create a new request, click on body section, select raw option, click on text and select JSON format.
With this we have finished to set our enviroment we are ready to sent requests.

# Basic structure of each endpoint
Here is the entire JSON structure for each root endpoint.
1. Dishes
```
{
  "name": "Uthappizza",
  "image": "images/uthappizza.png",
  "category": "mains",
  "label": "Hot",
  "price": "4.99",
  "featured": "true",
  "description": "A unique combination of Indian Uthappam (pancake) and Italian pizza, topped with Cerignola olives, ripe vine cherry tomatoes, Vidalia onion, Guntur chillies and Buffalo Paneer.",
  "comments": [
    {
      "rating": 5,
      "comment": "Imagine all the eatables, living in conFusion!",
      "author": "John Lemon",
      "date": "2012-10-16T17:57:28.556094Z"
    },
    {
      "rating": 4,
      "comment": "Sends anyone to heaven, I wish I could get my mother-in-law to eat it!",
      "author": "Paul McVites",
      "date": "2014-09-05T17:57:28.556094Z"
    },
    {
      "rating": 3,
      "comment": "Eat it, just eat it!",
      "author": "Michael Jaikishan",
      "date": "2015-02-13T17:57:28.556094Z"
    },
    {
      "rating": 4,
      "comment": "Ultimate, Reaching for the stars!",
      "author": "Ringo Starry",
      "date": "2013-12-02T17:57:28.556094Z"
    },
    {
      "rating": 2,
      "comment": "It's your birthday, we're gonna party!",
      "author": "25 Cent",
      "date": "2011-12-02T17:57:28.556094Z"
    }
  ]
}
```
2. Promotions
```
{
  "name": "Weekend Grand Buffet",
  "image": "images/buffet.png",
  "label": "New",
  "price": "19.99",
  "featured": "true",
  "description": "Featuring mouthwatering combinations with a choice of five different salads, six enticing appetizers, six main entrees and five choicest desserts. Free flowing bubbly and soft drinks. All for just $19.99 per person "
}
```
3. Leaders
```
{
  "name": "Peter Pan",
  "image": "images/alberto.png",
  "designation": "Chief Epicurious Officer",
  "abbr": "CEO",
  "featured": "false",
  "description": "Our CEO, Peter, credits his hardworking East Asian immigrant parents who undertook the arduous journey to the shores of America with the intention of giving their children the best future. His mother's wizardy in the kitchen whipping up the tastiest dishes with whatever is available inexpensively at the supermarket, was his first inspiration to create the fusion cuisines for which The Frying Pan became well known. He brings his zeal for fusion cuisines to this restaurant, pioneering cross-cultural culinary connections."
}
```

To interact wih a specific endpoint you must to send the JSON structure in the body of each request. The Espress REST API supports and treats properly
the four basic HTTP VERBS: GET, PUT, POST and DELETE.

Now, maybe you're wondering what to exactly put in the sections that contains an Id in each endpoint, well to obtain that ID you must to send a GET request and
when the server receives this request it will response you with the data that you send but now with an ID added (MongoDB adds this automatically). That is the
ID you can use for each query and HTTP VERB.

Here is an example for promotions. Which the first thing we do is send a GET request and in the body of that request we send the JSON structure
 



