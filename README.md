# AI6127 DEEP NEURAL NETWORK FOR NATURAL LANGUAGE PROCESSING
#   SQuAD baseline BiDAF model

## Set up environment

To setup and install dependencies, clone or download this repository into your local machine. 
Create and activate conda environment for squad baseline with the following command.

```shell script
conda env create -f environment.yml
conda activate squad_baseline
```

Next, download the file __*data.zip*__ containing the processed dataset, embedding vectors and GloVE pre-trained word vectors *glove.840d.300d.txt* from the following link:

https://drive.google.com/open?id=1cPpDSnXKm-Grh7yW8nU3EQq1skfVBBnm

Unzip the file and place the entire /data folder in the same folder as the script files. If you setup correctly, the scripts and data shoud be in the following structure:
- args.py
- train.py
- models.py
- layers.py
- util.py
- /data/char_emb.json
- /data/char2idx.json 
- /data/word_emb.json
- /data/word2idx.json
- /data/dev.npz
- /data/train.npz
- /data/test.npz
- /data/glove.840B.300d/glove.840B.300d.txt

If all the files are present, you're good to go.


## Train and evaluate

### 1. To train baseline model WITH character-level embedding, use this command:

    python train.py --name <label>

Example:
```shell script
python train.py --name baseline_char_embed
```

### 2. To train baseline model WITHOUT character-level embedding, use this command:

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
