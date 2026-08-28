# Collisioni

## Collisioni della Tile Map
Per non cadere attraverso la Tile Map, dobbiamo impostare le collisioni. Per farlo apriamo abbiamo due modi ma preferiamo il secondo per prevenire errori di collisione tra tile adiacenti:
1. Apriamo il **Tile Set** e per ogni tile clcchiamo su **Add Box** (i tile alla quale è stato effettuato ciò sono visuliazzibali abilotando il bottone **Colliding Tils**).
2. Aggiungiamo dal **Quick Add Menu** un **Plane** che posizioniamo ala stessa altezza facendo si che copra tutta la mappa. Per evitare glitch visivi disattiviamo la visibilità del plane.

## Collisioni del Character
Per evitare che il personaggio "scavalchi" oggetti come alberi, rocce o altri ostacoli, dobbiamo reagolare il **Max Step Height** nel BP del personaggio e la **Collision Thickness** dello sprite dell'ostacolo.

Inoltre se vogliamo delle collisioni realistiche dove il personaggio riesce ad arrivare fino al bordo dell'oggetto sia sopra e sotto che ai lati, dobbiamo impostare la dimensione della **Capsule Component del personaggio** in modo che copra i soli piedi del personaggio. Mentre per gli ostacoli dobbiamo impostare nello sprite la **Collision Box**, tramite **Edite Collision**, in modo che copra solo la base dell'ostacolo.

## Ordinamento di rendering
Per evitare che il personaggio vengo disegnato sopra a qualcosa che dovrebbe essere davanti a lui, dobbiamo impostare diverse cose:
- Il **Pivot Point** di tutti gli sprite deve essere impostato in basso al centro. (Serve per capire dove si trova il personaggio e dove si trova l'ostacolo, si scegli in basso al centro perchè il personaggio si muove in basso e non in alto).

- Il **Default Material** di tutti gli sprite deve essere impostato su **TranslucentUnlitSpriteMaterial**. (Abilitare **Show Engine Content** e ** Show Plugin Content** per trovarlo).

- Modificare il **Translucent Sort Policy** a **Sort Along Axis** e impostare **Traslucent Sort Axis** a **Y** = -1 nei **Project Settings**. (Serve per ordinare i layer in base alla posizione Y, impostando Y = -1 si fa in modo che più un oggetto è in basso più viene disegnato sopra).

- Modificare anche il **Materiale** dello sprite del personaggio nel suo **Blueprint** in quanto quest'ultimo sovrascrive il materiale dello sprite.

- Stessa cosa del passaggio precendente per i **Flipbook** di eventuali ostacoli o decorazioni.