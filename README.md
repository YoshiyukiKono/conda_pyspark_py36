# Getting Started with PySpark

This baseline project shows how to interact with PySpark on Yarn
on Cloudera Data Science Workbench. To begin, open an IPython workbench.

## Cluster permissions

If your cluster is Kerberized, you will need to enter your Kerberos
credentials. Click the "Kerberos" tab under your user settings.

Otherwise, you will need to set the HADOOP_USER_NAME environmental
variable. Click the "Environment" tab under your project settings.

## Files

Modify the default files to get started with your own project.

* `README.md` -- This project's readme in Markdown format.
* `pi.py` -- The simplest PySpark example script.

# Getting Started with Python3.6 for Spark

## CDSW preparations

### Project Settings

Project Menu -> Settings -> Engine -> Environment Variables

`Add` the variable below and `Save Environment`

- Name:`PYSPARK_PYTHON`
- Value:`./PY36/py36/bin/python`

### Workbench

```
$ conda create -n py36 -y python=3.6 numpy pip
$ source activate py36
(py36)$ cp -r ~/.local/lib ~/.conda/envs/py36/
(py36)$ source deactivate
```
```
$ cd ~/.conda/envs
$ zip -r ../../py36.zip py36
```

### spark-defaults.conf
The `spark-defaults.conf` included in this repository already has the following lines.
```
spark.yarn.appMasterEnv.PYSPARK_PYTHON=./PY36/py36/bin/python
spark.yarn.dist.archives=py36.zip#PY36
```



## File

* `pi.ipynb` -- The simplest PySpark example script for Jupyter notebook with Python3.
