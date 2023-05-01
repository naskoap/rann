## Experiment

In this section we run an experiment where we test three different tools for hyperparameter tuning: Grid Search, Hyperopt, and Optuna. For more information on this (and each tool), see the information below:

___________

### What is Hyperparameter Tuning

In the field of machine learning, hyperparameter tuning is the process of selecting an optimal set of hyperparameters for a learning algorithm. Hyperparameters are user-selected parameters applied to learning algorithms that affect how they are implemented–for example, constraints, weights, learning rates, number of algorithm layers/complexity, etc.

Depending on which set of hyperparameters is selected, the results and performance of a particular machine learning algorithm can vary dramatically. The possible decision space, however, is enormous. In many cases, there are essentially an infinite set of possible combinations for all of the tuning parameters in a model. It is impossible to try every single one of them and find the absolute best option–instead, users must select a good option.

### Grid Search

Typically, in hyperparameter tuning, users will pre-define a list of combinations to try. For example, if they must provide two parameters, $\beta$ and $\lambda$, they might try all combinations of the following:

$\beta$ = {3, 5, 7, 9}

$\lambda$ = {0.001, 0.01, 0.1, 1.0}

This technique is known as a grid search. It can sometimes produce decent results, but has several main downsides.

The user must themselves define which lists of values to try. This is subjective.

It is very computationally intensive to try every single combination, one at a time. As the number of parameters increases, the number of combinations grows exponentially.

Several hyperparameter tuning tools have been developed in recent years to help simplify this process and produce better results. Some use parallel computing to test a parameters simultaneously and speed up the training process, Many have UI implementations that can help make it easier for users to compare performance across models. Additionally, modern tuning software often uses advanced mathematical techniques to help the user select the best hyperparameters, such as intelligently moving the tuning in a direction that appears to be associated with increased performance scores scores.

Hyperopt (released in 2011) and Optuna (released in 2020) and are two industry standard parameter optimization tools designed to integrate with Python. Both have their code publicly available on GitHub, have public documentation pages, and include UI components. For more details, see the Appendix.


### Details on Hyperopt

Hyperopt is a popular Python library for hyperparameter optimization that has been around–and been considered industry standard–for more than a decade.

It is based on Bayesian optimization techniques, specifically Sequential Model-Based Optimization (SMBO). In SMBO, trials are run one after another, with each trial updating its hyperparameters by updating a probability model and applying Bayesian reasoning. Its goal is to maximize some "score" by modifying a configuration, and it does this by working to narrow the search space and use advanced algorithms for finding which combination of parameters can maximize the probability model.

Within SMBO, it implements several advanced hyperparameter tuning methods including:

- Tree-Structured Parzen Estimator (TPE)

- daptive Tree of Parzen Estimators (ATPE)

- Gaussian Processes (GP)

Hyperopt does not have a full UI implementation, but it does have several built in visualization functions for comparing models.

Hyperopt's code is publicly available on GitHub:

https://github.com/hyperopt/hyperopt

It also has a basic documentation website:

http://hyperopt.github.io/hyperopt/

### Details on Optuna

Optuna was released into the hyperparameter tuning market at a time when there were already quite a few established and trusted tools available (including the second tool we will discuss–Hyperopt).

Its creators chose to introduce Optuna after they discovered limitations in many other existing tuning algorithms, including that they:

- Had instability in some environments

- Were not utilizing the newest technology/advancements in hyperparameter optimization

- Did not provide a way to specify which hyperparameters should be tuned directly within the Python code (instead, requiring the user to write special code just for the optimizer)

The creators of Optuna attempted to fill those gaps, advertising the following features:

1. Define-By-Run style API – An API style that is beginning to become industry standard in deep learning, but had not yet been applied to hyperparameter tuning prior to Optuna. Compared to an older system Define-And-Run. Using Define-By-Run allows users to write more modular code and access more complex hyperparameter spaces.

2. Use of learning curves to prune trials – Optuna uses deep learning and gradient boosting algorithms to predict the end result of a training trial before it is over. This can help it quit unpromising trials before they complete, improving efficiency.

3. Parallel distributed optimization – Optuna supports distributed optimization, simultaneously running multiple trials. This can dramatically speed up the tuning process and allow the user to increase the scale of how many parameters they can try.

4. Visualization dashboard - Optuna provides a UI dashboard where users can watch the optimization process and easily compare results from optimization experiments.

Like Hyperopt, the tool uses several advanced algorithms (including Bayesian methods) for tuning that go beyond standard grid search:

- Tree-Structured Parzen Estimator (TPE)

- Gaussian Processes (GP)

- Covariance Matrix Adaptation (CMA)

- Asynchronous Successive Halving Algorithm (ASHA)

These algorithms are similar to those used in Hyperopt, though Hyperopt is missing CMA and ASHA. The inclusion of ASHA in Optuna is particularly of note, as this is a key feature for allowing parallel optimization.

Optuna is framework agnostic, meaning it can easily be integrated with any of Python's machine learning/deep learning frameworks: Scikit-Learn, PyTorch, Tensorflow, etc.

The code for Optuna is publicly available on GitHub:

https://github.com/optuna/optuna

There is a second GitHub page supporting their UI dashboard component, which was released separately:

https://github.com/optuna/optuna-dashboard

Optuna also has a custom website with tutorials, examples, and links to documentation:

https://optuna.org
