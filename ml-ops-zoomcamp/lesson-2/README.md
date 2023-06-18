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
