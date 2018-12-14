## End-to-End Machine Learning with TensorFlow on 
### Effective ML
- Train model with as much data as you can. Don't sample or aggregate. Tensorflow can scale to big data!
- Gradient descent optimizations are not embarassingly parallel.
- Bad shortcuts - Get big machines with lots of GPUs or Sample data.
- Major improvements to ML happens when human insights are included. Tensorflow can capture many types of feature transformations!
- Use appropriate model architecture. Tensorflow has many model architecture implementations!
### Fully managed
- Hyperparameter tuning.
- Autoscale prediction code. REST API.
- Bookkeeping for pre-processing and feature crosses. Prevent training serving skew.
- Deployment.
### Creating a dataset
- "Good" Feature - related to objective, known at prediction-time, numeric with meaningful magnitude, enough examples, bring human insight.
- Avoid nearly identical data points existing in both training and evaluation. Use hash function such as `FARM_FINGERPRINT`.
- Can use in combination with `MOD` to split. Train on `MOD(x,10)<8`, evaluate on `MOD(x,10)=8`, test on `MOD(x,10)=9` (80-10-10 split).
- Develop on small subset of data. Can use `RAND` to sample. `RAND() < 0.01` samples `1%`.
### Build the model
- Pass Python fuction instead of training dataset directly so that possible to hold data larger than memory.
- Just a number: `numeric_column`.
- Categorical with possible values know beforehand: `categorical_column_with_vocabulary_list`.
- Category is indexed: `categorical_column_with_identity`.
- One-hot encode categorical column: `indicator_column`.
- In distributed training, think in terms of steps/examples and not epochs.
- Training dataset will grow and retrain model only on fresh data.
- Sparse = Wide -> Linear
- Dense = Deep -> DNN
### Operationalizing the model
- For distributed batch prediction, a key such as `hashlib.sha224(data).hexdigest()` is required to match input with result.
### Cloud ML Engine
- `task.py` - parse command-line arguments.
- `model.py` - model, feature columns,  input functions, train-evaluate loop.
- Separate arguments specific to CMLE vs `task.py`.
```
from google.datalab.ml import TensorBoard
TensorBoard().start()
```
- More parallel trials will finish earlier but too many parallel trials will not be able to learn from prior trials.
- Same as naive grid search.
