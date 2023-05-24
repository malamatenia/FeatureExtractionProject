# FeatureExtractionProject

### Link to models and weights : https://drive.google.com/drive/folders/1KMNZ3roDhKn93ovfJK4Bl2TD5FWmWBhj?usp=share_link 


L'objectif de ce projet est d'explorer l'extraction et l'interprétation des features issues d'un classificateur CNN de deux classes de manuscrits médiévaux différents : fortement abrégés et non-abrégés. Pour cela, l'équipe s'est inspirée du cadre DeepScript de Mike Kestemont : https://github.com/mikekestemont/DeepScript où ils ont observé des signes d'abréviation apparaissant dans la feature map.

La première étape du projet consiste à choisir et construire un ensemble de données pour notre expérience. Nous avons décidé de travailler avec des jeux de données en latin et en français ancien qui sont bien documentés :
CREMMA-fro: https://github.com/HTR-United/cremma-medieval
CREMMa-lat: https://github.com/HTR-United/CREMMA-Medieval-LAT 
Gallocorpora_15: https://github.com/Gallicorpora/HTR-MSS-15e-Siecle 
ECMEN: https://github.com/oriflamms/ECMEN
Données de Margueritte Vernet

La question la plus importante est de définir les deux classes de manière à ce qu'elles soient symptomatiques de ce que nous considérons comme des pages de manuscrits "fortement abrégées" et "non abrégées". Les ensembles de données choisies ont l'avantage d'être accompagnés de transcriptions et d'une segmentation au niveau de la zone, ce qui permet de réduire le bruit provenant de l'arrière-plan et des initiales/figures.

Afin de diviser les images de l'ensemble de données en deux catégories de manière non subjective, nous avons eu l'idée d'exploiter les transcriptions et de calculer le pourcentage total de signes abréviatifs par page. Le seuil a été fixé à <1 pour les manuscrits à peine abrégés et à >6,5 pour les manuscrits fortement abrégés. Les observations sur les seuils proviennent d'un article récent sur les modèles de transcription HTR : https://hal.science/hal-03828353/ et sont indicatives, donc susceptibles d'être ajustées et affinées en fonction des résultats.

TODO:

- [x] Final clean of the data and balancing of classes (Matenia)
- [ ] Adaptation of https://github.com/mikekestemont/DeepScript code for our purposes - couldn't do - problems of package compatibility
- [ ] Interpretation of the extracted features - impossible 
- [x] train a ResNet50 
- [x] train a homemade model
- [x] extract them features  
