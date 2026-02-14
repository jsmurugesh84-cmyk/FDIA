<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/11e7e437-0e4d-4455-973a-4355f42114e6" />README

Manuscript Information

Name of the manuscript: Data-Driven Detection of False Data Injection Attacks in Smart Grids using Self-Attention Enabled Conditional GAN with Gradient Penalty;

Authors: S. Murugesan, Student Member, IEEE, Ram Jethmalani C.H, Member, IEEE, Navin Sam K, Member, IEEE, Venkadesan A, Senior Member, IEEE and Sadheesh Kumar S J, Senior Member, IEEE 

Affiliations: Department of Electrical and Electronics Engineering, National Institute of Technology Puducherry, Karikal 609609, India.

Submission ID:10238


Overview of the SACGAN-GP framework:
The proposed SACGAN-GP framework consists of four main components: Generator, Discriminator, Self-Attention Mechanism and Gradient penalty. The model follows an adversarial learning approach, where the Generator creates synthetic attack samples, and the Discriminator distinguishes between real and fake data. The self-attention mechanism enhances FDIA detection in power systems by capturing long-range dependencies and complex feature interactions within measurement data. Gradient Penalty ensures training stability and sharp decision boundaries, contributing to improved generalization on attack scenarios.



Repository Organization:

This repository provides the source code and datasets necessary to reproduce the experimental results presented in this paper “Data-Driven Detection of False Data Injection Attacks in Smart Grids using Self-Attention Enabled Conditional GAN with Gradient Penalty”.

├── data/
│ ├── IEEE14/
│ │ ├── train_ test_data.csv 
│ │ 
│ ├── IEEE118/
│ │ ├── train_ test_data.csv
│ │ 
│
├── src/
│ ├── data_preprocessing.py
│ ├── model.py
│ ├── train.py
│ ├── evaluate.py
│
├── results/
│ ├── metrics/ 
│ ├── figures/
│
├── requirements.txt
├── README.md


Description of Files and Directories

-data 
  Contains the generated CSV datasets used for training and testing. Separate folders are provided for the IEEE 14-bus and IEEE 118-bus systems.

- src/data_preprocessing.py
  Performs feature extraction, normalization, train–test splitting, and optional noise injection.

-src/model.py
  Implements the SACGAN-GP architecture, including the generator, discriminator, self-attention layer, and gradient penalty.

- src/train.py 
  Trains the SACGAN-GP model using the specified dataset and hyperparameters.

- src/evaluate.py 
  Evaluates the trained model and generates performance metrics.




- results/
  Stores generated plots and exported evaluation metrics.

- requirements.txt
  Lists all Python dependencies required to run the code.

Software Requirements

- Python 3.8 or later  
- TensorFlow 2.x  
- NumPy  
- Pandas  
- Scikit-learn  
- Matplotlib  

Instructions to run Python code from GitHub in Google Colab

1.	Go to Google Colab
2.	Click File → Open notebook
3.	Select GitHub tab
4.	Paste the GitHub repository URL
5.	Choose the .ipynb file and open

Dataset: 
To reproduce the results, please ensure the data is placed in the data/ directory. This directory should contain the generated CSV dataset files used for training and testing.

Source Code:

Proposed method: SACGAN-GP Model

Base line method: Isolation Forest,GAN, WGAN, CGAN

Dataset generation Method:

A simulated dataset was generated using the Panda power library. Power flow analyses were conducted using the Newton–Raphson method, and state estimation was carried out with the Weighted Least Squares (WLS) algorithm. The resulting system state variables were extracted from the measured data, including voltage magnitudes and phase angles.
Non-attacked data were produced by scaling the load demands at each bus to 25%, 50%, 75%, and 100% of their nominal values, with the corresponding voltage magnitudes and angles computed and stored as state variables. To simulate attacked data, FDIAs were introduced by modifying voltage magnitudes and angles by 5%–50% on selected buses (0, 1, and 5). Additionally, systematic angle deviations of up to 5° were applied to emulate coordinated attack strategies. 
Each data sample represents the electrical state of the system under specific operating conditions, consisting of 34 features (voltage, angle, and load information). 336 labelled samples were generated, divided into 268 for training (80%) and 68 for testing (20%). Of the test set, 55 correspond to non-attacked states and 13 to attacked states, introducing class imbalance consistent with realistic scenarios. Attacked data points were labelled as “1,” while normal samples were labelled as “0,” forming a binary classification framework suitable for FDIA detection. To emphasize the severity and stealthiness of FDIAs, small deviations such as 5%–50% in voltage magnitudes and up to 5° in angles were sufficient to significantly distort state estimation while remaining undetected by traditional BDD techniques. This study employs 336 samples for the IEEE 14-bus system and 2832 samples for the IEEE 118-bus system.

Dataset:

•	IEEE 14-bus system FDIA data set

•	IEEE 118-bus system FDIA data set
