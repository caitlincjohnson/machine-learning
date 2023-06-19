# MLflow

MLflow is an open source platform for the machine learning lifecycle. This contains four main modules:
- Tracking (i.e., Experiment Tracking)
- Models
- Model Registry
- Projects

For tracking experiments with MLflow, it allows you to organize your experiments into runs which helps you keep track of:
- Parameters
- Metrics
- Metadata (this can include tags)
- Artifacts
- Models

In addition, it automatically logs extra information about the run:
- Source code
- Version of the code (e.g., git commit)
- Start and end time of the experiment run
- Author

Each run is a trial in an ML experiment, which can contain many different runs/trials.

## Parameter Tuning

Resources for Hyperopt Search Space:
http://hyperopt.github.io/hyperopt/getting-started/search_spaces/

![Screenshot 2023-06-18 at 10 19 36 AM](https://github.com/caitlincjohnson/machine-learning/assets/35669839/3162d4bb-bff9-467c-ad46-40070695a31a)

![Screenshot 2023-06-18 at 10 52 02 AM](https://github.com/caitlincjohnson/machine-learning/assets/35669839/97f0ebd5-0b04-4210-87b7-643dd4e40c96)

When choosing the best model, the one with the best score isn't always necessarily the best one, as they may be way more complex and more time-consuming which impacts performance in production. Choosing one with a barely worse score yet less complexity may actually be the best path moving forward.

Resources for MLflow Autologs: https://mlflow.org/docs/latest/tracking.html#automatic-logging

## Experiment Tracking
![image](https://github.com/caitlincjohnson/machine-learning/assets/35669839/a99c88e9-044a-4a0a-929a-0c54ebf71326)

Source: https://neptune.ai/experiment-tracking

## Model Logging
![Screenshot 2023-06-19 at 7 53 40 AM](https://github.com/caitlincjohnson/machine-learning/assets/35669839/8d96fd6d-19c6-494e-9ab8-8ffedae47557)

Generally there are two options for logging models in MLflow:
1. Log model as an artifact: `mlflow.log_artifact("mymodel", artifact_path="models")`
2. Log model using the method "log_model": `mlflow.<framework>.log_model(model, artifact_path="models")`

## Model Registry
![Screenshot 2023-06-19 at 8 01 13 AM](https://github.com/caitlincjohnson/machine-learning/assets/35669839/40536fdb-c8c1-48a8-9ece-1458dea91d6d)

Model registry is not responsible for deploying; they're only used to list what models are production-ready, and the labels are assigned to models to designate the stage they're in. A CI/CD process is needed to complement the model registry for deployment purposes.

It provides:
- Model lineage
- Model versioning
- Stage transitions
- Annotations

## MLflow Client Class
A Client of:
- an MLflow Tracking Server that creates and manages experiments and runs
- an MLflow Registry Server that creates and manages registered models and model versions
To instantiate it we need to pass a tracking URI and/or a registry URI (e.g., "sqlite:///mlflow.db")

## Configuring MLflow for Real-World Scenarios
There are three main aspects when it comes to configuring MLflow, and not all scenarios will look the same nor have the same requirements.
1. Backend store
   - local filesystem
   - SQLAlchemy compatible DB (e.g., SQLite)
2. Artifacts store
   - local filesystem
   - remote (e.g., S3 bucket)
3. Tracking server
   - no tracking server
   - localhost
   - remote
