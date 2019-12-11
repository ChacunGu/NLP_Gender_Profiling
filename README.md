# NLP_Gender_Profiling

## Main objective

Natural Language Processing - Gender Profiling on tweets.

## Context

This project is developped in Python 3 during the Natural Language Processing seminar of the Master in Computer Science in the university of Neuchâtel, Switzerland.

This seminar is worth 5 ECTS points. According to the European Credit Transfer and Accumulation System 25-30 hours of work per members have been invested in this project.

Fall 2019.

## Team members

- [Chacun Guillaume](https://github.com/ChacunGu)
- [Vorpe Fabien](https://github.com/fabienvorpe)

## Installation

This project has been developped and tested in a Jupyter Notebook with Python 3.7.4 64 bits on Windows 10 Professional.  We can't guarantee it will be working on any other configuration.

Multiple Python modules were used in this project. They were installed with Python's package manager pip. They are all listed along with their version in the file requirements.txt.

To simplify the installation process, please consider using a virtual environment.

### Required files

A directory named 'data' has to be created in the root directory. It must contain the following files:
    AMale.txt (original corpus containing men' tweets - not available for download)
    AFemale.txt (original corpus containing women' tweets - not available for download)
    emoji-test.txt (list of existing emojis with their category - download link: https://unicode.org/Public/emoji/12.0/emoji-test.txt, consulted the 11th December 2019)

### Virtual environment

Description of the installation and use of a Python's virtual environment on Windows.

Install the virtual environment module 'virtualenv':
```
pip install virtualenv
```

In the root directory of the project, create a new virtual environment:
```
[path to python.exe (3.7.4 64bits)] -m venv [environment's name]
```

Activate the virtual environment:
```
[environment's name]\Scripts\activate
```

Manually download the spaCy's english model (execute the following from the activated virtual environment):
```
python -m spacy download en_core_web_sm
```

Manually download NLTK's files to use Punkt stemmer and SentiWordNet (execute the following from the activated virtual environment):
```
python
import nltk
nltk.download('punkt')
nltk.download('averaged_perceptron_tagger')
nltk.download('wordnet')
nltk.download('sentiwordnet')
exit()
```

You can then automatically install all the remaining Python's modules required for the project to be working:
```
pip install requirements.txt
```

For more information about virtualenv please check the documentation on : https://python-guide-pt-br.readthedocs.io/fr/latest/dev/virtualenvs.html

## Usage

From the activated virtual environment, you can access the Jupyter Notebook:
```
jupyter notebook
```

The notebook (NLP_Gender_Profiling.ipynb) is structured as follows:
1. Imports
2. Function definitions for data preprocessing, features computation, model training, data visualization & features selection

--- (up to this point, all cells should be executed for the following code to work)

3. Constants and parameters definition (used features, classifier, scaler, etc.)
4. Loading raw corpus (files ./data/AMale.txt/AFemale.txt) or already preprocessed dataset (./data/*.pkl)
5. Compute statistics on the corpus
6. Data visualization with t-SNE
7. Word clouds for women and men
8. Feature selection with Shap
9. Gridsearch
10. Training of a classifier
11. Evaluation of the classifier
