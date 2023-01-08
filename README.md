# Application_Innovation
Prédiction des notes de films à l'aide de différents modèles NLP, formés sur la base de données Allo Ciné
# Prétraitement
Pour lancer le prétraitement pour générer le jeux de données A  il faut lancer le code du fichier pretraitement.ipynb sauf la fonction qui enlève les stop words marqué dans le fichier.   
Pour générer le jeux de données B Il faut décomenter les lignes de code indiqué dans la fonction text_preprocessing_pipeline et puis lancer tous le code.   
# SVM 
Pour modifier le jeu de données à utiliser, il suffit de changer le chemin dans les fonctions pd.read_csv().    
Pour lancer l'entraînement du SVM faut lancer tous les blocs de code dans le fichier testNLP.   
# CNN
Pour modifier le jeu de données à utiliser, il suffit de changer le chemin dans les fonctions pd.read_csv().   
Pour lancer l'entraînement du modèle en utilisant word2vec ou fast text, il suffit d'exécuter les blocs de code sous leur titre respectif   après avoir généré les embeddings initiaux.   
Pour lancer le train de modèles utilisant keras tokenizer, il suffit d'exécuter les derniers blocs de code sous le titre keras tokenizer après avoir généré les embeddings initiaux
# Camembert
Le fichier Camembert_final_complete contient le code pour entraîner le model camembert. Pour lancer l'entraînement sur les deux différents jeux de données il suffit de changer le path de pd.read_csv() et lancer le code sans rien changer
# Lexique Sentimentale

