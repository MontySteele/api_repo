# api_repo

This project was submitted at the end of my course with Springboard's Machine Learning track. The ultimate goal of this project is to build a web api in which a user can enter a sample comment for a news article and receive a prediction of how many 'likes' or 'recommendations' their comment will receive. This program could be useful to web managers to create a spam filter that automatically removes low-value spam comments or places comments that are predicted to eb popular at the top of a discussion thread for easy viewing. 

This repo will run an api that use the trained model produced by the code in my "NLP_production_repo" in the backend. The program produces a simple html webpage where individual comments can be entered one at a time for testing, as well as an api

### Dependencies ###

This project uses fastai to load and run the trained model on incoming data. It is recommended that fastai be installed under a virtual environment. To create a virtual environment using conda (anaconda) with all necessary dependencies installed, run the following command:

conda create -n fastai python=3.6

Documentation for installing conda can be found [here.](https://docs.anaconda.com/anaconda/install/)

### Using this project ###

After cloning this repo, make sure that the model file is copied into the repo directory. Then run the following commands from the repo directory:

python api.py

The api will now be listening for incoming requests at port 8000. To reach the webserver, go to:

http://<Your_IP_address>:8000

To sent an api call, send an html request using the following format: http://<Your_IP_address>:8000/comment/api/?comment=<YOUR_COMMENT_HERE>

The API will return a JSON dictionary formatted as:
{ 
<YOUR_COMMENT_HERE> : < A string containing the estimated number of likes here > 
}

### Warning ###

Currently this API only discriminates between zero-like comments nonzero-like comments. It can filter out spam but is not yet equipped with a second model that is trained to provide numerical predictions of the comment's number of likes. Stay tuned!
