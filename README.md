# cMolGPT 

Implementation of ["cMolGPT: A Conditional Generative Pre-Trained Transformer for Target-Specific De Novo Molecular Generation"](https://pubmed.ncbi.nlm.nih.gov/37298906/).
Enforcing target embeddings as queries and keys.

## Data

### [Mol_target_dataloader](https://github.com/alfredyewang/Mol_target_dataloader)
Please download this repo and put the folder in the root directory.

## How to run

*unzip train.sim.zip

### Train
```
  python3 main.py --batch_size 512 --mode train \
                  --path model_base.h5 
```
### Fine-tune
```
  python3 main.py --batch_size 512 --mode finetune \
                  --path model_base.h5 --loadmodel
```
*In the case of fine-tuning, the base model will be overwritten in place.

*You can change the number of targets in [model_auto.py](https://github.com/VV123/cMolGPT/blob/f0eba15dbf53b47a35afc305674c997354472590/model_auto.py#L58C66-L58C107).

### Infer/Generate
```
  python3 main.py --mode infer --target 2 --path model_finetune.h5
```
