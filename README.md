<img src="https://github.com/Maxew42/ML/blob/main/web-site/src/images/logo.png" alt="Aimeos logo" title="Trashedy" align="right" height="160" />

# Trashedy

Repository for the Trashedy project. A four weeks school project aiming to develop a ML object detection model to help map river litter. 

## Authors

- Maximilien Dufau
- Benoit Claudic
- Rémi Legrand
- Luc Manceau
- Amélie Jond

We used Pytorch 1.9.0 as the main Deep Learning library.

## Content

The project is divided in three main parts :

- The "production" part with the website and the integrated ML model.
- The research part with notebooks used to train and test the model.
- The .sql database dump, for you to easily install our database with MySQL.

### ml-models-environment

* Notebooks :
  * Train : This notebook can be use to train a pretrained faster rccn model on a specific dataset.
  * Load and execute Model : This notebook is a walk-through presenting how to load a saved model and perform prediction on images in a dataset.

* Saved model and datasets : These directories are made to contain the models and datasets. As they are too heavy to be hosted on GitHub you will need to download them with the links available in `url_to_*.json`

### web-site

The website was created with VueJS 3.0.1. It is working in pair with an homemade API powered by Flask 2.0.1
This is a development website.  

#### Website installation steps

1. Install required python libraries with `pip3 install -r requirements.txt --no-index`
2. Setup the database :
  1. Import `dbTrashedy.sql` in MySQL
  2. Modify connection information in `server/main.py`to fit your own database.
3. Get a model from `ml-models-environment/saved_models/url_to_models.json` and copy it in `web-site/server/static/ml_models`. Adapt the `MODEL_PATH` value in `web-site/server/main.py` if needed.
4. Launch the Vue.js app with `npm install` then `npm run serve`
5. Launch the Flask API with `python web-site/server/main.py`