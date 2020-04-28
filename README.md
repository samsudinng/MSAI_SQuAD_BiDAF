# AI6127 DEEP NEURAL NETWORK FOR NATURAL LANGUAGE PROCESSING
#   SQuAD baseline BiDAF model

## Set up environment

To setup and install dependencies, create and activate conda environment for squad baseline as follows.

```shell script
conda env create -f environment.yml
conda activate squad_baseline
```

Next, download the GloVE pre-trained word vectors glove.840d.300d.zip from the following link:

http://nlp.stanford.edu/data/glove.840B.300d.zip

Unzip the file in the /data folder. The glove vectors __*glove.840B.300d.txt*__ should be located in the folder /data/glove.840B.300d/ 

## Train and evaluate

To train baseline model with character-level embedding, use this command:

    python train.py --name <label>

Example:
```shell script
python train.py --name baseline_char_embed
```

To train baseline model without character-level embedding, use this command:

    python train.py --name <label> --use_char_emb 0

Example:
```shell script
python train.py --name baseline_without_char_embed --use_char_emb 0
```

## About our code

This code package is adapted from  SQuAD baseline by Chris Chute

https://github.com/chrischute/squad.git

Scripts available here:
- `args.py`  : available arguments
- `train.py` : main training script
- `models.py`: BiDAF model
- `layers.py`: implementation of different layers in the model
- `util.py`  : utilities script