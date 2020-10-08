# IFN646 Project: COVID-19 X-ray Classification

This is a repository for IFN646: Biomedical Data Science Project under Semester 2, 2020 from Queensland University of Technology. The goal of this project is to build a classifier that will be able to classify the chest X-ray images into three categories: Normal, Pneumonia or COVID-19. Project contributors are:

* [Atif Ibne Zoha Sreezon][atif-github]
* [Bahareh Shahrestanaki][bahar-github]
* Nahid Ebrahimi

## Requirements
There are two environment files (.yml) in the repository, named 'envbiopy.yml' and 'envcovidnet.yml'. The first one contains the necessary packages with required versions to run the project notebook. The second one is for generating the dataset. Details instructions for generating the dataset is given in the next section.
Project Requirements:
* numpy
* h5py
* sklearn
* cv2
* tqdm
* jupyter notebook/lab

To create the environment using the yml file, please run the following command from your conda prompt: `conda env create -f envbiopy.yml`

## X-ray Image Data Source
The image dataset for this project has been procured from the open-access COVID-19 X-RAY (CXR) dataset under the [COVID-Net project](https://github.com/lindawangg/COVID-Net/blob/master/docs/COVIDx.md). The minimum requirements for generating the dataset are:

* OpenCV 4.2.0
* Python 3.6+
* Numpy
* Scikit-Learn
* Matplotlib
* PyDicom
* Pandas
* Jupyter

### Environment for generating the dataset
The environment we used to generate the dataset has been uploaded to our git-repository, named 'envcovidnet.yml'. To use this to create an environment, please run the following command from your conda prompt: `conda env create -f envcovidnet.yml`

### Image data sources
The current COVIDx dataset is constructed by the following open source chest radiography datasets:

* https://github.com/ieee8023/covid-chestxray-dataset
* https://github.com/agchung/Figure1-COVID-chestxray-dataset
* https://github.com/agchung/Actualmed-COVID-chestxray-dataset
* https://www.kaggle.com/tawsifurrahman/covid19-radiography-database
* https://www.kaggle.com/c/rsna-pneumonia-detection-challenge (which came from: https://nihcc.app.box.com/v/ChestXray-NIHCC)

### Steps to generate the dataset
1. Clone the COVID-Net repository to your local machine: `git clone https://github.com/lindawangg/COVID-Net.git`
2. Download the datasets listed above
 * `git clone https://github.com/ieee8023/covid-chestxray-dataset.git`
 * `git clone https://github.com/agchung/Figure1-COVID-chestxray-dataset.git`
 * `git clone https://github.com/agchung/Actualmed-COVID-chestxray-dataset.git`
 * go to this [link](https://www.kaggle.com/tawsifurrahman/covid19-radiography-database) to download the COVID-19 Radiography database. Only the COVID-19 image folder and metadata file is required. The overlaps between covid-chestxray-dataset are handled
 * go to this [link](https://www.kaggle.com/c/rsna-pneumonia-detection-challenge/data) to download the RSNA pneumonia dataset
3. Create a `data` directory and within the data directory, create a `train` and `test` directory
4. Use [create\_COVIDx\_v3.ipynb](../create_COVIDx_v3.ipynb) to combine the three dataset to create COVIDx. *Make sure to remember to change the file paths*.
5. We provide the train and test txt files with patientId, image path and label (normal, pneumonia or COVID-19). The description for each file is explained below:
 * [train\_COVIDx2.txt](../train_COVIDx3.txt): This file contains the samples used for training COVIDNet-CXR.
 * [test\_COVIDx2.txt](../test_COVIDx3.txt): This file contains the samples used for testing COVIDNet-CXR.

### COVIDx data distribution

Chest radiography images distribution
|  Type | Normal | Pneumonia | COVID-19 | Total |
|:-----:|:------:|:---------:|:--------:|:-----:|
| train |  7966  |    5459   |   473    | 13898 |
|  test |   100  |     100   |   100    |   300 |

Patients distribution
|  Type | Normal | Pneumonia | COVID-19 |  Total |
|:-----:|:------:|:---------:|:--------:|:------:|
| train |  7966  |    5444   |    320   |  13730 |
|  test |   100  |      98   |     74   |    272 |


[atif-github]: https://github.com/atif-sreezon
[bahar-github]: https://github.com/baharSh