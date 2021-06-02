This repository is reproduction of the work done in paper: [Towards Fairness in Visual Recognition: Effective Strategies for Bias Mitigation](https://arxiv.org/abs/1911.11834v2)


Original Authors: Zeyu Wang, Klint Qinami, Ioannis Christos Karakozis, Kyle Genova, Prem Nair, Kenji Hata, Olga Russakovsky


## Requirements
* Python 3.6+
* PyTorch 1.0+
* h5py
* tensorboardX

## Data Preparation
First download and unzip the CIFAR-10 and CINIC-10 by running the script `download.sh`

Then manually download the [CelebA dataset](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html), put `Anno` into `data/celeba/Anno`, `Eval` into `data/celeba/Eval`, put all align and cropped images to `data/celeba/images`

Run the `preprocess_data.py` to generate data for all experiments (this step involves creating h5py file for CelebA images, so would take some time 1~2 hours)

### Changes

- In the original code, the certificate to download `cinic` data had expired. This issue has been resolved here by replacing it with chained certificate.
- There are exisitng issues in getting the complete CelebA dataset bcause of their size. This issue will be resolved in next update.

## Run Experiments
To conduct experiments, run `main.py` with corresponding arguments (`experiment` specifies which experiment to run, `experiment_name` specifies a name to this experiment for saving the model and result). For example:

```
python main.py --experiment cifar_color --experiment_name e1 --random_seed 1
```

After running, the experiment result will be saved under `record/experiment/experiment_name`
