# mlflow02

mlflow

## commands used

### for getting user interface

~~~bash
mlflowui
~~~

### for running an ml project

> mlflow run . 

### To run a MLproject inside a current working directory with existing conda env
>mlflow run . --no-conda
### To run a MLproject inside a current working directory with parameters specified in MLproject
>mlflow run . -P param1=0.2 
### To run a MLproject inside from a github repository
>mlflow run https://github.com/<USERNAME>/<REPO_NAME.git -P param=5.0
### To export conda environment to a file
>conda env export > conda.yaml

## command for prediction on serving model

### for windows -
>curl -X POST -H "Content-Type:application/json; format=pandas-split" --data "{\"columns\":[\"alcohol\", \"chlorides\", \"citric acid\", \"density\", \"fixed acidity\", \"free sulfur dioxide\", \"pH\", \"residual sugar\", \"sulphates\", \"total sulfur dioxide\", \"volatile acidity\"],\"data\":[[12.8, 0.029, 0.48, 0.98, 6.2, 29, 3.33, 1.2, 0.39, 75, 0.66]]}" http://127.0.0.1:1234/invocations

### On Linux and macOS
>curl -X POST -H "Content-Type:application/json; format=pandas-split" --data '{"columns":["alcohol", "chlorides", "citric acid", "density", "fixed acidity", "free sulfur dioxide", "pH", "residual sugar", "sulphates", "total sulfur dioxide", "volatile acidity"],"data":[[12.8, 0.029, 0.48, 0.98, 6.2, 29, 3.33, 1.2, 0.39, 75, 0.66]]}' http://127.0.0.1:1234/invocations

### Or use Thunder client extension on VSCode or use PostMan