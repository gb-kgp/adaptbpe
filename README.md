This is the official codebase for the EMNLP submission titled: Adaptive BPE Tokenization for Enhanced Vocabulary Adaptation in Finetuning Pretrained Language Models.

Here we give the modeified tokenization files specific to the models: RoBERTA and BART. Inside the files we have marked the changes that we have made explicity over the original file so that you can undo them to switch to default tokenization for comparison.

The file tokenization_bart.py is originally present [here](https://github.com/huggingface/transformers/blob/main/src/transformers/models/bart/tokenization_bart.py) and file tokenization_roberta.py is present [here](https://github.com/huggingface/transformers/blob/main/src/transformers/models/roberta/tokenization_roberta.py) .In brief, we have made following changes in RoBERTa and BART:
  1. We create a new disctionary for added vocabulary to efficintly search longest substring in newly added vocab as explained in [tokenization_roberta.py](https://github.com/med-tools/adaptbpe/blob/main/tokenization_roberta.py#L200-L206) and [tokenization_bart.py](https://github.com/med-tools/adaptbpe/blob/main/tokenization_roberta.py#L193-L199).

  2. We add one function and two helper functions to conduct the longest match recursively. This is described in  [tokenization_roberta.py](https://github.com/med-tools/adaptbpe/blob/main/tokenization_roberta.py#L233-L282) and [tokenization_bart.py](https://github.com/med-tools/adaptbpe/blob/main/tokenization_roberta.py#L224-L272)
