# ChestX-Det10-Dataset

ChestX-Det10 is a subset with instance-level box annotations of NIH ChestX-14 https://www.nih.gov/news-events/news-releases/nih-clinical-center-provides-one-largest-publicly-available-chest-x-ray-datasets-scientific-community. 

We select 3,543 images from NIH ChestX-14 and invite three board-certified radiologists to annotate them with 10 common categories of diseases or abnormalities. 

The 10 categories are Atelectasis, Calcification, Consolidation, Effusion, Emphysema, Fibrosis, Fracture, Mass, Nodule, Pneumothorax.

The format in annotation files are: "file_name": "xxx.png", "syms": [s1, s2, ...], "boxes": [[x1, y1, x2, y2], [x1, y1, x2, y2], ...]
x1, y1, x2, y2 are left, top, right, bottom coordinates of the bounding box.

Below is an example annotation of one sample:
{"file_name": "36199.png", "syms": ["Fibrosis", "Fibrosis"], "boxes": [[632, 721, 909, 969], [129, 611, 474, 909]]}

For image downloading, please visit http://resource.deepwise.com/xraychallenge/train_data.zip and http://resource.deepwise.com/xraychallenge/test_data.zip

If you need to use ChestX-Det10, please cite the paper: https://arxiv.org/abs/2006.10550
@misc{liu2020chestxdet10,
    title={ChestX-Det10: Chest X-ray Dataset on Detection of Thoracic Abnormalities},
    author={Jingyu Liu and Jie Lian and Yizhou Yu},
    year={2020},
    eprint={2006.10550},
    archivePrefix={arXiv},
    primaryClass={eess.IV}
}
, and the original paper: Wang, Xiaosong, et al. "Chestx-ray8: Hospital-scale chest x-ray database and benchmarks on weakly-supervised classification and localization of common thorax diseases." Proceedings of the IEEE conference on computer vision and pattern recognition. 2017.

If you want to evaluate your detection results, please use **eval.py**. The detection results of each test sample should be stored as a JSON file. The JSON file name needs to be the same as the Image file name. For example, 10000.png corresponds to 10000.json. The format in each JSON file is [{“nodule”: [x1, y1, x2, y2, score]}, {“mass”: [x1, y1, x2, y2, score]}, …]. x1, y1, x2, y2 are left, top, right, bottom coordinates of the bounding box. All JSON files should be put in one folder.

For evaluation, using recall (sensitivity) at fixed false positives per image as the main criteria. The threshold of positive sample IOU is set to 0.5. In **eval.py**, the rates of instance-level FP/image are set to 0.05, 0.1 and 0.2. Moreover, the *avgrecall* is the average of recall@0.05fp, recall@0.1fp and recall@0.2fp. 
