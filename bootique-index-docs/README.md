This module contains source of the Bootique cross-module documentation index published on the website. 
The docs are in Docbook XML format.

## Publishing Prerequisites

Checkout the web site:

```shell
# going to the parent of <main_bootique_checkout>
cd <main_bootique_checkout>/../

# checkout a second copy of Bootique to be able to copy stuff between the branches
git clone git@github.com:nhl/bootique.git bootique-pages 

# get on the website branch
git checkout -b gh-pages origin/gh-pages
```

## Building the Docs

```shell
cd <main_bootique_checkout>/bootique-index-docs
mvn clean package
```

You can now inspect the local docs under ```target/site/index/```.

## Publishing the Docs

Build the docs locally as described above, and then do this:

```shell

cd <main_bootique_checkout>/bootique-index-docs
cp -r target/site/bootique-index-docs/ ../../bootique-pages/docs/
cd ../../bootique-pages/docs/ 
git add -A
git commit -m "docs index update"
git push
```

In a few seconds you will be able to check the result at http://bootique.io/docs/ .