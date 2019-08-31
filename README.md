# Graph-based Conceptual Complexity Assessment of Encyclopedia Texts for Schoolchildren
This repository contains data, code and results for my Individual Module at the Cognitive Systems M.Sc. of Potsdam University.

### Abstract 
The conceptual complexity of a text can be defined as the level of background knowledge necessary for understanding it. A system that automatically assesses conceptual complexity could be beneficial for the inclusion of certain low-level reader groups. In this project, I implement such a system using the graph-based features first described by Štajner and Hulpuş (2018) and evaluate it on encyclopedia texts designed for schoolchildren of three different age groups. The text graphs are created with the help of the DBPedia knowledge graph and the DBPedia Spotlight entity linker. A binary classification experiment, with the task of finding the more complex of two texts describing the same topic, achieves an accuracy of 0.88, while a three-way classification of all texts reaches 0.74. The features with the highest discriminative power quantify the number of topics in a sentence or paragraph and the importance of concepts in the text. I compare the results with the original experiment, which is conducted on news articles, and conclude that the features transfer well between the two studied domains.

### Reference
Sanja Štajner and Ioana Hulpuş. 2018.  Automatic assessment of conceptual text complexity using knowledge graphs. In
Proceedings of the 27th International Conference on Computational Linguistics, pages 318–330, Santa Fe, New Mexico, USA. Association
for Computational Linguistics.

### Short manual
All the code was tested with:
* Ubuntu 18.04
* Python 3.6.8
* jupyter-notebook 5.7.8
* Git Large File Storage (LFS) 2.8.0
* See further requirements in the requirements.txt file

The Newsela articles are found in the folder 'newsela' and the Britannica articles in the folder 'britannica.' All CSV files that the notebooks generate are placed in the csv folder. All visualizations that the notebooks generate are placed in the png folder.

The notebooks can be run in the numbered order and they contain information about their contents. Below is a short general description of the workflow. See in brackets the CSV files that the discussed notebooks generate.

1. The notebook 1.IM_create_DF.ipynb creates dataframes from  the texts (britannica.csv and newsela.csv)
2. The notebook 2.IM_add_graphs_to_DF.ipynb contains all steps needed to add the text graphs to the DF (britannica_with_graphs.csv, newsela_with_graphs.csv,  britannica_semrel_with_graphs.csv, britannica_sematch_with_graphs.csv) 
      * It also contains code for outlier removal with Sematch.
3. The notebook 3.IM_add_features_to_DF.ipynb contains code to add feature values to the DF (britannica_with_features.csv, newsela_with_features.csv, britannica_semrel_with_features.csv, britannica_sematch_with_features.csv)
      * It also contains code for outlier removal with Exclusivity-based Semantic Relatedness.
4. The notebook 4.IM_classification.ipynb shows classification results.
5. The notebooks 5.IM_visualize_graphs.ipynb and 6.IM_visualize_features.ipynb contain visualization experiments.
