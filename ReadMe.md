<p align="center">
   <img src="https://raw.githubusercontent.com/camelot-dev/camelot/master/docs/_static/camelot.png" width="200">
</p>


#### 1. Steps to Initialize Git Repository
```
git init
```
```
git clone https://github.com/Praveen-Kumar-SGK/simple-dvc-demo.git
```
#####Or if you want to push it to the repo by command line
```
git remote add origin  https://github.com/Praveen-Kumar-SGK/simple-dvc-demo.git
```
#### 2. DVC
```
dvc init
```
#### 3. Create requirements.txt
 ```
pip install -r requirements.txt
```
#### 4. Create template.py 
- It creates empty folders - data(raw,processed), notebooks, src, templates, saved_models,tests,reports etc
- It creates empty files - src(__init__.py,get_data,load,split,evaluate), dvc.yaml, params.yaml , .gitignore, tests(init,conftest,test_config)
#### 5. Uploading the created files
```
git add .
```
```
git commit -m "First Commit"
```
```
git push origin main
```
- If you want single line command for git
```
git add . && git commit -m "First Commit" && git push origin main
```
#### 6. Download dataset and placing in data_given folder
https://drive.google.com/drive/folders/18zqQiCJVgF7uzXgfbIJ-04zgz1ItNfF5?usp=sharing

#### 7. Adding files to DVC
- Github does not hold bigger files but dvc will save it in our google drive and track the version.
```
dvc add data_given/winequality.csv
```
#### 8. Source files- src 
- get_data : If the data is from cloud or any other local folder we access and place it in data/raw
- load_data : The raw data might need some cleaning like changing the column names
- split_data : We will train test split and storing in data/processed folder
- train_and_evaluate : We train the model and evaluate the train dataset and dump the model and the scores & params in respective folder( saved_model and reports).
#### 9. DVC yaml
- This file creates a pipeline/stages for tracking the version of the required doc.
#### 10. tox.ini
#### 11. setup.py 
- We can install the src file by converting into a package.
#### 12. webapp
- static : css folder containg main.css and script folder containg the index.js
- templats : It contains the index, 404 and base html files.
#### 13. app.py
- This file is a flask deployment file where it contains values from the html or api response and produces predicted value in the html page.
#### 14. prediction_service
- schema.json : This json file holds the "min" and "max" of respective Independent parameter(X variables).
- prediction.py : This file validates the inputs range of values given for predictions and gives the prediction to html file.
#### 15. cicd.yaml
