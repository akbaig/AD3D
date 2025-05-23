A bachelor's thesis for ranking articulation disparity using **3D facial features** generated by deep learning models

## Video Explanation
https://github.com/user-attachments/assets/d4bf8590-ecc1-4de1-b2e0-9afb56d5ffc7

## GUI

![BS_FYP_SS](https://github.com/akbaig/Diagnosis-of-Articulation-and-Motor-Speech-Disorders/assets/57063370/fc07f0f2-c236-4e09-b87a-64ffd60d7c55)

## Requirements

* Python
* Conda

## Steps

* `git clone` this repository
* `git submodule init` and `git submodule update` to initialize the submodules
* Create conda environment `voca` & resolve [dependencies](voca/README.md#set-up) from voca directory
* Create conda environment `deca` & install [dependencies](deca/README.md#requirements) from deca directory
* Create conda environment `autoeditor` & run `pip install auto-editor`
* Create conda environment `pyqt` & run `pip install pyqt5`
* Activate `pyqt` environment and execute [speech app](pipeline/speechapp.py)

## How it works

1. User provides input in the form of video
2. Frame rate of input video is changed to 24
3. Silence part is removed
4. Duration is adjusted
5. Extract Audio from Video
6. Convert Video to Frames
7. Convert Frames to 3D Meshes
8. Compare 3D Meshes with Standard

## Generating standards

By default, this repository contains only one standard [stream](voca/preprocess_audios/standard/stream.wav). If you wish to add more standard words, perform the following steps:

* Make sure selenium is installed
* Place your desired words in [words.txt](audio_scraper/words.txt) file to scrape from online dictionary.
* Run [audio_scraper.py](audio_scraper/audio_scraper.py)
* Place scraped **mp3 files** into [standard audios](voca/preprocess_audios/standard/) folder
* Activate environment `voca`
* Run [preprocess_audios.py](voca/preprocess_audios.py)
* Run [generate_vertices.py](voca/generate_vertices.py)
* You should see your [standard's 3D Meshes](voca/generated_animations) generated by VOCA model
