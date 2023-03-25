# Prefix_Debiasing

## Code and dataset reference

The main project and datasets are based on: 

(Auto-Debias)https://github.com/Irenehere/Auto-Debias

(CrowS-Pairs)https://github.com/nyu-mll/crows-pairs

## Running instructions

To reproduce the results in the report, please copy the repo into your Google Drive and follow the Jupyter Notebook Probing_Prefix_learning_based_Debiasing_Method_for_Pre_trained_Language_Models.ipynb. (You may need to change some file paths.)

It is worth noticing that the process is highly time-consuming and require advanced hardware.


[prefix_metric.py](https://github.com/YLtrees2/Prefix_Debiasing/blob/main/crows-pairs/prefix_metric.py) is used to evaluate prefix-debias given the learned prefixes. usage:

```
python prefix_metric.py --input_file data/crows_pairs_anonymized.csv 
	--lm_model [mlm_name] 
	-n [size of sub-samples of prefixes]
	--prefix_file [prefix_filename]
	--output_file [output_filename]
	--bias_tested [bias_type]
```

For `mlm_name`, the code supports `bert`, `roberta`, and `albert`; for `bias_tested`, the code supports `gender` and `race-color`.


[metric_local.py](https://github.com/YLtrees2/Prefix_Debiasing/blob/main/crows-pairs/metric_local.py) is used to evaluate local pre-trained models.
usage:

```
python metric_local.py --input_file data/crows_pairs_anonymized.csv 
	--input_file data/crows_pairs_anonymized.csv 
	--lm_model [mlm_name] 
	--output_file [output_filename]
	--model_or_path [model_or_path]
```
where `model_or_path` can be either model name like `bert-base-uncased` or the path to a (fine-tuned) model stored locally.

