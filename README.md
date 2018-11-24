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
