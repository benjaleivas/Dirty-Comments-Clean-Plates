# Dirty Comments, Clean Plates
Dirty Comments, Clean Plates: Using Restaurant Reviews to Predict Failed Restaurant Inspections in Philadelphia

Our task: use a corpus of text-based reviews to train a model to classify if a restaurant is likely to fail a health inspection

Our project has had the following phases:
* attempting to use Chicago inspections and Yelp review data
* pivoting to a philadelphia-based approach when our scraping efforts were throttled
* creating NN and transformer-based models
* building a fake reviews dataset
* applying our binary-classification models on the fake reviews labeled dataset

This repository has the following directories, which include code for how we constructed our project:
* `collect/`: contains two sub-directories that chronicle our data collection efforts for both the Chicago-based approach and the philadelpha approach.
    * `chicago/datatypes.py`: ReviewDataset class for reading in scaped yelp data (Jack, 25 lines)
    * `chicago/get_inspections.py`: Gets inspections and restaurants jsons, cleans and merges them (Claire, 90 lines)
    * `chicago/get_restaurants_by_point.py`: Pulls top 1000 restaurants given a list of lat/long coordinates (Claire, 85 lines)
    * `chicago/identify_points.py`: Given chicago geographic boundaries, identifies n random points (Claire, 59 lines)
    * `chicago/yelp_scrape.py`: Scrapes yelp reviews given a business id (Jack, 127 lines)
    * `philadelphia/merge.py`: merges inspection and review datasets for philadelphia (Jack & Claire, 145 lines)
    * `philadelphia/merge.py`: merges inspection and review datasets for philadelphia (Jack & Claire, 145 lines)
    * `yelp/yelp_cleaning.py`: subsets all yelp reviews to only those by verified users (Raul, 80 lines)
* `data/`: houses outputs from both data collection processes (no code here, just intermediate outputs)
* `eda/`: contains a few notebooks that explore the merged philadelphia dataset
    * `eda.py`: overview of merged philadelphia data (Benja, 150 lines)
    * `graphs_plots.py`: plots for eda (Raul, 100 lines)
    * `yelp_data_eda.py`: counts for yelp data for getting an idea of what is available (Claire, 30 lines)
* `models/`: contains a few key custom classes/functions that build our modeling pipeline. The rest of the files are notebooks that use these custom packages to run our models and report results.
    * `dataloaders.py`: custom dataset classes and vectorizers for text processing (Claire & Jack, 215 lines)
    * `features.py`: data cleaning to make the feature variables into numeric arrays (Jack, 200 lines)
    * `shared_models.py`: 5 developed models (Claire & Jack, 88 lines)
    * `helpers.py`: helpers for training models and displaying results, adapted from class functions (Claire, 97 lines)
    * `run_models.ipynb`: implements all Logistic/SVN models (Claire, 100 lines)
    * all other ipynb notebooks: implements BERT and RNN models (Jack, ~100 lines per script)
* `chat_gpt/`: contains our pipeline to read in "fake" reviews from ChatGBT 3.5 and 4.0. 
    * `generate_reviews.py`: Uses the openAI API to generate fake reviews (Benja, 200 lines)

