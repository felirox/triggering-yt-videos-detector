# triggering-yt-videos-detector
This is a project developed to parse the youtube field of an Individual, pass the video's title and thumbnail to various AI models to understand whether they are offensive, triggering, or negative in any way such that it would affect a mentally soft/needy person.

## Inspiration

There have been many instances in all of our everyday lives where social media platforms such as YouTube , Quora, etc. display violent, unpleasing and negatively inducing suggestions which the user would have not wanted to see at all. 

The downside of such algorithms that rely on trends end up showing videos/posts about a certain topic which might not be what the user likes. 

Generally, under normal circumstances, when we o not like something, we would just ignore it and go ahead with our work. But, many times, these videos are so provoking yet so catchy that the person scrolling gets involuntarily attracted to open it and then uncontrollable chain of watching such videos continues. This causes a negative chain of loop and the person ends up having to feel bad about it later on. 

Now, let's imagine a scenario where the user never even came across that video in the beginning to begin with. 

Imagine the mental suffering you are saved from.

That's what we are trying to achieve here. 

## What it does

The mentioned program is the brainchild of a bigger product that we are trying to achieve. Our final goal is to create a full-fledged application which can automate and work on filtering the videos the user would not like based on learning and understanding their interest. 

The developed program preliminarily fires up Selenium and goes on Automation mode. We are doing this so that the video thumbnail  and the titles can be easily extracted to demonstrate the working. In real life scenario, the same code will be utilised to scrape the user's youtube webpage. 

The extracted video thumbnails and texts are cleaned, and then are passed through an array of custom tuned AI models which help us in detecting the vulgar, toxic, obscene, threatening, insulting, identity attacking and profinite words. The AI model also tries to go through the contents in the video thumbnail by using a Dense Object Detector. 

## How we built it
To begin with, we use Selenium to extract the information from youtube. 
Automation commands are specified in order to navigate through the webpage and load the necessary amount of titles to work on the project.

Later the Title & URL are retrieved for the whole section using xpath and they are appended in to a dataframe. 
The data is then passed onto to extract the image from the internet using get request. 

We pass the image primarily through ResNet and YOLO to implement dense object detection and obtain data of what all objects are present in the thumbnail. This gives the user a fair idea on what to expect in the video and helps in blocking the videos which contain any specific type of object that the user specifically dislikes (Eg: Ghosts)


Xpath is specified to instruct selenium to download the necessary objects once again. 

Then the titles that were extracted before are passed onto the models - We use two models, each for DeToxifying and Profanity Detecting. These help in detecting the various parameters that we discussed above and if any of the said words were detected, and the user would be someone who would not like it, we can prevent them from viewing it. 

## Challenges we ran into

- Since this was a hackathon which was conducted online, we initially had difficulties getting adjusted to it.
- Developing the models were very difficult
- It was a bit hard to initially set up Selenium to automate the tasks
- We wanted to develop a full application which would work end-to-end as said without any of our intervention. But, given the difficulty in the project, deployment to the cloud is something for another day.


## Accomplishments that we're proud of

- We learnt Selenium!
- We know how to develop and utilise new models

## What we learned
- Computer Vision, Tensorflow.
- Team management and time management

## What's next for Triggering YouTube Videos Detector
- Deploying the code to the cloud so that an extension on Chrome could be deployed. This would let anyone to use the project for their own purporse. 