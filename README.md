Simple Search Engine      [![Build Status](https://travis-ci.org/cjlcarvalho/search.py.svg?branch=master)](https://travis-ci.org/cjlcarvalho/search.py)
===

This is a simple search engine project working with Solr, built in Python 2.7 with [web.py](http://webpy.org/) and [PySolarized](https://github.com/izacus/pysolarized).

Summary:
===
1. [Requirements](#requirements)

2. [Configuration commands](#configuration-commands)

3. [Running the web server](#running-the-web-server)

4. [Running the tests](#running-the-tests)

5. [Running with Docker](#running-with-docker)


Requirements:
---

* Python 2.7+

* Solr 6.0.0+

* OpenJDK (because Solr needs it)
 
* Docker (if you want to run with the container)

Configuration commands:
---

* Downloading and configuring Solr:

    `wget https://archive.apache.org/dist/lucene/solr/6.0.0/solr-6.0.0.tgz`

    `tar zxvf solr-6.0.0.tgz`

    `cd solr-6.0.0`
 
    `bin/solr start`

    `bin/solr create -c gettingstarted`

    `cd ..`

* Cloning the project and installing the required libraries:
 
    `git clone https://github.com/cjlcarvalho/search.py`

    `cd search.py`

    `pip2 install -r requirements.txt`


Running the web server:
---

`python __main__.py`

After this command, your webserver will be running in http://0.0.0.0:8080/ or http://localhost:8080/.


Running the tests:
---

* Testing the search module:

    `python test_search.py -v`


Running with Docker:
---

* Build the Docker image:

    `cd Dockerfile`
    
    `docker build -t=caiojcarvalho/container .`

* Create the container and use the container's terminal:

    `docker run -i -t -p 8080:8080 caiojcarvalho/container`

* In the container's terminal, run these commands:

    `# solr-6.0.0/bin/solr start`
    
    `# solr-6.0.0/bin/solr create -c gettingstarted`
    
    `# cd search.py`
    
    `# python __main__.py`
