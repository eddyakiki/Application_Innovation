# Application_Innovation
Prédiction des notes de films à l'aide de différents modèles NLP, formés sur la base de données Allo Ciné
# Prétraitement
Pour lancer le prétraitement pour générer le jeux de données A  il faut lancer le code du fichier pretraitement.ipynb sauf la fonction qui enlève les stop words marqué dans le fichier.   
Pour générer le jeux de données B Il faut décomenter les lignes de code indiqué dans la fonction text_preprocessing_pipeline et puis lancer tous le code.   
A est le jeu de données pour lequel nous n'avons pas supprimé les mots d'arrêt, les caractères spéciaux français et les apostrophes.   
B est le jeu de données pour lequel on a supprimé les mots d'arrêt et les caractères spéciaux français et les apostrophes.
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
Pour lancer le train de modèles utilisant keras tokenizer, il suffit d'exécuter les derniers blocs de code sous le titre keras tokenizer après avoir généré les embeddings initiaux
Le tableau ci-dessous montre les accuracy de validation des modèles entraînés sur les ensembles de données A et B en utilisant les différents types de embeddings.  
|  | A | B | 
| :---- | :----: | :----: | 
| Keras Tokenizer | 38% | 39% | 
| Word2Vec | 39,3% | 38% |
| Fast Text | 38,4% | 38,5% |
# Camembert
Le fichier Camembert_final_complete contient le code pour entraîner le model camembert. Pour lancer l'entraînement sur les deux différents jeux de données il suffit de changer le path de pd.read_csv() et lancer le code sans rien changer.  
Le tableau ci-dessous montre les accuracy de test des modèles camembert entraînés sur les ensembles de données A et B. 
|  | A | B | 
| :---- | :----: | :----: | 
| 10 Labels | 46,37% | 40,3% | 
| 3 Labels | 86,54% | 83,5% |
# Lexique Sentimentale
Il faut lancer tout les blocs de code du fichier lexique_sentimentale_stat, et vérifier que vous avez sauvgarder les trois fichier cvs de train test et dev avec la nouvelle colonne de polarité ainsi que les résultats de classement de la méthode naïve dans trois fichier text différents pour train test et dev.  
Vous pouvez ensuite lancer l'entraînement du model CNN avec la polarité en lançant tous les blocs de code dans le fichier CNN_polarity, et en vérifiant que les dataframes de polarity ont le path du dataframe polarity généré par le fichier lexique_sentimentale_stat, et que les fichier de résultats de classement ont aussi les paths correspondants.  
 Le tableau ci-dessous montre les accuracy de validations des deux approches sur les ensembles de données A et B. 
|  | Méthode Naïve | CNN | 
| :---- | :----: | :----: | 
| A | 13,6% | 39,68% | 

