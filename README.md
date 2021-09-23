# Do we Know What We Don't Know? 
Studying Unanswerable Questions beyond SQuAD 2.0

Repository for the paper:
          
          Do We Know What We Don't Know? Studying Unanswerable Questions beyond SQuAD 2.0
          Elior Sulem, Jamaal Hay and Dan Roth
          Findings of EMNLP 2021
        
## 1. Datasets

### Existing Datasets Used in the paper:

* SQuAD 2.0
  - [Train Set](https://rajpurkar.github.io/SQuAD-explorer/dataset/train-v2.0.json)
  - [Dev Set](https://rajpurkar.github.io/SQuAD-explorer/dataset/dev-v2.0.json)
* MNLI 
  - [Train Set](GLUE_DATA/MNLI/train.tsv)
  - [Dev Set](GLUE_DATA/MNLI/dev_matched.tsv)

Script for downloading GLUE_DATA: https://gist.github.com/W4ngatang/60c2bdb54d156a41194446737ce03e2e

Link for MNLI (Matched) data alone: https://dl.fbaipublicfiles.com/glue/data/MNLI.zip

### New Dataset (released in this repository):

* ACE-whQA
The corpus is in SQuAD 2.0 format so it can be used with the same code.
  - Has Answer: **DATA/ACE-whQA/ACE-whQA-has-answer.json**
  - Compet. IDK: **DATA/ACE-whQA/ACE-whQA-IDK-competitive.json**
  - Non-Compet. IDK: **DATA/ACE-whQA/ACE-wkQA-non-competitive.json**

## 2. Pretrained Models

* Extractive QA:

  - [SQuAD 2.0 baseline](https://drive.google.com/drive/folders/1AOy4vJUqmBknzgrNUR1UyLWsdgzZOEZx?usp=sharing)
  
  - [Additional pretraining on MNLI](https://drive.google.com/drive/folders/1HXrEstlj_HFvV1xJco485PReQvUvNCpk?usp=sharing)

  - [Additional pretraining on c(MNLI)](https://drive.google.com/drive/folders/1qW49KLdgI58H56vJ1FOOgyW9MnejuhSJ?usp=sharing)
  
 ## 3. Commands for Training and Testing on SQuAD 2.0 and MNLI:


* Setting: TensorFlow using Google Cloud and a single TPU (v2.8)

* Creating a virtual environment: 
                    
                    pip install virtualenv   #install virtualenv
                    
                    mkdir IDK-Beyond-SQuAD2.0-exeriments

                    cd IDK-Beyond-SQuAD2.0-exeriments
                    
                    virtualenv venv           #create environment
                    
                    source venv/bin/activate  #activate environment
                  
* Installing requirements:  
                     
                      pip install tensorflow==1.15
                      
                      pip install bert-tensorflow

                      pip install --upgrade google-api-python-client
                     
                      pip install --upgrade oauth2client
 
  
 * Downloading BERT LARGE CASED model: https://storage.googleapis.com/bert_models/2018_10_18/cased_L-24_H-1024_A-16.zip
 
   The.zip file contains three items:
   
                   A TensorFlow checkpoint (bert_model.ckpt) containing the pre-trained weights (which is actually 3 files).
      
                   A vocab file (vocab.txt) to map WordPiece to word id.
       
                   A config file (bert_config.json) which specifies the hyperparameters of the model.
                   
   It should be unzipped to some directory $BERT_MODEL.
   
   * Code: https://github.com/google-research/bert
 
      - MNLI: https://github.com/google-research/bert#sentence-and-sentence-pair-classification-tasks

      - SQuAD 2.0: https://github.com/google-research/bert#squad-20
        
