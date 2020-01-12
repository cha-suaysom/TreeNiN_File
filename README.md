# reana-demo-treenin

This repository contains a yadage workflow running the [TreeNiN](https://github.com/diana-hep/TreeNiN) algorithm for top tagging. This workflow only contains the evaluation part of 

## Quickstart

### Environment

If your environment does not already have `yadage` installed, I suggest using free Google Cloud Shell since it already has the correct software versions so that `yadage` can be installed quickly.

### Steps

The following describes necessary steps to setup yadage workflow for TreeNiN

#### Set up yadage virtual environment

First we set up virtual environment and activate it

`virtualenv ~/.virtualenvs/yadage
source ~/.virtualenvs/yadage/bin/activate`

Next install `yadage` with `pip` or `pip3` note that there could be extra requirements as seen in [here](https://yadage.readthedocs.io/en/latest/introduction.html).

`pip install yadage` 

or 

`pip3 install yadage`


