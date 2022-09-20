# Multilingual Keyphrase Generation

Code \& Dataset for our NAACL 2022 Findings paper: Retrieval-Augmented Multilingual Keyphrase Generation with Retriever-Generator Iterative Training https://aclanthology.org/2022.findings-naacl.92/

The dataset is released under [CDLA-Permissive-2.0](https://cdla.dev/).

If you use our data, please cite our paper as follows:

```
@inproceedings{gao-etal-2022-retrieval,
    title = "Retrieval-Augmented Multilingual Keyphrase Generation with Retriever-Generator Iterative Training",
    author = "Gao, Yifan  and
      Yin, Qingyu  and
      Li, Zheng  and
      Meng, Rui  and
      Zhao, Tong  and
      Yin, Bing  and
      King, Irwin  and
      Lyu, Michael",
    booktitle = "Findings of the Association for Computational Linguistics: NAACL 2022",
    month = jul,
    year = "2022",
    address = "Seattle, United States",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2022.findings-naacl.92",
    doi = "10.18653/v1/2022.findings-naacl.92",
    pages = "1233--1246",
    abstract = "Keyphrase generation is the task of automatically predicting keyphrases given a piece of long text. Despite its recent flourishing, keyphrase generation on non-English languages haven{'}t been vastly investigated. In this paper, we call attention to a new setting named multilingual keyphrase generation and we contribute two new datasets, EcommerceMKP and AcademicMKP, covering six languages. Technically, we propose a retrieval-augmented method for multilingual keyphrase generation to mitigate the data shortage problem in non-English languages. The retrieval-augmented model leverages keyphrase annotations in English datasets to facilitate generating keyphrases in low-resource languages. Given a non-English passage, a cross-lingual dense passage retrieval module finds relevant English passages. Then the associated English keyphrases serve as external knowledge for keyphrase generation in the current language. Moreover, we develop a retriever-generator iterative training algorithm to mine pseudo parallel passage pairs to strengthen the cross-lingual passage retriever. Comprehensive experiments and ablations show that the proposed approach outperforms all baselines.",
}
```

## Code

https://github.com/amzn/multilingual-keyphrase-generation

## Dataset in E-Commerce Domain (EcommerceMKP)

A multilingual keyphrase generation dataset on the e-commerce domain, built on Amazon product data. It includes (`passage`, `keyphrases`) pairs in Spanish, French, German and Italian. 

We have splitted the dataset into train, dev and test set (`./e-commerce/<split>.json`).
Each instance in our dataset is in the `jsonl` format including the following entries:

- `id`: the unique id for the instance, it is the md5 hashing result of the product ASIN id.

- `title`: the title of the product.

- `context`: the passage description of the product.

- `keywords`: the keywords of the product.

- `lang`: the language of current instance.

In addition, we provide the Amazon English keyphrase generation dataset (`./e-commerce/en.json`) for experimental replication purpose.
The instances in the `en.json` are of the same format with our multilingual dataset. The product appears in different languages share the same `id`.

## Dataset in Academic Domain (AcademicMKP)

A multilingual keyphrase generation dataset on the academic domain, built on Microsoft Academic Graph. It includes (`passage`, `keyphrases`) pairs in Korean and Chinese. 

We have splitted the dataset into train, dev and test set (`./academic/<split>.json`).
Each instance in our dataset is in the `jsonl` format including the following entries:

- `asin`: the unique id for the instance.

- `context`: the passage description of the product.

- `keywords`: the keywords of the abstract.

- `lang`: the language of current instance.

In addition, we provide the our processed [KP20K](https://github.com/memray/OpenNMT-kpg-release) (`./academic/en.json`) for experimental replication purpose.