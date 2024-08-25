# Functional Connectivity Regressor

This project aims to predict age based on functional connectivity derived from fMRI data using a deep learning approach by analyzing fMRI data during movie watching. The project leverages functional connectivity matrices extracted from fMRI data as input features for a neural network regressor.


### Project Overview

This project focuses on analyzing functional connectivity patterns derived from fMRI data using machine learning techniques. Functional connectivity refers to the temporal correlation between spatially distinct brain regions, providing insights into how different brain areas work together.


### Results
The importance of these brain region connections in predicting age reflects how different brain functions change over time:

1. **Intraparietal Sulcus - Cuneus**: Indicates changes in visuospatial attention and processing with age.
  
2. **Inferior Occipital Gyrus - Lingual Gyrus**: Reflects age-related shifts in visual perception and memory.

3. **Putamen - Postcentral Gyrus**: Shows how motor and sensory functions evolve with age.

4. **Calcarine Cortex - Cingulate Gyrus**: Highlights changes in visual processing linked to cognitive and emotional integration.

5. **Insula - Inferior Frontal Sulcus**: Suggests alterations in cognitive control and emotional regulation as we age.

![image](https://github.com/user-attachments/assets/91f089ed-80c7-4676-81b8-5b997ff7af11)


### Experimental Setup

1. **Data Acquisition and Preprocessing**:
   - **Data Source**: The data used is from the `development_fmri` dataset obtained via Nilearn, containing fMRI images and associated confound variables.
   - **Data Exploration**: Initial exploration includes loading and inspecting the dataset for functional and confound files, as well as participant demographics such as age and gender.

2. **Connectivity Analysis**:
   - **Atlas Definition**: Difumo atlas is used to define 64 brain regions of interest (ROIs) for extracting functional connectivity.
   - **Connectivity Estimation**: Nilearn's `MultiNiftiMapsMasker` is employed to extract time series from ROIs and `ConnectivityMeasure` computes correlation matrices to quantify connectivity.

3. **Machine Learning Model**:
   - **Feature Selection**: Features derived from connectivity matrices are used to predict participant age.
   - **Model Architecture**: A non-linear regression model is defined using PyTorch, optimized via Optuna for hyperparameters like hidden layer sizes, dropout rates, and learning rates.
   - **Training and Evaluation**: The model is trained using `AdamW` optimizer with early stopping based on validation loss, evaluated using MSE, MAE, and R² metrics.

4. **Findings and Insights**:
   - **Neuroscientific Insights**: Significant brain regions contributing to age prediction are identified through feature importance analysis using perturbation methods.
   - **Visualization**: Visualizations such as histograms, connectivity matrices, and feature importance plots provide intuitive insights into data patterns and model outcomes.

### Key Findings

1. **Functional Connectivity Patterns**:
   - Strong correlations between specific brain regions suggest coordinated activity networks.
   - Variations in connectivity strength across age groups indicate developmental changes in brain organization.

2. **Impact of Age on Connectivity**:
   - Age-related changes in connectivity metrics reflect ongoing neural maturation and functional specialization.
   - Differential patterns between children and adults highlight distinct stages of cognitive development and aging effects.

3. **Methodological Advancements**:
   - Integration of machine learning with neuroimaging allows for precise prediction of age from brain connectivity data.
   - Identification of critical brain regions underscores their roles in cognitive functions and developmental trajectories.

### Conclusion

This project demonstrates the integration of neuroimaging data analysis with machine learning techniques to uncover meaningful insights into brain connectivity and its relationship with age. By leveraging advanced tools and methodologies, it contributes to understanding neural mechanisms underlying human development and aging processes.

