# BNIA - Great Expectations tutorial

This repository was created using the Great Expectations 'How to Guide' tutorial applied to BNIA data. I recommend following their guide if interested in the earlier set up action items.

The following walks through validating a dataset against a InfoUSA2021 data sample. The validation checks (i.e. Expectations) were created using the Great Expecations automatic Profiler on the data sample, these validations will need to be updated.

## Key Files

- expectations/bnia/demo.json: the validation checks being performed
- checkpoints: these are bundled validation data check, you'll create one in the below steps
- great_expectations.yml: configuration information set in the init stage

## Steps to Validate dataset

The core operation of Great Expectations is to "Validate data X against Expectation Y." These steps walk through how to validate a new dataset against the validation checks created from the original dataset.

### Clone repo locally
add if needed
### Set up Python Virtual Environment
add if needed
### Get new dataset ready 
Save the new dataset as a csv in the data directory. 

*Notes- will need to know the file name and file type so if thats something you want to automatically document, may want to write a pre-validation script. Also GE gave me an error in opening the UI when comparing a dataset with different fields, need to look into this. *
### Set up a checkpoint
Run the following command:
```
great_expectations --v3-api checkpoint new my_new_checkpoint
```
This will open a juypter notebook. Update the yaml_config template code to include the correct csv file in the data directory.
```
data_asset_name: my_new_dataset.csv
```
Run the notebook. If you want it to open the UI (Data Docs), uncomment the bottom cell.
This will have created a new checkpoint yml file in the checkpoint directory.
### Open Data Docs
You can also open the data docs with the following command:
```
great_expectations docs build
```
The Data Docs UI allows you to explore your Validation results, as well as your Expectations. 
