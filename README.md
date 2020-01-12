# reana-demo-treenin

This repository contains a yadage workflow running the [TreeNiN](https://github.com/diana-hep/TreeNiN) algorithm for top tagging. This workflow only contains the evaluation part of TreeNiN as outlined in the repository. User can use their own data or use the sample data from this repository.

## Quickstart

### Computing Environment

If your environment does not already have `yadage` installed, I suggest using free Google Cloud Shell since it already has the correct software versions so that `yadage` can be installed quickly.

The following describes necessary steps to setup yadage workflow for TreeNiN

### Set up yadage virtual environment

First clone this repository with

`git clone https://github.com/cha-suaysom/reana-demo-treenin`

Next we set up virtual environment and activate it

`virtualenv ~/.virtualenvs/yadage`

`source ~/.virtualenvs/yadage/bin/activate`

Next install `yadage` with `pip` or `pip3` note that there could be extra requirements as seen in [here](https://yadage.readthedocs.io/en/latest/introduction.html).

`pip install yadage` 

or 

`pip3 install yadage`

### Running the workflow

There are ways to obtain input data, based on user's preference.

1. Using the sample input file in this repository, in which case we set the data url to be `https://github.com/cha-suaysom/reana-demo-treenin/raw/master/test_top_tag_reference_dataset_kt_1200000_Njets_.zip` and the yadage workflow can be run with

`rm -rf _run && mkdir -p _run && chmod -R a+rwx _run && yadage-run  _run workflow/workflow.yml workflow/input.yml -p input_url=https://github.com/cha-suaysom/reana-demo-treenin/raw/master/test_top_tag_reference_dataset_kt_1200000_Njets_.zip --accept-metadir`

Note that the first part of command clear the workspace and give appropriate permission to the folders that yadage needs to write in. The second part sets where the input data has to be downloaded from.


2. Using custom data. User can use TreeNiN repository and run `python dataWorkflow.py N` where `N` is a suitable number (more details at the [TreeNiN repository](https://github.com/diana-hep/TreeNiN). After running this we will get a pickle file with name `test_top_tag_reference_dataset_kt_1200000_Njets_.pkl` which is then zipped into `test_top_tag_reference_dataset_kt_1200000_Njets_.zip`. Suppose this file is uploaded (for example to Github, storage bucket or other clouds) to a url `your_zip_file_input_url` then we run.

`rm -rf _run && mkdir -p _run && chmod -R a+rwx _run && yadage-run  _run workflow/workflow.yml workflow/input.yml -p input_url=your_zip_file_input_url --accept-metadir`

**Note** The input data in `input.yml` file is actually not used.

### Result

The result is saved into `TreeNiN_hd50.pkl` which saved the probabilities of each of the 9 models for each jet.







