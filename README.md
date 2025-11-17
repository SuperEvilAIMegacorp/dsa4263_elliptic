## data folder
if you want to re-train models, download elliptic++ csv files from their google drive: https://drive.google.com/drive/folders/1MRPXz79Lu_JGLlJ21MDfML44dKN9R08l

put these in `data/`:
- AddrTx_edgelist.csv
- TxAddr_edgelist.csv
- txs_classes.csv
- txs_edgelist.csv
- txs_features.csv (663mb warning)

trained models already in `models/` so only download if retraining

## setup
```
docker-compose build
docker-compose up

#or to run specific models
docker-compose run --rm fraud-detection python3 run_full_experiments.py --models xgboost graphsage --epochs 200

#or specific configurations
docker-compose run --rm fraud-detection python3 run_full_experiments.py --configs engineered_weight
```

## output
results saved to `results/` - check summary_(timestamp).txt for readable results

models saved to `models/` as {config}_{model}_model.pt or .pkl where config is baseline_noweight, baseline_weight, engineered_noweight, engineered_weight

best model: baseline_noweight xgboost (f1=0.612)

