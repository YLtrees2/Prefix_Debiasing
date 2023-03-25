# Prefix_Debiasing

## code and dataset reference

The main project and datasets are based on: 

(Auto-Debias)https://github.com/Irenehere/Auto-Debias

(CrowS-Pairs)https://github.com/nyu-mll/crows-pairs

## running instructions

To reproduce the results in the report, please copy the repo into your Google Drive and follow the Jupyter Notebook Probing_Prefix_learning_based_Debiasing_Method_for_Pre_trained_Language_Models.ipynb. (You may need to change some file paths.)

It is worth noticing that the process is highly time-consuming and require advanced hardware.

## CrowS-Pairs

[prefix_metric.py](https://github.com/YLtrees2/Prefix_Debiasing/blob/main/crows-pairs/prefix_metric.py) is used to evaluate prefix-debias given the learned prefixes. usage:

```
python prefix_metric.py --input_file data/crows_pairs_anonymized.csv 
	--lm_model [mlm_name] 
	-n [size of sub-samples of prefixes]
	--prefix_file [prefix_filename]
	--output_file [output_filename]
	--bias_tested race-color
```

For `mlm_name`, the code supports `bert`, `roberta`, and `albert`.


metric_prefix.py is used to evaluate prefix-debias given the learned prefixes. usage:
