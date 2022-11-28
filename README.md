# Relevant Search for OpenSearch

This repository is forked from the original at https://github.com/o19s/relevant-search-book. Changes include adapting the examples for OpenSearch 2.4, an upgrade to python 3.x, using pipenv for installation and package management, and changing the notebook environment from iPython to JupyterLab.

Original code and Examples for [Relevant Search](http://manning.com/turnbull) by [Doug Turnbull](http://github.com/softwaredoug) and [John Berryman](http://github.com/jnbrymn). Published by [Manning Publications](http://manning.com).

Relevant Search is all about leveraging Solr, Elasticsearch, and OpenSearch to build more intelligent search applications with intuitive results!

# How to run

## Install Python

Examples in this repository are written in Python 3.9 and use JupyterLabs. The first thing you'll need to do is install Python, pip (the Python package installer).

1. Install Python 3.x for your platform [here](https://www.python.org/downloads/). For Windows we recommend the [ActivePython](http://www.activestate.com/activepython) distribution.
2. Install pipenv: https://pipenv.pypa.io/en/latest/

## Install OpenSearch

The examples expect OpenSearch to be hosted at localhost:9200. There are multiple ways to install OpenSearch

### Recommended: Docker Compose

Docker is a tool for installing and provisioning virtual machines locally for development purposes. If you've never used Docker or Docker Compose, you can follow the instructions [here](https://opensearch.org/downloads.html). 

   ```
1. Confirm OpenSearch is running

  ```
  curl -XGET http://localhost:9200
  ```
  
  or visit this URL in your browser. 
  
  You should see JSON returned from the Elasticsearch instance. Something like:

   ```json
   {
	"name": "runTask-0",
	"cluster_name": "runTask",
	"cluster_uuid": "bvzc-Pn_QMOahVxShDASAA",
	"version": {
		   "distribution": "opensearch",
		   "number": "3.0.0-SNAPSHOT",
		   "build_type": "tar",
		   "build_hash": "e3fd49f7b143f3da9aee132712b87a6ccbbe0214",
		   "build_date": "2022-11-26T04:38:04.718104Z",
		   "build_snapshot": true,
		   "lucene_version": "9.5.0",
		   "minimum_wire_compatibility_version": "2.5.0",
		   "minimum_index_compatibility_version": "2.0.0"
	},
	"tagline": "The OpenSearch Project: https://opensearch.org/"
   }
   ```

5. When you're done working with examples, shut down the Docker containers.

  ```
  docker-compose down
  ```

## Running The Python Examples

The examples are written in Python 3.9 in [Jupyter notebooks](https://jupyter-notebook.readthedocs.io/en/stable/) depending only on a few basic libraries. It is recommended to use [JupyterLab](https://jupyterlab.readthedocs.io/en/stable/) as an execution environment. Examples either use opensearch-py or [requests](http://docs.python-requests.org/en/latest/) HTTP library. Some of the external APIs require API keys (for example TMDB, you can obtain one [here](https://www.themoviedb.org/faq/api)).

To run the IPython Notebook Examples

1. First ensure you have git, python 2.7 and pip installed and in your PATH

2. Then use the following commands to install the required dependencies
  ```
  git clone git@github.com:macohen/relevant-search-book.git
  cd relevant-search-book
  cd ipython
  pipenv install requests
  pipenv install jupyter
  pipenv install opensearchdsl
  pipenv install opensearchpy
  ```

5. Launch!

  ```jupyterlab notebook```

6. Play!

Switch to your default browser where the notebook examples are ready for you to experiment with. Keep in mind many examples are order dependent, so you can't just jump to an interesting listing and run it. Indexing commands with certain settings and what not need to be run. Be sure to run the prior notebook commands too!

Happy Searching!

