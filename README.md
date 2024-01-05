# Tutorial for applying Great Expectations to BNIA data 

Tutorial for data researchers to apply [Great Expectations](https://legacy.docs.greatexpectations.io/en/latest/guides/how_to_guides.html) validation check to [BNIA data](https://bniajfi.org).

The core operation of Great Expectations is to "Validate data X against Expectation Y." 

The validation checks (i.e. Expectations) included here were created using the Great Expecations automatic Profiler on the data sample.

The following steps walk through how to validate a new dataset against the validation checks created from the original dataset.

## Key Files

- `expectations/bnia/demo.json`: the validation checks being performed
- `checkpoints`: the bundled validation data check, you'll create a new checkpoint in the steps below
- `great_expectations.yml`: configuration information set in the init stage

## Steps to Validate dataset

### Set up local repo
  1. Clone repo locally
  2. Set up your Python Virtual Environment
  3. Prepare new BNIA dataset. Save data file in the data directory and keep track of the file name and type.

### Set up a checkpoint
Run the following command:
```
great_expectations --v3-api checkpoint new my_new_checkpoint
```
This will open a Juypter Notebook. Update the yaml_config template code to include the correct csv file in the data directory.
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
