# SMA
Extend SOMEF to extract dependencies from the GitHub dependency page, and find software that has related functionality.        

## Dependency Extractor

The current version of GitHub dependecy extractor is a fork of xkcd2347. The inital setup is the same as found of the github page https://github.com/edsu/xkcd2347

To get dependency run the following command:

The command takes four inputs
- input file name
- output_file
- git_hub_key
- hop 

The output i.e. the list of dependencies in written the output file in the form of a json

```sh
$ python dependency_ectractor.py <<input_file>> <<output_file>> <<git_hub_key>> <<hop>>
```

## Clustering analysis Methods:
* Topic Modeling
* k-means
* GMM


## Install from GitHub

Clone this GitHub repository

```
git clone https://github.com/KnowledgeCaptureAndDiscovery/SMA.git
```

Install sma (note that you should be in the folder that you just cloned)

```
cd sma
pip install -e
```

or
```
pip install git+https://github.com/KnowledgeCaptureAndDiscovery/SMA.git
```

## Usage 



## Dependencies

SMA  was written for Python 3 and tested on the following versions of Python:

python 3.8

SMA the following packages:
* Numpy
* gensim 
* json
* os 
* re 
* pyLDAvis 
* matplotlib 
* diskcache
* pyspark
* dotenv
