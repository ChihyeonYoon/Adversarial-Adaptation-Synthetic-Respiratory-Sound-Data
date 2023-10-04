# Adversarial Fine-tuning using Generated Respiratory Sound to Address Class Imbalance
Training Respiratory Sound Classification Model with Adversarial FT


### Environments
`Ubuntu xx.xx`  
`Python 3.8.xx`


## Datasets

We provide the pre-processed dataset with original ICBHI and Mixed500 dataset as follows:

Please download and extract in ./data/

## Run

### AST FT (No aug.)
```
$ ./scripts/icbhi_ce.sh
```

### AST FT (Mixed500)
```
$ ./scripts/icbhi_ce_1msteps_500.sh
```

### AST FT (Mixed2k)
```
$ ./scripts/icbhi_ce_1msteps_2k.sh
```

### Aderversarial FT (Mixed500)
```
$ ./scripts/icbhi_aft_1msteps_500_mixed.sh
```

## Evaluation

We provide the AFT pretrained on Mixed500, which has the performance of around 62 Score as follows:


Please download and move in ./

### Run evaluation
```
$ ./scripts/eval_aft_mixed500.sh
```