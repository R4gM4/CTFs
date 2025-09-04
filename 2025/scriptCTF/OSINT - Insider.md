# Insider 1

![](attachment/e7cb35f8aae4e71d82958d1494f64ee9.png)

The first thing to do was to go see the support team at this address:  
- https://play.scriptsorcerers.xyz/support

Then you had to check the Discord bio of one of the support members:  
![](attachment/d4525b3c1da67959fd9ee792f31226cf.png)

Flag: `scriptCTF{1ts_0bv10u5ly_j0hn_d03_aka_n00bm4573r}`

___
# Insider 2

![](attachment/bf415318bfee7c0abb3e43ceabd41247.png)

Not done, but here’s someone else’s write-up:  
- https://github.com/0xt4req/ScriptCTF-writeup/tree/main/OSINT

___
# Insider 3

![](attachment/b27af378ccb3a0e6c60739ed6fe319d9.png)

After discovering who leaked as well as his GitHub account, you could see that he had committed other things on another GitHub account:  
![](attachment/43be3fc9b10ac7694d83fbc405e0ee59.png)

By following the link to this other account, we find the 3rd flag in our series!  
![](attachment/0c87a1d600da3f872e8d225f3d9e6eb6.png)

Flag: `scriptCTF{2026_fl4g_f0und_1n_2025}`

___
# Insider 4

We arrive at the last step of our journey!  

![](attachment/589bd115615d96b5a6fc1b01fa8471e0.png)

We find information about the last GitHub account discovered:  

![](attachment/faf1c5cfe9a6c10ba229cf14eaec7292.png)

In the same `attachments` folder, we find two photos and a secret file containing this:  
`as a photographer, i add comments/descriptions to my images`

First image: `fireworks.jpg`  
![](attachment/53e36f126ff5d738eaba45cbfcd8d21d.jpg)

Second image: `room.jpg`  
![](attachment/2e7e2819542561b0aa814dbec048a4b2.jpg)

<<<<<<< Updated upstream
Premièrement, la recherche inversée d'image ne donne rien. Il ne nous reste donc plus qu'à exploiter le petit secret !
=======
First, reverse image search gives nothing. All we have left is to exploit the little secret!  
>>>>>>> Stashed changes

For that, we’re going to use the `exiftool` tool:  

![](attachment/153ff5cbb6a5c1da48d4facbe466c8cc.png)

Bingo! The `fireworks.jpg` photo does contain a comment!  

![](attachment/0ec9c67a0aeae5958cf77a387e97203e.png)

Clicking on the Facebook link, we land on this page:  

![](attachment/8c3f2cfac93098ab8646a65a77835bca.png)

We then see the event’s website. Going there, we can see this:  

![](attachment/028c45ac9193ac87e8ae5db4c77265b7.png)

Knowing we’re looking for a hotel, we click on `Where to Eat, Stay, & Watch` then scroll down to `Where to STAY`. We observe two places:  
- Key Allegro, Real Estate Company  
- The INN at Fulton Harbor  

<<<<<<< Updated upstream
Ces deux lieux vont nous aider dans notre recherche, surtout le premier.
Si nous revenons sur nos pas, nous n'avons utilisé qu'une seule des deux photos du challenge : `firework.jpg`. Mais maintenant qu'on sait où chercher, la photo `room.jpg` va grandement nous guider pour trouver l'hôtel et la chambre !

Premièrement, on observe la forme de l'hôtel : en forme de `U`, avec un parking devant et quelques tables de picnic. On observe également une terre séparée par de l'eau.
La seule zone qui peut correspondre est celle-ci :
=======
These two places help our search, especially the first one.  
If we go back, we’ve only used one of the two challenge photos: `firework.jpg`. But now that we know where to search, the `room.jpg` photo will guide us a lot in this search!  

First, we observe the shape of the hotel: U-shaped, with a parking lot in front and some picnic tables. We also see land separated by water!  
The only area that matches is this one:  
>>>>>>> Stashed changes

![](attachment/702e3a2e155a1c3899e4694d1d5dd5aa.png)

We do indeed find *Key Allegro*. With a Google Maps search of hotels facing the bay, we just need to check which hotel matches our `room.jpg` description.  

We very quickly end up at this spot:  

![](attachment/25393ab7a92a3242a875324f86437784.png)

To visualize the view, here’s the maps link: https://www.google.com/maps/@28.0315856,-97.0462669,3a,34.3y,256.27h,87.31t/data=!3m7!1e1!3m5!1scf74P7wpw6ffASoGftMhew!2e0!6shttps:%2F%2Fstreetviewpixels-pa.googleapis.com%2Fv1%2Fthumbnail%3Fcb_client%3Dmaps_sv.tactile%26w%3D900%26h%3D600%26pitch%3D2.6903063287553834%26panoid%3Dcf74P7wpw6ffASoGftMhew%26yaw%3D256.27150613110496!7i16384!8i8192?hl=fr&entry=ttu&g_ep=EgoyMDI1MDgxMy4wIKXMDSoASAFQAw%3D%3D  

We then retrieve the hotel address: `901 Hwy 35 N, Rockport, TX 78382, United States`  

Thus we have the first part of the flag!  
- `scriptCTF{901_Hwy_35_N_`  

<<<<<<< Updated upstream
Maintenant, on va se pencher sur le numéro de la chambre. La première observation se fait sur le lien maps juste au dessus : 
- on ne voit pas les numéros de chambres de cet emplacement, il faudra donc aller de l'autre côté, juste ici : https://www.google.com/maps/@28.031457,-97.047378,3a,75y,69.91h,75.94t/data=!3m7!1e1!3m5!1s7RXlB_db0szyw8-FjaD_lA!2e0!6shttps:%2F%2Fstreetviewpixels-pa.googleapis.com%2Fv1%2Fthumbnail%3Fcb_client%3Dmaps_sv.tactile%26w%3D900%26h%3D600%26pitch%3D14.058045464968231%26panoid%3D7RXlB_db0szyw8-FjaD_lA%26yaw%3D69.91178046392373!7i16384!8i8192?hl=fr&entry=ttu&g_ep=EgoyMDI1MDgxMy4wIKXMDSoASAFQAw%3D%3D
=======
Now, let’s focus on the room number. The first observation comes from the maps link above:  
- we don’t see the room numbers from this spot, so we have to go to the other side, right here: https://www.google.com/maps/@28.031457,-97.047378,3a,75y,69.91h,75.94t/data=!3m7!1e1!3m5!1s7RXlB_db0szyw8-FjaD_lA!2e0!6shttps:%2F%2Fstreetviewpixels-pa.googleapis.com%2Fv1%2Fthumbnail%3Fcb_client%3Dmaps_sv.tactile%26w%3D900%26h%3D600%26pitch%3D14.058045464968231%26panoid%3D7RXlB_db0szyw8-FjaD_lA%26yaw%3D69.91178046392373!7i16384!8i8192?hl=fr&entry=ttu&g_ep=EgoyMDI1MDgxMy4wIKXMDSoASAFQAw%3D%3D  
>>>>>>> Stashed changes

Then in the `room.jpg` photo, we observe:  
- the room is on the ground floor  
- it is aligned with the third parking spot from the left, so it’s well to the left but not all the way at the end  

Finally, in the last maps link, when zooming in on the room all the way to the right, we can see this:  

![](attachment/91972574d4445ccfd2cff936a30b3c52.png)

Looking closely, we can read the number `107`.  
But that’s not all, two rooms to the left we find `109`!  
Thus, the further left we go, the higher the number. Now that we know each door equals one room, we count left to leave only numbers between `111` and `114`, since our room is to the left.  

All that’s left is to try each combination with a different room number ;)  

Flag: `scriptCTF{901_Hwy_35_N_111}`
