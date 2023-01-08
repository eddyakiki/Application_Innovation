# Application_Innovation
Prédiction des notes de films à l'aide de différents modèles NLP, formés sur la base de données Allo Ciné
# Prétraitement
Pour lancer le prétraitement pour générer le jeux de données A  il faut lancer le code du fichier pretraitement.ipynb sauf la fonction qui enlève les stop words marqué dans le fichier.   
Pour générer le jeux de données B Il faut décomenter les lignes de code indiqué dans la fonction text_preprocessing_pipeline et puis lancer tous le code.   
# SVM 
Pour modifier le jeu de données à utiliser, il suffit de changer le chemin dans les fonctions pd.read_csv().    
Pour lancer l'entraînement du SVM faut lancer tous les blocs de code dans le fichier testNLP.   
| Jeux de Données A | Jeux de données B| 
| :---- | :----: | 
| 32%| 34% | 
# CNN
Pour modifier le jeu de données à utiliser, il suffit de changer le chemin dans les fonctions pd.read_csv().   
Pour lancer l'entraînement du modèle en utilisant word2vec ou fast text, il suffit d'exécuter les blocs de code sous leur titre respectif   après avoir généré les embeddings initiaux.   
Pour lancer le train de modèles utilisant keras tokenizer, il suffit d'exécuter les derniers blocs de code sous le titre keras tokenizer après avoir généré les embeddings initiaux
# Camembert
Le fichier Camembert_final_complete contient le code pour entraîner le model camembert. Pour lancer l'entraînement sur les deux différents jeux de données il suffit de changer le path de pd.read_csv() et lancer le code sans rien changer
# Lexique Sentimentale
Il faut lancer tout les blocs de code du fichier lexique_sentimentale_stat, et vérifier que vous avez sauvgarder les trois fichier cvs de train test et dev avec la nouvelle colonne de polarité ainsi que les résultats de classement de la méthode naïve dans trois fichier text différents pour train test et dev.  
Vous pouvez ensuite lancer l'entraînement du model CNN avec la polarité en lançant tous les blocs de code dans le fichier CNN_polarity, et en vérifiant que les dataframes de polarity ont le path du dataframe polarity généré par le fichier lexique_sentimentale_stat, et que les fichier de résultats de classement ont aussi les paths correspondants.  

