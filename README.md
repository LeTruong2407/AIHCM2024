# Multi-User Video Search: Bridging the Gap Between Text and Embedding Queries
[Khai Trinh Xuan](https://github.com/trinhxuankhai), [Nguyen Nguyen Khoi](https://github.com/nguyen-brat), [Huy Luong-Quang](https://github.com/WMumei), [Sang Hoa-Xuan](https://github.com/HXSang), [Anh Nguyen-Luong-Nam](https://github.com/namanh2k2av), [Minh-Hung An](https://github.com/anminhhung)

**SOICT 2023** [[`Paper`](https://dl.acm.org/doi/10.1145/3628797.3628957)]

## Pipeline
<img src="./figs/pipeline.jpg" alt="image" style="zoom:50%;" />

## Dataset preparation
Dataset structure:
```
|- dict 
   |- ...
   |- faiss_clip_cosine.bin
   |- faiss_clipv2_cosine.bin
|- frontend
   |- ai
   |   |- public
   |   |   |- data
   |   |   |   |- KeyFrames
   |   |   |   |   |-L01
   |   |   |   |   |-L01_extra
   |   |   |   |   |-....
```

### Dict
Download dict zip file: [dict](https://drive.google.com/file/d/1QbLLyBb60JD-dhdN9aIYnULFf8mchLVX/view?usp=sharing)




## Dataset extraction
Detailed on dataset extraction: [data](dataset_extraction/README.md)

## Installation
- ### Backend
```
conda create -n AIChallenge2023
conda activate AIChallenge2023
pip install git+https://github.com/openai/CLIP.git
pip install -r requirements.txt
```

- ### Frontend
Install nodejs: https://nodejs.org/en/download
```
npm install

npm install next react react-dom

```

- ### DB Sever
```
pip install flask
pip install flask-cors
pip install flask-socketio
pip install pyngrok==4.1.1
ngrok authtoken your_token # Add your ngrok authentication
```

## Usage
It is recommended to configure the environment using Anaconda. Linux support only.

- ### Backend
Using local machine, from root of repo:
```
python app.py
```
Using colaboratory, run appNotebook (App section) for starting the backend.

- ### Frontend
Change url in frontend/ai/src/helper/web_url.js. 
```
cd frontend/ai/
npm run dev
```

- ### DB Sever
Open 2 terminal and run:
```
python appStorage.py
```
```
ngrok http 5000
```

- ### Interface
<img src="./figs/interface.jpg" alt="image" style="zoom:50%;" />

## Citation
If you have any questions, please leave an issue or contact us: trinhxuankhai2310@gmail.com
```
@inproceedings{10.1145/3628797.3628957,
author = {Trinh Xuan, Khai and Nguyen Khoi, Nguyen and Luong-Quang, Huy and Hoa-Xuan, Sang and Nguyen-Luong-Nam, Anh and An, Minh-Hung and Nguyen, Hong-Phuc},
title = {Multi-User Video Search: Bridging the Gap Between Text and Embedding Queries},
year = {2023},
isbn = {9798400708916},
publisher = {Association for Computing Machinery},
address = {New York, NY, USA},
url = {https://doi.org/10.1145/3628797.3628957},
doi = {10.1145/3628797.3628957},
abstract = {Video search is a crucial task in the modern era, as the rapid growth of video platforms has led to an exponential increase in the number of videos on the internet. Effective video management is therefore essential. Significant research has been conducted on video search, with most approaches leveraging image-text retrieval or searching by object, speech, color, and text in images. However, these approaches can be inefficient when multiple users search for the same query simultaneously, as they may overlap in their search spaces. Additionally, most video search systems do not support complex queries that require information from multiple frames in a video. In this paper, we propose a solution to these problems by splitting the search space for different users and ignoring images that have already been considered by other users to avoid redundant searches. To address complex queries, we split the query and apply a technique called forward and backward search.},
booktitle = {Proceedings of the 12th International Symposium on Information and Communication Technology},
pages = {923–930},
numpages = {8},
keywords = {embedding-based search, interactive video retrieval, multi-user search engine, multimedia and multimodal retrieval, text-based search},
location = {Ho Chi Minh, Vietnam},
series = {SOICT '23}
}
```
