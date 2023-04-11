# DatasetHelper
List of small components written in python, that helps you to ease the task.

## List of components
* Dataset Splitter - Splits Dataset in Train, Test and Validation Dataset Randomly (80:10:10) ratio

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

2. (Optional) Unzip if your dataset is in zip compressed folder.

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

