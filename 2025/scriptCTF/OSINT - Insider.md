
- [[#Insider 1]]
- [[#Insider 2]]
- [[#Insider 3]]
- [[#Insider 4]]

___
# Insider 1

![](attachment/e7cb35f8aae4e71d82958d1494f64ee9.png)

La première chose à faire était d'aller voir l'équipe du support à cette adresse : 
- https://play.scriptsorcerers.xyz/support

Il fallait ensuite regarder dans la bio discord d'un des membres du support :
![](attachment/d4525b3c1da67959fd9ee792f31226cf.png)

Flag : `scriptCTF{1ts_0bv10u5ly_j0hn_d03_aka_n00bm4573r}`

___
# Insider 2

![](attachment/bf415318bfee7c0abb3e43ceabd41247.png)

Pas fait, mais voici un WU de quelqu'un d'autre : 
- https://github.com/0xt4req/ScriptCTF-writeup/tree/main/OSINT

___
# Insider 3

![](attachment/b27af378ccb3a0e6c60739ed6fe319d9.png)

Après avoir découvert qui a leak ainsi que son compte github, ou pouvait voir qu'il a commit d'autres choses sur un autre compte github :
![](attachment/43be3fc9b10ac7694d83fbc405e0ee59.png)

En suivant le lien vers cet autre compte, on tombe sur le 3e flag de notre série !
![](attachment/0c87a1d600da3f872e8d225f3d9e6eb6.png)

Flag : `scriptCTF{2026_fl4g_f0und_1n_2025}`

___
# Insider 4

On arrive à la dernière étape de notre parcours !

![](attachment/589bd115615d96b5a6fc1b01fa8471e0.png)

On trouve des informations sur le dernier compte github trouvé :

![](attachment/faf1c5cfe9a6c10ba229cf14eaec7292.png)

Dans le même dossier `attachments`, on retrouve deux photos ainsi qu'un fichier secret contenant ceci :
	`as a photographer, i add comments/descriptions to my images`

Première image : `fireworks.jpg`
![](attachment/53e36f126ff5d738eaba45cbfcd8d21d.jpg)

Deuxième image : `room.jpg`
![](attachment/2e7e2819542561b0aa814dbec048a4b2.jpg)

Premièrement, la recherche inversée d'image ne donne rien. Il ne nous reste plus qu'à exploiter le petit secret !

Pour cela, on va utiliser l'outil `exiftool` :

![](attachment/153ff5cbb6a5c1da48d4facbe466c8cc.png)

Bingo ! La photo `fireworks.jpg` contient bien un commentaire !

![](attachment/0ec9c67a0aeae5958cf77a387e97203e.png)

En cliquant sur le lien Facebook, on tombe sur cette page :

![](attachment/8c3f2cfac93098ab8646a65a77835bca.png)

On aperçoit ensuite le site de l'évènement. En allant dessus on peut voir ceci :

![](attachment/028c45ac9193ac87e8ae5db4c77265b7.png)

Sachant que l'on cherche un hotel, on clique sur `Where to Eat, Stay, & Watch` puis on descend vers `Where to STAY`. On observe deux lieux : 
- Key Allegro, Real Estate Company
- The INN at Fulton Harbor

Ces deux lieux vont nous aider dans notre recherche, surtout le premier.
Si nous revenons sur nos pas, nous n'avons utilisé qu'une seule des deux photos du challenge : `firework.jpg`. Mais maintenant qu'on a trouvé où chercher, la photo `room.jpg` va grandement nous guider dans cette recherche !

Premièrement, on observe la forme de l'hôtel : en forme de `U`, avec un parking devant et quelques tables de picnic. On observe également une terre séparée par de l'eau !
La seule zone qui peut correspondre est celle-ci :

![](attachment/702e3a2e155a1c3899e4694d1d5dd5aa.png)

On y retrouve bien *Key Allegro*. Avec une recherche des hôtels faisant face à la baie sur google maps, on a juste à regarder quel hôtel correspond à notre description de la photo `room.jpg`.

On arrive très rapidement à cet endroit :

![](attachment/25393ab7a92a3242a875324f86437784.png)

Pour visualiser la vue, voici le lien maps : https://www.google.com/maps/@28.0315856,-97.0462669,3a,34.3y,256.27h,87.31t/data=!3m7!1e1!3m5!1scf74P7wpw6ffASoGftMhew!2e0!6shttps:%2F%2Fstreetviewpixels-pa.googleapis.com%2Fv1%2Fthumbnail%3Fcb_client%3Dmaps_sv.tactile%26w%3D900%26h%3D600%26pitch%3D2.6903063287553834%26panoid%3Dcf74P7wpw6ffASoGftMhew%26yaw%3D256.27150613110496!7i16384!8i8192?hl=fr&entry=ttu&g_ep=EgoyMDI1MDgxMy4wIKXMDSoASAFQAw%3D%3D

On récupère donc l'adresse de l'hôtel : `901 Hwy 35 N, Rockport, TX 78382, États-Unis`

Ainsi on a la première partie du flag !
- `scriptCTF{901_Hwy_35_N_`

Maintenant, on va se pencher sur le numéro de la chambre. La première observation se fait que le lien maps juste au dessus : 
- on ne voit pas les numéros de chambres de cet emplacement, il faudra donc aller de l'autre côté, juste ici : https://www.google.com/maps/@28.031457,-97.047378,3a,75y,69.91h,75.94t/data=!3m7!1e1!3m5!1s7RXlB_db0szyw8-FjaD_lA!2e0!6shttps:%2F%2Fstreetviewpixels-pa.googleapis.com%2Fv1%2Fthumbnail%3Fcb_client%3Dmaps_sv.tactile%26w%3D900%26h%3D600%26pitch%3D14.058045464968231%26panoid%3D7RXlB_db0szyw8-FjaD_lA%26yaw%3D69.91178046392373!7i16384!8i8192?hl=fr&entry=ttu&g_ep=EgoyMDI1MDgxMy4wIKXMDSoASAFQAw%3D%3D

Ensuite sur la photo `room.jpg`, on observe :
- la chambre se situe au rez-de-chaussée
- elle est alignée sur la troisième place de parking en partant de la gauche, elle est donc placée bien à gauche mais pas tout au bout

Pour finir, sur le dernier lien maps, lorsqu'on zoom sur la chambre tout à droite, on peut voir ceci :

![](attachment/91972574d4445ccfd2cff936a30b3c52.png)

Si on regarde avec attention, on peut y lire le numéro `107`.
Mais ce n'est pas tout, deux chambres sur la gauche se trouve la `109` !
Ainsi, plus on va sur la gauche et plus le nombre augmente. Maintenant qu'on sait qu'une porte équivaut à une chambre, on compte vers la gauche pour ne laisser que les numéros compris entre `111` et `114`, puisque pour rappel notre chambre se situe à gauche.

Il suffit alors d'essayer chaque combinaison avec un numéro de chambre différent ;)

Flag : `scriptCTF{901_Hwy_35_N_111}`
