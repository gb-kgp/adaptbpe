This is the official codebase for the EMNLP submission titled: Adaptive BPE Tokenization for Enhanced Vocabulary Adaptation in Finetuning Pretrained Language Models.

Here we give the modeified tokenization files specific to the models: RoBERTA and BART. Inside the files we have marked the changes that we have made explicity over the original file so that you can undo them to switch to default tokenization for comparison.

The file tokenization_bart.py is originally present [here](https://github.com/huggingface/transformers/blob/main/src/transformers/models/bart/tokenization_bart.py) and file tokenization_roberta.py is present [here](https://github.com/huggingface/transformers/blob/main/src/transformers/models/roberta/tokenization_roberta.py) .In brief, we have made following changes in RoBERTa and BART:
  1. We create a new disctionary for added vocabulary to efficintly search longest substring in newly added vocab as explained in [tokenization_roberta.py](https://github.com/med-tools/adaptbpe/blob/main/tokenization_roberta.py#L200-L206) and [tokenization_bart.py](https://github.com/med-tools/adaptbpe/blob/main/tokenization_roberta.py#L193-L199).

  2. We add one function and two helper functions to conduct the longest match recursively based on implemenation of [FLOTA](https://github.com/valentinhofmann/flota). This is described in  [tokenization_roberta.py](https://github.com/med-tools/adaptbpe/blob/main/tokenization_roberta.py#L233-L282) and [tokenization_bart.py](https://github.com/med-tools/adaptbpe/blob/main/tokenization_roberta.py#L224-L272)

Pleaase use the following bib entry to cite this work
```
@inproceedings{balde-etal-2024-adaptive,
    title = "Adaptive {BPE} Tokenization for Enhanced Vocabulary Adaptation in Finetuning Pretrained Language Models",
    author = "Balde, Gunjan  and
      Roy, Soumyadeep  and
      Mondal, Mainack  and
      Ganguly, Niloy",
    editor = "Al-Onaizan, Yaser  and
      Bansal, Mohit  and
      Chen, Yun-Nung",
    booktitle = "Findings of the Association for Computational Linguistics: EMNLP 2024",
    month = nov,
    year = "2024",
    address = "Miami, Florida, USA",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2024.findings-emnlp.863/",
    doi = "10.18653/v1/2024.findings-emnlp.863",
    pages = "14724--14733"
}
```
