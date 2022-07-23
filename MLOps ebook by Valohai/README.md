# Practical MLOps

```by Valohai```

## Best Practices

- Version control everything, including models, code, data, parameters, and environment. Enable anyone to trace how a model was produced.
- Componentize the steps of the model creation process and build them into a pipeline. A single notebook is not a pipeline.
- Codify testing. With checkpoints and safeguards in place, there is a standard that models have to adhere to.
- Automate work to increase how much time can be spent on future development.

## MLOps metrics

- Model update frequency met (and able to identify stale models)
- Time to re-train and deploy a new model and push to production
- Performance of model endpoint for online predictions (e.g. response time in ms)
- \# of calls / % of failed calls to themodel endpoint
- Collaboration between the multidisciplinary team (e.g. data scientists, engineers, IT-Ops, legal, business)
- Attendance of key stakeholders to regular project updates (for example, every six weeks)
- Infrastructure scales to the machine learning teams without manual work from IT.

## End-to-End pipelines

- The pipeline is the product, not the model. Do not deploy the model; deploy the pipeline.
- To build a pipeline, split the system down into small well-defined components.
- Model accuracy will eventually degrade as the world changes. Prepare for it.

## Productionalization - Feature Stores

Getting features to production is particularly hard because we need to get feature transformations (or pipelines) to production, and curate the feature values to serve consistent data for training and online inference. Data scientists typically pass their feature transformations to data engineers to re-implement the feature pipelines with
production-hardened code. That’s a complicated process that typically introduces weeks or months of lead time.

This is where feature stores come in. Feature stores are central hubs
for features. They transform raw data into feature values, store the
values, and serve them for model training and online predictions. By
automating these steps, feature stores allow data scientists to build
and deploy features within hours instead of months. They enable
data scientists to fully control their features from development to
production, bringing DevOps-like tooling to the feature engineering
process.

### Feature stores allow data scientists to

- Build a library of great features collaboratively. Instead of managing
feature transformations in a local notebook, data scientists create
standard feature definitions that are managed in a Git-backed
repository. These feature definitions are then applied to the feature
store. This brings consistency to feature definitions, and the ability
to collaborate on new features.
- Deploy features to production instantly. Once feature definitions
are applied to the feature store, it automates the feature
transformations and curates the feature values. Those values can
be used to create training datasets or can be served online for
real-time inference.
- Share, discover, and re-use features. Features and their metadata,
transformation logic, and values, are all managed in a central
feature registry and are searchable. Data scientists can easily
discover existing features and re-use them across models.

Feature stores were first introduced by the Uber Michelangelo team.
Since then, many companies like Airbnb and Netflix have built their
own internal feature stores to solve this problem. But feature stores
are also complicated to build, and have to a large extent remained
inaccessible to less advanced organizations.

## Testing

- Data Testing
- Model Testing
- Infrastructure Testing
