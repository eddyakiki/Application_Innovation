# Application_Innovation
Prédiction des notes de films à l'aide de différents modèles NLP, entraînés sur la base de données Allo Ciné
# Prétraitement
Pour lancer le prétraitement pour générer le jeux de données A  il faut lancer le code du fichier pretraitement.ipynb sauf la fonction qui enlève les stop words marqué dans le fichier.   
Pour générer le jeux de données B Il faut décomenter les lignes de code indiqué dans la fonction text_preprocessing_pipeline et puis lancer tous le code.   
Pour générer le jeux de données C Il faut lancer tous les blocs de code dans le fichier prétraitement C.  
A est le jeu de données pour lequel nous n'avons pas supprimé les mots d'arrêt, les caractères spéciaux français et les apostrophes.   
B est le jeu de données pour lequel on a supprimé les mots d'arrêt et les caractères spéciaux français et les apostrophes.
C est le jeu de données pour lequel on a supprimé les caractères non alpha-numériques et on appliqué un stemming sur les tokens.
# SVM 
Pour modifier le jeu de données à utiliser, il suffit de changer le chemin dans les fonctions pd.read_csv().    
Pour lancer l'entraînement du SVM faut lancer tous les blocs de code dans le fichier testNLP.   
Le tableau ci-dessous montre les accuracy de validation des modèles entraînés sur les ensembles de données A et B.  
| A | B | 
| :---- | :----: | 
| 32% | 34% | 
# CNN
Pour modifier le jeu de données à utiliser, il suffit de changer le chemin dans les fonctions pd.read_csv().   
Pour lancer l'entraînement du modèle en utilisant word2vec ou fast text, il suffit d'exécuter les blocs de code sous leur titre respectif   après avoir généré les embeddings initiaux.   
Pour lancer le train de modèles utilisant keras tokenizer, il suffit d'exécuter les derniers blocs de code sous le titre keras tokenizer après avoir généré les embeddings initiaux.  
Le tableau ci-dessous montre les accuracy de validation des modèles entraînés sur les ensembles de données A et B en utilisant les différents types de embeddings.  
|  | A | B | 
| :---- | :----: | :----: | 
| Keras Tokenizer | 38% | 39% | 
| Word2Vec | 39,3% | 38% |
| Fast Text | 38,4% | 38,5% |
# MLP
En total il y a 5 model MLP 1 model entraîné en utilisant doc2vec. Pour l'entraîner il faut lancer tous les bloc de codes dans le fichiers MLP_doc2vec_A. L'accuracy de validation de ce model est de 16,33%.  
Pour entraîner les deux MLP sur A et B avec les méta données, en utilisant keras tokenizer text_to_sequence il faut lancer tous les bloc de code dans le fichier MLP_sur_AetB_avec_MetaData.  
Pour entraîner les deux MLP sur A et B sans les méta données, en utilisant keras tokenizer text_to_sequence il faut lancer tous les bloc de code dans le fichier MLP_sur_AetB_sans_MetaData.  
Le tableau ci-dessous montre les accuracy de validation de ces 4 modeles. 
|  | A | B | 
| :---- | :----: | :----: | 
| Avec Méta Data | 35.58% | 36.8% | 
| Sans Méta Data | 34,63% | 35,43% |
# Camembert
Le fichier Camembert_final_complete contient le code pour entraîner le model camembert. Pour lancer l'entraînement sur les deux différents jeux de données il suffit de changer le path de pd.read_csv() et lancer le code sans rien changer.  
Le tableau ci-dessous montre les accuracy de test des modèles camembert entraînés sur les ensembles de données A et B. 
|  | A | B | 
| :---- | :----: | :----: | 
| 10 Labels | 46,37% | 40,3% | 
| 3 Labels | 86,54% | 83,5% |
# LSTM 
Pour lancer l'entraînement des deux LSTM sur B un avec les méta données et l'autre sans les méta données, il faut lancer tous les blocs du fichier lstm_lstmbidirectionnel_sur_B_meta_data et les blocs du lstm unidirectionnel du fichier lstm_lstmbidirectionnel_sur_B_meta_data .  
L'accuracy de validation du model avec les méta données est de 37.01% et de l'autre model sans les méta données est de 38.2%.  
Pour entraîner l'LSTM bidirectionnel sur B avec les méta données il faut lancer les blocs du lstm bidirectionnel du fichier lstm_lstmbidirectionnel_sur_B_meta_data. L'accuracy de validation de ce model est de 38.8%.  
# Lexique Sentimentale
Il faut lancer tout les blocs de code du fichier lexique_sentimentale_stat, et vérifier que vous avez sauvgarder les trois fichier cvs de train test et dev avec la nouvelle colonne de polarité ainsi que les résultats de classement de la méthode naïve dans trois fichier text différents pour train test et dev.  
Vous pouvez ensuite lancer l'entraînement du model CNN avec la polarité en lançant tous les blocs de code dans le fichier CNN_polarity, et en vérifiant que les dataframes de polarity ont le path du dataframe polarity généré par le fichier lexique_sentimentale_stat, et que les fichier de résultats de classement ont aussi les paths correspondants.  
 Le tableau ci-dessous montre les accuracy de validations des deux approches sur les ensembles de données A et B. 
|  | Méthode Naïve | CNN | 
| :---- | :----: | :----: | 
| A | 13,6% | 39,68% | 

