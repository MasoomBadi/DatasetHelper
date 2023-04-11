# DatasetHelper
List of small components written in python, that helps you to ease the task.

## List of components
* Dataset Splitter - Splits Dataset in Train, Test and Validation Dataset Randomly (80:10:10) ratio
* CSV Generator - Generates a CSV file from Pascal VOC dataset.
* TFRecord Generator - Generates TFRecord from CSV file of Pascal VOC dataset.

## Usage

* ### Dataset Splitter

Steps to split the PASCAL VOC dataset in Colab.

Sample dataset structure would look like:

```
images.zip
  -- img1.jpg
  -- img1.xml
  -- img2.jpg
  -- img2.xml
  ...
```

1. Make the image dir

```
!mkdir /content/images
```

2. (Optional) Unzip if your dataset is in zip compressed folder. (Note: If you have unzipped dataset, make sure all your files are in '/images/all' directory)

```
!unzip -q images.zip -d /content/images/all
```
3. Make Directories for Test, Train and Validation

```
!mkdir /content/images/train; mkdir /content/images/test; mkdir /content/images/validation
```

4. Import the DatasetSplitter.py file

```
!wget https://raw.githubusercontent.com/MasoomBadi/DatasetHelper/main/DatasetSplitter.py
```

5. Run the python file.

```
!python DatasetSplitter.py
```

* ### CSV Generator & TFRecord Generator

Once you have your dataset ready, execute these script to generate the CSV file from Pascal VOC dataset and create a TFRecord file from it.

1. Get the scripts.

```
!wget https://raw.githubusercontent.com/MasoomBadi/DatasetHelper/main/CSVGenerator.py
!wget https://raw.githubusercontent.com/MasoomBadi/DatasetHelper/main/TFRecordGenerator.py
```

2. Run the files to create a TFRecord.

```
!python3 CSVGenerator.py
!python3 TFRecordGenerator.py --csv_input=images/train_labels.csv --labelmap=labelmap.txt --image_dir=images/train --output_path=train.tfrecord
!python3 TFRecordGenerator.py --csv_input=images/validation_labels.csv --labelmap=labelmap.txt --image_dir=images/validation --output_path=val.tfrecord
```
