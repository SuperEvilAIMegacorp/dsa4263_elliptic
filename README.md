
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
results are saved to the `results/` directory refer to summary_(timestamp).txt for readable summary
models are saved to the `models/` directory:
- `gcn_model.pt`, `gat_model.pt`, `graphsage_model.pt`
- `xgboost_model.pkl`

