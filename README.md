# GWU-Machine-Learning-1-Fall-2018-Mushroom-Classification-Project
Mushroom Classification Machine Learning Project

Mushroom Features: ([good domain knowledge overview](https://datascienceplus.com/mushrooms-classification-part-1/))

![m](https://www.english-online.at/biology/mushrooms/parts-of-a-mushroom.gif) 

`cap-shape`: bell=b,conical=c,convex=x,flat=f, knobbed=k,sunken=s. ![m](https://datascienceplus.com/wp-content/uploads/2018/02/mushroom-cap-shape.jpg)
`cap-surface`: fibrous=f,grooves=g,scaly=y,smooth=s ![m](https://datascienceplus.com/wp-content/uploads/2018/02/mushroom-cap-surface.jpg)
`cap-color`: brown=n,buff=b,cinnamon=c,gray=g,green=r, pink=p,purple=u,red=e,white=w,yellow=y
`bruises`: bruises=t,no=f. While identifying mushrooms, check for [bruising]((https://www.mushroom-appreciation.com/identifying-mushrooms.html) by nicking the top and bottom of the cap and watching for any color change.  
`odor`: almond=a,anise=l,creosote=c,fishy=y,foul=f, musty=m,none=n,pungent=p,spicy=s. 
`gill-attachment`: attached=a,descending=d,free=f,notched=n. ![m](https://datascienceplus.com/wp-content/uploads/2018/02/mushroom-gill-attachment.jpg)
`gill-spacing`: close=c,crowded=w,distant=d. ![m](https://datascienceplus.com/wp-content/uploads/2018/02/mushroom-gill-spacing.jpg).
`gill-color`: black=k,brown=n,buff=b,chocolate=h,gray=g, green=r,orange=o,pink=p,purple=u,red=e,white=w,yellow=y. 
`stalk-shape`: enlarging=e,tapering=t.   
`stalk-root`: bulbous=b,club=c,cup=u,equal=e,rhizomorphs=z,rooted=r,missing=?. ![m](https://datascienceplus.com/wp-content/uploads/2018/02/mushroom-stalk.jpg)
`stalk-surface-above-ring`: fibrous=f,scaly=y,silky=k,smooth=s.  
`stalk-surface-below-ring`: fibrous=f,scaly=y,silky=k,smooth=s.  
`stalk-color-above-ring`: brown=n,buff=b,cinnamon=c,gray=g,orange=o, pink=p,red=e,white=w,yellow=y.  
`stalk-color-below-ring`: brown=n,buff=b,cinnamon=c,gray=g,orange=o, pink=p,red=e,white=w,yellow=y.  
`veil-type`: partial=p,universal=u. Tissue that connects the stem and the cap before the gills are exposed. ![m](https://upload.wikimedia.org/wikipedia/commons/thumb/b/b7/1797-09-03_Agaricus_campestris_Plate_by_James_Sowerby.jpg/640px-1797-09-03_Agaricus_campestris_Plate_by_James_Sowerby.jpg).  
`veil-color`: brown=n,orange=o,white=w,yellow=y.  
`ring-number`: none=n,one=o,two=t.  
`ring-type`: cobwebby=c,evanescent=e,flaring=f,large=l, none=n,pendant=p,sheathing=s,zone=z. ![m](https://datascienceplus.com/wp-content/uploads/2018/02/mushroom-ring-type.jpg)  
`spore-print-color`:  black=k,brown=n,buff=b,chocolate=h,green=r, orange=o,purple=u,white=w,yellow=y. For most mushrooms, if the cap is cut off and placed gill-side-down overnight, a powdery impression reflecting the shape of the gills (or pores, or spines, etc.) is formed (when the fruit body is sporulating). The color of the powdery print, called a spore print, is used to help classify mushrooms and can help to identify them.  
`population`: abundant=a,clustered=c,numerous=n, scattered=s,several=v,solitary=y.  
`habitat`: grasses=g,leaves=l,meadows=m,paths=p, urban=u,waste=w,woods=d. 

Problem.	Various guides clearly state that there is no simple rule for determining the edibility of a mushroom (some cites). Normally, one needs to identify the name of the mushroom to be able to tell if it is edible or not. However, this task is very difficult and time consuming for non-experts, so we thought that a machine learning approach on mushroom data could shed light on some of the features that almost guarantee a mushroom will be poisonous. This way, novices can avoid wasting time trying to identify a mushroom that will most likely end up being poisonous and focus on mushrooms that will most likely be edible instead.

We are going to use a dataset from the UCI Machine Learning Repository: https://archive.ics.uci.edu/ml/datasets/mushroom, which contains 8123 mushrooms records and about 22 features, classified as poisonous or edible, drawn from the The Audubon Society Field Guide to North American Mushrooms (insert cite), for two genus (Lepiota and Agaricus) from the Agaricaceae family. We hope to build various machine learning algorithms that can give perfect predictions, or at least no false positives (identifying poisonous mushrooms as edible) and identify the top features for better interpretability and generalization to other families of mushrooms.

Motivation.	We realized that many people in the USA do not know the difference between an edible mushroom and a poisonous one. We hope that through this project we can help educate people on the top significant features that determine whether a mushroom is safe for ingestion or not. We hope this will help save lives and avoid tragedy, especially with children who are curious.

Proposed Methods.    We will be using the following model classifiers:

1. Logistic Regression
2. Decision Tree
3. Random Forest
4. K-Nearest Neighbors
5. Gaussian Naive Bayes
6. Support Vector Machine
7. K-Means Clustering

Packages.     We utilized the following packages:

%matplotlib inline
import numpy as np 
import pandas as pd
import matplotlib.pyplot as plt
import warnings
warnings.filterwarnings("ignore") 
from sklearn.impute import SimpleImputer
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import LabelEncoder
from sklearn.pipeline import Pipeline
from sklearn.model_selection import GridSearchCV
from sklearn.model_selection import StratifiedKFold
from sklearn.linear_model import LogisticRegression
from sklearn.feature_selection import RFE
from sklearn.tree import DecisionTreeClassifier
from sklearn.ensemble import RandomForestRegressor
from pydotplus import graph_from_dot_data
from sklearn.tree import export_graphviz
from IPython.display import Image
from sklearn.ensemble import RandomForestClassifier
from sklearn.svm import SVC
from sklearn.neighbors import KNeighborsClassifier
from sklearn.naive_bayes import GaussianNB
from sklearn.cluster import KMeans
from sklearn.metrics import confusion_matrix

It is strongly encouraged that these models only be used to aid expertise (domain knowledge) of whether a mushroom is edible or poisonous. Expertise should almost always override data/models, especially when identifying potentially dangerous foods like mushrooms. Even though there is high confidence in our models, experts may have made mistakes in gathering the data – as they are human and prone to make mistakes. Lastly due to the ethics and legal considerations of following a model blindly should also be considered. Make no mistake domain knowledge of trained experts should always be adhered to vice a highly accurate prediction model. Better to err on the side of caution than to be wrong! 

Happy Mushroom Classifying!
