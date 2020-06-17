# ChestX-Det10-Dataset

ChestX-Det10 is a subset with instance-level box annotations of NIH ChestX-14 https://www.nih.gov/news-events/news-releases/nih-clinical-center-provides-one-largest-publicly-available-chest-x-ray-datasets-scientific-community. 

We select 3,543 images from NIH ChestX-14 and invite three board-certified radiologists to annotate them with 10 common categories of diseases or abnormalities. 

The 10 categories are Atelectasis, Calcification, Consolidation, Effusion, Emphysema, Fibrosis, Fracture, Mass, Nodule, Pneumothorax.

The format in annotation files are: "file_name": "xxx.png", "syms": [s1, s2, ...], "boxes": [[x1, y1, x2, y2], [x1, y1, x2, y2], ...]
x1, y1, x2, y2 are left, top, right, bottom coordinates of the bounding box.

Below is an example annotation of one sample:
{"file_name": "00000042_006.png", "syms": ["Fibrosis", "Fibrosis"], "boxes": [[632, 721, 909, 969], [129, 611, 474, 909]]}

For image downloading, please goes to https://nihcc.app.box.com/v/ChestXray-NIHCC
