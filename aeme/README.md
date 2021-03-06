# Autoencoded Meta-Embedding

## File listing

+ __model.py__ The main implementation of Autoencoded Meta-Embeddings
+ __run.py__ Scripts used to launch the training of AEMEs
+ __utils__ Including some useful scripts
    + __corrector.py__ Scripts used to correct user inputs with regex
    + __logger.py__ A tool to keep logging in disc and command line
    + __utils.py__ Scripts used for large-scale data I/O

## Instructions on AEME training

Start training by:

    pip install -r requirements.txt
    python run.py -m AAEME -i ~/data/CBOW.txt ~/data/GloVe.txt -d 300 300 -o ~/results/res.txt

Required parameters:

+ __-i__ path of source embeddings
+ __-o__ path of yielded meta-embedding
+ __-m__ the model to train, within (DAEME, CAEME, AAEME)
+ __-d__ the dimensionality of each source embedding

Tune hyperparameters:

+ __-r__ learning rate, default 0.001
+ __-b__ batch size, default 128
+ __-e__ number of epoches, default 500
+ __-a__ activation function, default relu
+ __-n__ ratio of noise, default 0.05
+ __-f__ loss function coefficients
+ __--embed-dim__ the dimensionality of embeddings when applying AAEME, default 300

Set path parameters:

+ __--log-path__ the directory of log, default ./log/
+ __--ckpt-path__ the directory to store checkpoint file, default ./checkpoints/

Set boolean parameters:

+ __--oov__ whether to deal with OOV (not pre-processing, just padding missing words with zeros), default False
+ __--restore__ whether restore saved checkpoint, default False
+ __--cpu-only__ whether use cpu only or not, default False
