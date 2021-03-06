# Duet Baseline
To help community reproduce our results and get started quickly we are including out DUET baseline present in our leaderboard. As of right now only duet.py works as we are separating the items into a predict and train file

## Requirements
Python 3.5
CUDA 9.0 
Pytorch
h5py
numpy
## Setup
1. Download all the MSMARCO ranking files into your datadir
2. Use the existing normalized idf or generate your own normalized idf values using something like our makeidf.py script or any other system you would like.
3. We suggest you use [Conda](https://conda.io/docs/) to create enviroments. Doing so go ahead and create a new enviroment
~~~
conda create --name msmarcoranking python=3.6 --file req.txt
conda activate msmarcoranking
~~~
Modify the duet.py script so that DATA_DIR now includes the following: ngraphs.txt, idf.norm.tsv, triples.train.sample.tsv(or triples.train.full.tsv), top1000.dev.tsv qrel.dev.tsv(or change to top1000.eval.tsv and comment out the usage of qrels to just produce the submitable predcition).
4. Confirm your enviorment has everything necessary and run duet.py if the model finishes then raise the epoch count to whatever train period you desire. 