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

Resources for Hyperopt Search Space:
http://hyperopt.github.io/hyperopt/getting-started/search_spaces/

![Screenshot 2023-06-18 at 10 19 36 AM](https://github.com/caitlincjohnson/machine-learning/assets/35669839/3162d4bb-bff9-467c-ad46-40070695a31a)

![Screenshot 2023-06-18 at 10 52 02 AM](https://github.com/caitlincjohnson/machine-learning/assets/35669839/97f0ebd5-0b04-4210-87b7-643dd4e40c96)

When choosing the best model, the one with the best score isn't always necessarily the best one, as they may be way more complex and more time-consuming which impacts performance in production. Choosing one with a barely worse score yet less complexity may actually be the best path moving forward.
