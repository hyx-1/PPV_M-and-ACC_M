# 1. ClusterONE reproduction: 
First come to the http://www.paccanarolab.org/cluster-one/ website to download the Java archive (1.0), attention in advance good configuration Java
environment, Locate the directory where you downloaded the jar package named cluster_one-1.0.jar, place the files you need to reproduce in the same 
directory, enter the cmd interface, and run the "$java-jar cluster_one.jar input file.txt" to get the corresponding results.

# 2. AdaPPI reproduction: 
*	dataset/ contains the PPI network dataset file;
*	evaluator/ contains the evaluations of protein functional modules (compare_performance.py);
*	model/ contains:
    * the implementation of the adaptive graph convolution network based on core-attachment method (adappi_model.py);
    * the implementation of AGC based on core-attachment method(protein_agc_model.py);
    * the implementation of the core-attachment method(core_attachment.py);
    * adappi/ contains:
        * the implementation of self-supervision in loss function (loss_estimator.py);
        * the implementation of the adaptive graph convolution network (repres_learner.py);
        * preparing to train the adaptive graph convolution network (trainer.py);
* util/ contains data preprocessing of PPI network dataset (data_processor.py);
* supplementary_files/ contains the p-value of (predicted but unmatched) potential candidate protein functional modules in two tables calculated by GOTermFinder tool.
Finally, sets all hyperparameters and may be used to execute a full training run on PPI network dataset.
Modify the dataset you want to run according to the github reference documentation in the following section:

<div align=center>
<img width="461" alt="1740905912948" src="https://github.com/user-attachments/assets/ac1d6d50-38f9-48be-b98d-d8c5d89d6bb0" />  
</div>

After making these changes, run "$python model/adappi_model.py" in the terminal to get the results/.

# 3. PC2P reproduction:
PC2P is a network clustering algorithm that can be used to find protein complexes from protein-protein interaction networks (PPIN).
PC2P is written in 2 formats: sequential and parallel.
The parallel version is implemented in python using 2 packages: Ray and Multiprocess. The Ray implementation runs on Mac and Linux systems, but for Windows computers, you can use the Multiprocess implementation.
To run the program, you need to call one of these implementations and pass your network to the function.
Modify the input data set in the following sections:

<div align=center>
<img width="460" alt="1740906806612" src="https://github.com/user-attachments/assets/574c77ae-dc3c-4c00-a338-0f35def3dab1" />  
</div>

Select the version to use in the following sections:

<div align=center>
<img width="460" alt="1740906869532" src="https://github.com/user-attachments/assets/8e1a5481-3bd7-48eb-a862-e84ff2a7600b" />  
</div>

We use the sequential version. Modify the corresponding data set and version, and type "python main_Function.py" into the terminal.

# 4.Run
Create a new folder 'Baseline' and inside that create new folders for each algorithm with the algorithm name. Place the output of the algorithm in each subfolder and call it 'dataset name.txt'. Then modify test_baseline.py accordingly and run it.
