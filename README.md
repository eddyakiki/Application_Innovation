# Application_Innovation
Prédiction des notes de films à l'aide de différents modèles NLP entraînés sur la base de données d'Allo Ciné.
# Prétraitement
Pour lancer le prétraitement et générer le jeu de données A, il suffit d'exécuter le code du fichier "pretraitement.ipynb", sauf la fonction qui enlève les stop words marquée dans le fichier.

Pour générer le jeu de données B, il faut décommenter les lignes de code indiquées dans la fonction "text_preprocessing_pipeline" et lancer l'ensemble du code.

Pour générer le jeu de données C, il faut exécuter tous les blocs de code dans le fichier "pretraitement C".

Le jeu de données A est celui pour lequel nous n'avons pas supprimé les mots d'arrêt, les caractères spéciaux français et les apostrophes.

Le jeu de données B est celui pour lequel nous avons supprimé les mots d'arrêt, les caractères spéciaux français et les apostrophes.

Le jeu de données C est celui pour lequel nous avons supprimé les caractères non alphanumériques et appliqué un stemming sur les tokens.
# SVM 
Pour modifier le jeu de données à utiliser, il suffit de changer le chemin dans les fonctions pd.read_csv().

Pour lancer l'entraînement du SVM, il suffit d'exécuter tous les blocs de code dans le fichier "testNLP".

Le tableau ci-dessous montre les précisions de validation des modèles entraînés sur les ensembles de données A et B.
| A | B | 
| :---- | :----: | 
| 32% | 34% | 
# CNN
Pour modifier le jeu de données à utiliser, il suffit de changer le chemin dans les fonctions pd.read_csv().

Pour lancer l'entraînement du modèle en utilisant Word2Vec ou FastText, il suffit d'exécuter les blocs de code sous leur titre respectif après avoir généré les embeddings initiaux.

Pour lancer l'entraînement de modèles utilisant le tokenizer de Keras, il suffit d'exécuter les derniers blocs de code sous le titre "Keras Tokenizer" après avoir généré les embeddings initiaux.

Le tableau ci-dessous montre les précisions de validation des modèles entraînés sur les ensembles de données A et B en utilisant les différents types d'embeddings.
|  | A | B | 
| :---- | :----: | :----: | 
| Keras Tokenizer | 38% | 39% | 
| Word2Vec | 39,3% | 38% |
| Fast Text | 38,4% | 38,5% |
# MLP
Au total, il y a 5 modèles MLP, dont 1 entraîné en utilisant Doc2Vec. Pour l'entraîner, il faut exécuter tous les blocs de code du fichier "MLP_doc2vec_A". La précision de validation de ce modèle est de 16,33%.

Pour entraîner deux MLP sur A et B avec les métadonnées en utilisant le tokenizer "text_to_sequence" de Keras, il faut exécuter tous les blocs de code du fichier "MLP_sur_AetB_avec_MetaData".

Pour entraîner deux MLP sur A et B sans les métadonnées en utilisant le tokenizer "text_to_sequence" de Keras, il faut exécuter tous les blocs de code du fichier "MLP_sur_AetB_sans_MetaData".

Le tableau ci-dessous montre les précisions de validation de ces 4 modèles.
|  | A | B | 
| :---- | :----: | :----: | 
| Avec Méta Data | 35.58% | 36.8% | 
| Sans Méta Data | 34,63% | 35,43% |
# Camembert
Le fichier "Camembert_final_complete" contient le code pour entraîner le modèle Camembert. Pour lancer l'entraînement sur les deux différents jeux de données, il suffit de changer le chemin d'accès de la fonction pd.read_csv() et de lancer le code sans rien modifier d'autre.
Le tableau ci-dessous montre les précisions des modèles Camembert entraînés sur les ensembles de données A et B.
|  | A | B | 
| :---- | :----: | :----: | 
| 10 Labels | 46,37% | 40,3% | 
| 3 Labels | 86,54% | 83,5% |
# LSTM 
Pour lancer l'entraînement de deux LSTM sur B, l'un avec les métadonnées et l'autre sans, vous devez exécuter tous les blocs du fichier "lstm_lstmbidirectionnel_sur_B_meta_data" ainsi que les blocs du LSTM unidirectionnel du même fichier.
La précision de validation du modèle avec les métadonnées est de 37,01 %, tandis que celle de l'autre modèle sans les métadonnées est de 38,2 %.
Pour entraîner l'LSTM bidirectionnel sur B avec les métadonnées, vous devez exécuter les blocs du LSTM bidirectionnel du fichier "lstm_lstmbidirectionnel_sur_B_meta_data". La précision de validation de ce modèle est de 38,8 %. 
# Lexique Sentimentale
Il faut lancer tous les blocs de code du fichier "lexique_sentimental_stat" et vérifier que vous avez sauvegardé les trois fichiers CSV de train, test et dev avec la nouvelle colonne de polarité ainsi que les résultats de classification de la méthode naïve dans trois fichiers texte différents pour train, test et dev. Ensuite, vous pouvez lancer l'entraînement du modèle CNN en exécutant tous les blocs de code du fichier "CNN_polarity". Veuillez vérifier que les dataframes de polarité ont le chemin d'accès du dataframe de polarité généré par le fichier "lexique_sentimental_stat", et que les fichiers de résultats de classification ont également les chemins d'accès correspondants. Le tableau ci-dessous montre les précisions des deux approches sur les ensembles de données A et B.
|  | Méthode Naïve | CNN | 
| :---- | :----: | :----: | 
| A | 13,6% | 39,68% | 

