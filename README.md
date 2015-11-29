# Playdrone Archive Crawler

An automated utility for finding and downloading Android APKs collected by the [PlayDrone](https://github.com/nviennot/playdrone) project and stored on [Archive.org](https://archive.org/). With this tool I discovered over 1.5M APKs, many of which were subjected to vulnerability testing as part of my capstone project in EC521 Cyber Security at Boston University.

Installation
------------

Create a virtual environment and activate it: 

```
pip install virtualenv
virtualenv venv
. ./venv/bin/activate
```

Install the necessary dependencies:

```
(venv)$ pip install -r /path/to/requirements.txt
```
    
Usage
-----

Try out the crawler:

```python
from archivecrawler import ArchiveCrawler
c = ArchiveCrawler()
c.index_archive()
c.save()
c.download(10)
```
    
* `index_archive()` builds a local index of the APK repositories hosted on archive.org.
* `save()` writes that index to a file for easy retrieval in the future.
* `download(n)` downloads the first n APKs found.

For a list of repositories indexed:

```python
print c.num_repos
print c.repos[0]
```

For a list of apks indexed (don't actually print this, it's over 1.5M items):

```python
print c.num_apks
print c.apks[0]
```

To restore the crawler from a previously saved index:

```
c.load()
```

Creator
------
Archive Crawler was created and is maintained by **Carlton Duffett**.

* [Github](https://github.com/cjduffett)
* [LinkedIn](https://www.linkedin.com/in/cduffett)

Copyright and License
---------------------
Copyright 2015 Carlton Duffett. Code released under the [Apache 2.0](./LICENSE) license.

    