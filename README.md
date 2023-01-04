# Conception d’une application de santé publique – Open Food Fact
### OpenClassrooms – Diplôme Data Scientist
---

L'agence "Santé publique France" a lancé un appel à projets pour trouver des idées innovantes d’applications en lien avec l'alimentation à partir des données de « Open Food Fact »
## Mission  
• Élaborer une idée d’application en identifier les arguments justifiant la faisabilité (ou non) de l’application à partir des données Open Food Facts.
## Données
Les données sont disponibles sur le site officiel https://world.openfoodfacts.org/   
Les variables sont définies à l’adresse : https://world.openfoodfacts.org/data/data-fields.txt     
Un fichier CSV :  
o	320772 lignes et 162 colonnes     
o	56 colonnes de types objet (nom du produit, marque, ingredients, etc)     
o	106 colonnes de type float (macro et micro nutriments / 100g composants le produit, nutriscore, etc) avec beaucoup de valeurs aberrantes      
o	76% de valeurs manquantes       

## Résultats 
L'application **'NUTRI CARE'** que je propose indique si un produit alimentaire est compatible ou non avec les maladies chroniques répandues. En pratique, l'utilisateur prend en photo le produit ou son code-barre. A partir de la photo, l'application affiche un score par maladie en se basant sur les données de « Open Food Fact » et on le comparant au Nutri-Score fourni. Les scores éclaireront l'utilisateur si le produit qu'il veut acheter, est approprié pour lui ou non :

**Score 5 ---> produit alimentaire approprié     
Score 1 ---> produit alimentaire non approprié**

Pour l'étude de la faisabilité de l’application, j’ai inclus quatre exemples de maladies chroniques : la diabète, l'hypertension, la lithiase rénale et la maladie cœliaque (l'intolérance au gluten).  

<img src="https://github.com/MayChoueib/Projet-Conception-d-une-application-de-sante-publique-Open-Food-Fact-/blob/main/app-Nutri-care.jpg" width="600" height="200" />

L’application peut facilement être étendue pour d'autres maladies chroniques liées à l'alimentation : la maladie de cœur ‘ATHÉROME ET CORONAROPATHIES’, l'ostéoporose, la goutte (l'inflammation d'articulations due à des dépôts de cristaux d'acide urique provenant de la dégradation des aliments), etc... Pour certaines maladies, il suffit de composer un score de synthèse à partir de ceux déjà réalisés dans ce projet.   
 
Cependant, étant basée sur les données de « Open Food Fact » la fiabilité de l'application en dépend de celle de ces données. A noter que le Nutri-Score fourni par le jeu des données de « Open Food Fact » ne se concorde pas avec les scores de certaines maladies qui se basent entre autre sur les quantités de sucre ou de sel à consommer. 

<img src="https://github.com/MayChoueib/Projet-Conception-d-une-application-de-sante-publique-Open-Food-Fact-/blob/main/produits-scores.jpg" width="200" height="200" />

<img src="https://github.com/MayChoueib/Projet-Conception-d-une-application-de-sante-publique-Open-Food-Fact-/blob/main/carbs-par-score.jpg" width="200" height="200" />
<img src="https://github.com/MayChoueib/Projet-Conception-d-une-application-de-sante-publique-Open-Food-Fact-/blob/main/sodium-score.jpg" width="200" height="200" />

En effet, les carbohydrates qui se décomposent en scure dans le corps ne sont pas pris en compte dans le calcul du Nutri-Score (on voit même des Nutri-Scores verts avec une quantité de plus que 80% de carbohydrates comme les pizzas par exemple! La quantité de sodium est relativement élevée pour un score santé. Des nutriscores verts se rapprochent de la moitié de l’apport quotidien toléré pour une personne en bonne santé et cela pour une quantité de 100g! 

Pour rappel, le Nutri-Score a été développé pour faciliter la compréhension des informations nutritionnelles par les consommateurs et les guider vers des choix alimentaires associés à leur état de santé (d’apres Santé publique France et les articles associés au Nutri-Score)
Le nutriscore se construit sous la forme d’une échelle de notation allant de la lettre A à E (scores équivalents dans le projet de 5 à 1). Il permet de comparer les produits alimentaires en :   
– favorisant : fibres, protéines, fruits, légumes  
– limitant  : énergie, acides gras saturés, sucres, sel      

<img src="https://github.com/MayChoueib/Projet-Conception-d-une-application-de-sante-publique-Open-Food-Fact-/blob/main/distribution-nutriscore-aliments.jpg" width="200" height="200" />
Environ 1/3 (32%) des produits sont considérés comme bon pour la santé selon le Nutri-Score (A et B)!    

Le projet est découpé en deux parties:   
## 1. Notebook PSanté_notebook_nettoyage   
• L'objectif de ce notebook est de nettoyer le jeu de données et de repérer des variables pertinentes pour l'application que je propose  

## 2. Notebook PSanté_notebook_exploration
• L'objectif de ce notebook est l'exploration et l'analyse des données qui va me permettre la création des scores de certaines maladies chroniques à titre d'exemple :la  diabète, l'hypertension, la lithiase rénale et la maladie cœliaque (l'intolérance au gluten). Je montre avec les scores crées une démonstration de la faisabilité de l'application	    


 
*Références pour la création des scores maladies : Une large documentation a été effectuée dans le cadre de la création des scores de maladies retenues comme exemples pour la réalisation de l'application dans ce notebook. Les principales références retenues sont :
https://www.snfge.org/content/maladie-coeliaque (Société Nationale Française de Gastro-Entérologie)
https://hypertension.ca/
Institute of Medicine of the National Academies (IOM) des États-Unis
https://www.diabetes.ca/ https://www.diabete.qc.ca/ American Association of Diabetes Educator (AADE)
https://rein.ca/ ; http://www.urofrance.org/fileadmin/medias/afu/communiques/2015-12-07_calculs-urinaires.pdf (Association française d’urologie)
ANSES (Agence nationale de sécurité sanitaire de l’alimentation, de l’environnement et du travail) OMS (Organisation Mondiale de la Santé)

