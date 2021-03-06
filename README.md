## What’s in a Question: Using Visual Questions as a Form of Supervision

This is the code for the CVPR'17 spotlight paper, [**What’s in a Question: Using Visual Questions as a Form of Supervision**](https://arxiv.org/pdf/1704.03895.pdf). 

[[Arxiv](https://arxiv.org/pdf/1704.03895.pdf)] [[bib](http://sidgan.me/images/GanjuCVPR17.bib)] [[Github](https://github.com/sidgan/whats_in_a_question)] [[Project Page](http://sidgan.me/whats_in_a_question/)]


![What’s in a Question: Using Visual Questions as a Form of Supervision](https://github.com/sidgan/cvpr2017/blob/master/pullfig.png)

Abstract

>  Collecting fully annotated image datasets is challenging and expensive. Many types of weak supervision have been explored: weak manual annotations, web search results, temporal continuity, ambient sound, and others. We focus on one particular unexplored mode: visual questions that are asked about images. Our work is based on the key observation that the question itself provides useful information about the image (even without the answer being available). For instance, the question “what is the breed of the dog?” informs the computer that the animal in the scene is a dog and that there is only one dog present. We make three contributions: (1) we provide an extensive qualitative and quantitative analysis of the information contained in human visual questions, (2) we propose two simple but surprisingly effective modifications to the standard visual question answering models that allows it to make use of weak supervision in the form of unanswered questions associated with images, and (3) we demonstrate that a simple data augmentation strategy inspired by our insights results in a 7:1%
improvement on the standard VQA benchmark.


The trained models attain the following scores on the test-dev of the [MS COCO VQA v1.0 dataset](http://www.visualqa.org/). 

|Model Name| Overall| Other |Number |Yes/No|
|-|-|-|-|-|
|iBOWIMG-2x  | 62.80  | 53.11  |37.94 | 80.72|

There are three tasks described in the paper: 

### 1. Image Descriptions

We analyze whether the visual questions contain enough information to provide an accurate description of the image using the Seq2Seq model. See [Image Descriptions README](https://github.com/sidgan/cvpr2017/blob/master/image_descriptions/README.md) for detailed description for each file.

### 2. Object Classification

Visual questions can provide information about the object classes that are present in the image. E.g., asking “what color is the bus?” indicates the presence of a bus in the image. See [Object Classification README](https://github.com/sidgan/cvpr2017/blob/master/object_classification/README.md) for detailed description for each file.

#### Training/fine-tuning the image features (caffe)

Fine-tuning modifies only the last layer of a network to give the application-specific number of outputs. For fine-tuning we start with the parameters initially learnt on the ImageNet images, and then fine-tune with MS COCO images. All caffe related code for fine-tuning the models is present in the `caffe` directory. See [caffe README](https://github.com/sidgan/cvpr2017/blob/master/caffe/README.md) for detailed description for each file.

### 3. Visual Question Answering

Visual Question Answering is, given an image and a natural language question about the image, the task is to provide an accurate natural language answer. Visual questions focus on different areas of an image, including background details and underlying context. We utilize not just the target question, but also the unanswered questions about a particular image. See [Visual Question Answering README](https://github.com/sidgan/cvpr2017/blob/master/vqa/README.md) for detailed description for each file.

### Acknowldegements

This code is based on [Simple Baseline for Visual Question Answering](https://arxiv.org/pdf/1512.02167.pdf) by Bolei Zhou and Yuandong Tian.

Please cite us if you use our code:

```
@inproceedings{GanjuCVPR17,
author = {Siddha Ganju and Olga Russakovsky and Abhinav Gupta},
title = {What's in a Question: Using Visual Questions as a Form of Supervision},
booktitle = {CVPR},
year = {2017}
}
```

