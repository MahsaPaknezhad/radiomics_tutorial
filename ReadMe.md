# Tree Bark Identification Using Radiomics 
Since the term radiomics was first coined in 2012, it has widely been used for medical image analysis. Radiomics is a method that automatically extracts a large of number of different features from medical images. These features have been able to uncover characteristics that can differentiate tumoral tissue from normal tissue and tissue at different stages of cancer.

In this repository, we aim to show that radiomic features can be useful for analysis of images in other domains as well. As a example, we show that radiomic features can be used for tree bark identification. We use a public dataset of tree bark images available [here](https://www.vicos.si/resources/trunk12/). All the code is provided in the notebook file: 

```tree_bark_analysis.ipynb```

## Evaluation results
Radiomic features were extracted from bark images and normalized to the range [0,1]. Below, we have shown the precision-recall curve for different classification models applied on the acquired radiomic features after normalization. We have compared our results with those of the paper [Boudra et al, 2018] for this dataset. Boudra et al. propose a novel texture descriptor and use this sescriptor to guide classification of tree bark images.

XGBoost  | SVM | Random Forest
:-------------:|:-------------:|:-------------:
<img src="plots/prec_recall_xgboost_crop_s_3000_new_s_256.png" width="160">  | <img src="plots/prec_recall_svm_crop_s_3000_new_s_256.png" width="160">  | <img src="plots/prec_recall_rf_crop_s_3000_new_s_256.png" width="160">

Linear Regression | SGD  | Boudra et al. 2018
:-------------:|:-------------:|:-------------:
<img src="plots/prec_recall_lr_crop_s_3000_new_s_256.png" width="160"> | <img src="plots/prec_recall_sgd_crop_s_3000_new_s_256.png" width="160"> | <img src="plots/prec_recall_boudra.png" width="160">

## Other evaluation metric

In the following table, we compare the performance of each classification model using multiple metrics: 

Classifier | XGBoost |SVM | Random Forest | LinearRegression | SGD | Boudra et al.
Precision | 0.656 | 0.699 | 0.579|0.686|0.485| -
Recall | 0.656 | 0.699|0.579|0.686|0.485| -
Accuracy | 0.656 | 0.699|0.579|0.686|0.485| 0.677
AUC | 0.933 | 0.952|0.905|0.945| - |
F1 | 0.656 | 0.699|0.579|0.686|0.485| -

# Reference 
```
@inproceedings{boudra2018bark,
  title={Bark identification using improved statistical radial binary patterns},
  author={Boudra, Safia and Yahiaoui, Itheri and Behloul, Ali},
  booktitle={2018 International conference on content-based multimedia indexing (CBMI)},
  pages={1--6},
  year={2018}
}
```