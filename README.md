# SMA
Extend SOMEF to extract dependencies from the GitHub dependency page, and find software that has related functionality.        
Clustering analysis Methods:
* Kmeans
* GMM
* Topic Modeling

## Requirements

- Python 3.8


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

### Configure
Before running SOMEF, you must configure it appropriately. Run

```bash
somef configure
```

And you will be asked to provide the following: 

- A GitHub authentication token [**optional, leave blank if not used**], which SOMEF uses to retrieve metadata from GitHub. If you don't include an authentication token, you can still use SOMEF. However, you may be limited to a series of requests per hour. For more information, see [https://help.github.com/en/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line](https://help.github.com/en/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line) 
- The path to the trained classifiers (pickle files). If you have your own classifiers, you can provide them here. Otherwise, you can leave it blank

### Run SOMEF

```bash
$ somef describe --help
  SOMEF Command Line Interface
Usage: somef describe [OPTIONS]

  Running the Command Line Interface

Options:
  -t, --threshold FLOAT           Threshold to classify the text  [required]
  Input: [mutually_exclusive, required]
    -r, --repo_url URL            Github Repository URL
    -d, --doc_src PATH            Path to the README file source
    -i, --in_file PATH            A file of newline separated links to GitHub
                                  repositories

  Output: [required_any]
    -o, --output PATH             Path to the output file. If supplied, the
                                  output will be in JSON

    -g, --graph_out PATH          Path to the output Knowledge Graph file. If
                                  supplied, the output will be a Knowledge
                                  Graph, in the format given in the --format
                                  option

  -f, --graph_format [turtle|json-ld]
                                  If the --graph_out option is given, this is
                                  the format that the graph will be stored in

  -h, --help                      Show this message and exit.
```

## Usage example:
The following command extracts all metadata available from [https://github.com/dgarijo/Widoco/](https://github.com/dgarijo/Widoco/). 

```bash
somef describe -r https://github.com/dgarijo/Widoco/ -o test.json -t 0.8
```

### Add/Remove a Category:

If the user wants to run the classifier for an additional category or wants to remove an existing category, corresponding path entry in the config.json should be provided and the category type should be added/removed in the category variable in cli.py

## Contribute:

If you want to contribute with a pull request, please do so by submitting it to the `dev` branch.

## Cite SOMEF:
```
@INPROCEEDINGS{9006447, 
author={A. {Mao} and D. {Garijo} and S. {Fakhraei}}, 
booktitle={2019 IEEE International Conference on Big Data (Big Data)}, 
title={SoMEF: A Framework for Capturing Scientific Software Metadata from its Documentation}, 
year={2019}, 
url={http://dgarijo.com/papers/SoMEF.pdf},
pages={3032-3037}
} 
```

## Next features:
We are improving SOMEF to incorporate the following features:
- Automated detection of other documentations sources, besides the readme.md file.
- Automated detection and annotation of Docker files.
- Automated detection and annotation of notebooks.
- Automated detection of examples associated with a software component.
