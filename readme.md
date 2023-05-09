# How Robust are Audio Embeddings for Polyphonic Sound Event Tagging?

## Reference

This jupyter notebook reproduces all experiments and figures for the article:

**Jakob Abeßer, Sascha Grollmisch, Meinard Müller, How Robust are Audio Embeddings for Polyphonic Sound Event Tagging? (2022)**

## How to reproduce experiments / figures?

* download supplementary data from [https://zenodo.org/record/7912746](https://zenodo.org/record/7912746) and store files in the ```data``` subfolder, here's the list of required files:

  * all_emb.p - md5:88b01701429904b8f5aa2b6338f51f54 -	2.2 GB
  * class_id.npy - md5:960d8f50da888ef4e7b8b003c505a544 - 16.1 kB
  * class_labels.p - md5:4e686fd87b8d96a87400598bdf98e8f7 -	810 Bytes
  * prefix_list.p - md5:f3e7f9f04ac220950d74f53847951c87 -	926.0 kB

* install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) on your system

* create a new conda environment including the following packages with the defined versions

```
python version: 3.7.4
jupyter version: 1.0.0
numpy version:  1.18.5
librosa version:  0.8.1
pandas version:  1.3.1
matplotlib version:  3.4.3
tensorflow version:  2.3.0
```

* activate conda environment

* run ```jupyter notebook```

* open ```article_2023_reproduction.ipynb``` and run all cells

* result figures will be stored in ```results``` folder

## Details on extracted embeddings

* [Details on extracted embeddings](embedding_details.md)

## ESC50Mix dataset

* The dataset has been published at https://zenodo.org/record/7913031
