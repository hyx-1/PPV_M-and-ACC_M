1.ClusterONE reproduction: 
First come to the http://www.paccanarolab.org/cluster-one/ website to download the Java archive (1.0), attention in advance good configuration Java environment, Locate the directory where you downloaded the jar package named cluster_one-1.0.jar, place the files you need to reproduce in the same directory, enter the cmd interface, and run the $java-jar cluster_one.jar input file.txt to get the corresponding results.

2.AdaPPI reproduction: 
•	dataset/ contains the PPI network dataset file;
•	evaluator/ contains the evaluations of protein functional modules (compare_performance.py);
•	model/ contains:
  ••	the implementation of the adaptive graph convolution network based on core-attachment method (adappi_model.py);
  ••	the implementation of AGC based on core-attachment method(protein_agc_model.py);
  ••	the implementation of the core-attachment method(core_attachment.py);
  ••	adappi/ contains:
    •••	the implementation of self-supervision in loss function (loss_estimator.py);
    •••	the implementation of the adaptive graph convolution network (repres_learner.py);
    •••	preparing to train the adaptive graph convolution network (trainer.py);
•	util/ contains data preprocessing of PPI network dataset (data_processor.py);
•	supplementary_files/ contains the p-value of (predicted but unmatched) potential candidate protein functional modules in two tables calculated by GOTermFinder tool.
Finally, sets all hyperparameters and may be used to execute a full training run on PPI network dataset.
Modify the dataset you want to run according to the github reference documentation in the following section:
<img width="461" alt="1740905912948" src="https://github.com/user-attachments/assets/ac1d6d50-38f9-48be-b98d-d8c5d89d6bb0" />

