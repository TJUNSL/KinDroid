# KinDroid: A Self-Adaptive Incremental Learning to Combat Concept Drift of Android Malware Families

## Introduction

The growing prevalence of Android malware highlights the critical need for effective classification and identification to ensure security. However, the emergence of new malware families introduces changes in malware characteristics, posing significant challenges for existing models in identifying new threats—a phenomenon known as concept drift. Current solutions often rely on full model retraining to address this issue, which is both time-intensive and dependent on large quantities of labeled data. To tackle these challenges, we propose KinDroid, a novel framework that leverages adaptive multi-teacher knowledge distillation for the incremental classification of Android malware families. KinDroid dynamically expands model representations, enabling accurate classification of known families while efficiently learning new families using only a small number of samples. The framework mitigates potential redundancy during dynamic model expansion by freezing previous representations, introducing new feature dimensions, and applying model pruning after completing the knowledge distillation process. We conduct rigorous evaluations of KinDroid on three datasets. After completing 10 incremental tasks, KinDroid achieves average accuracies of 99.79\%, 77.23\%, and 72.80\%, significantly outperforming state-of-the-art methods. The experimental results indicate that KinDroid successfully retains knowledge of previous categories while effectively learning new malware families, reducing the impact of concept drift.



![](framwork.png)

## How To Use

### Run experiment


1. Edit the [MODEL NAME].json file for global settings.
2. Edit the hyperparameters in the corresponding  [MODEL NAME].py file (e.g., models/kindroid.py).
3. Run： python main.py --config=./exps/[MODEL NAME].json.  To run our method  python main.py --config=./exps/kindroid.json.


### Datasets

There are three Android malware datasets: one is a widely used Android malware family dataset (AMD), and the other two are based on VirusShare datasets (VirusShareImg and VirusShareYearsImg). The datasets can be accessed [**here**](https://drive.google.com/drive/folders/1zRYfso7YJlm8SooZtosUkVHpsZw5ICr_?usp=drive_link).


**Virusshare.zip** is the **VirusShareImg** dataset, and **Virusshareyear.zip** is the **VirusShareYearsImg** dataset.


### Run
Before proceeding with the experiment, set up how the dataset is loaded in utils/data_manager.py:

In the **_setup_data** method, see the comment.

### Acknowledgments
This work is based on [**PyCIL**](https://github.com/G-U-N/PyCIL).

### Contact
If you have any questions, please contact the author Hongpeng Bai (bai931214@tju.edu.cn).
