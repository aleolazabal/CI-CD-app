![web app workflow](https://github.com/software-students-fall2022/final-project-team1-finalproject/actions/workflows/web-app.yml/badge.svg)

![web scraper workflow](https://github.com/software-students-fall2022/final-project-team1-finalproject/actions/workflows/web-scraper.yml/badge.svg)

![deploy to Dockerhub and DigitalOcean](https://github.com/software-students-fall2022/final-project-team1-finalproject/actions/workflows/docker-image.yml/badge.svg)
# Final Project

An exercise to put to practice software development teamwork, subsystem communication, containers, deployment, and CI/CD pipelines. See [instructions](./instructions.md) for details.

# Project Description
A software that takes a word or phrase from user and generate a word cloud image based on words related to the word from user. 

The software is composed of 3 sub-systems: a database, a web app and a web scraper app. 

* web app
    * Get the word from user and send a request to the web scrapper with the word. After the request returns, get the image from the database and display it to the user. 

    * The web app also has a featured word cloud page that randomly displays past generated word cloud images. Click refresh to generate a new set of featured images from all of past generated images.

* web scraper app
    * Recieve request with the input word from the web-app, perform a google search with the word, scrape the top websites from the google search, use the scraped result (as text) to generate a word cloud image, store the image to the database and return the request from the web-app. 

* database
    * Stores the user input word, the word cloud image, and the time that the image is generated. 

# Teammates

* Jonason Wu (jw5911): [Github Profile](https://github.com/JonasonWu)
* Brian Lin (bl2814): [Github Profile](https://github.com/blin007)
* Robert Chen (yc3363): [Github Profile](https://github.com/RobertChenYF)
* Alejandro Olazabal (ajo351): [Github Profile](https://github.com/aleolazabal)
* Mark Chen (xc2097): [Github Profile](https://github.com/markizenlee)
* Benji Luo (hjl464): [Github Profile](https://github.com/BenjiLuo) 

# Run the App Locally
1. Pull this repository to your machine.
2. Create and fill 2 .env file based on the template of the [example-env](./example-env) file. Put each of them inside the sub directory of the web-app and web-scrapper. Make sure when you fill the .env file with the mongo connection string inside the double quotes, so the entry should looks like 
```
MONGO_URI="mongodb+srv://cluster0.example.mongodb.net"
```
3. Download Docker Desktop.[link](https://www.docker.com/)
4. Inside the directory of the project, run
```
docker-compose up
```

At this point the scraper app and the web app should be running. <br>

To access the home page of the web app, type in this link in your browser. http://localhost:3000/ <br>

Type the word in the search bar and click search, a generated word cloud image will be displayed on the right side of the web page after the web scraping process is finished. Notice this process may take around 10 seconds. <br>

# Deployment Link

Dockerhub deployment:
* Link to Dockerhub repository: https://hub.docker.com/r/robertchenyf/software-engineer-final-team1-wordcloud

The web app and scraper are in the same dockerhub repository. <br>

The web app is tagged "web-latest". The scraper app is tagged "scraper-latest". <br>

Instuctions on how to pull and run these images are inside the dockerhub repository readme. 

DigitalOcean deployment:
* Link to App: https://sea-lion-app-zbqj8.ondigitalocean.app

# Operate the Unit Tests locally
* Look at [README.md](./web-app/tests) file for steps to test the web-app.
* Look at [README.md](./web-scraper/tests) file for steps to test the web-scraper.

# Miscellaneous
* Link to figma: https://www.figma.com/file/r3ZeAmaOnoKWEQIJ6U7wJP/WordCloud-Scraper?node-id=0%3A1&t=rErnsd2vC5nJtcFk-0
* Look at [README.md](./web-app/README.md) for screenshots of the web app
