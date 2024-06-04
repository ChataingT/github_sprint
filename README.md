# github_sprint

test  


## DiffVersify: a scalable approach to differentiable pattern mining though coverage regularization



This is the python implementation accompanying the paper *DiffVersify: a scalable approach to differentiable pattern mining though coverage regularization*.
The code is based on Fischer et al [1] and is available under the license GNU General Public License v3.0. We strongly recommend to run the code on a GPU.

### 1. Required packages
- pyTorch (1.12.1 for the results in the paper)
- numpy
- pandas
- scipy 
- torchmetrics 
- scikit-learn 
- matplotlib 
- seaborn 
- tqdm 
- tabulate 
- openpyxl 
- tensorboard

### 2. Folder organization
- **code:** Contains the code of our method, *diffversify*, and scripts to reproduce all the reults presented in the paper
- **data:** Data used for the experiments for real data. 
- **results:** Directory to store the results outputted by the scripts in **code**
- **appendix.pdf**: Contains appendix for the main paper 

### 3. Running experiments locally 
To run the experiments on **synthetic data**, the scripts `run_exp.py`allow to run all 4 synthetic experimennt and the real data one.
The parameter `--xp {xp}` define which experimennt to run :  
    1 :exp1 - scalability over the number of features  
    2 :exp2 - scalability over the number of classes  
    3 :exp3 - robustness to additive noise  
    4 :exp4 - robustness to destructive noise  
    5 :expR - real dataset   

For the xp 5 (real data) a second argument is necessary `--dataset` to specify over which dataset to run the real dataset experimennt. The available values are [cardio, disease, braca-n, brca-s].

ex : `$python3 real_exp.py --xp 5 -d cardio` ,

executes *diffversify* for the specified dataset. The results are saved to `results/real_results/`.

An optional `--output [FOLDER_PATH]` is available to compress and copy the results to a specified directory 

### 4. Running experiment over docker
A dockerfile is joined to run the experiment remotely or without installing dependency.
It is recommended to use the `--output` argument with a mounted folder to copy the results outside of the docker.



[1] Fischer, J.; and Vreeken, J. 2021. Differentiable pattern set mining.
    In Proceedings of the ACM International Conference on Knowledge Discovery and Data Mining (SIGKDD)
