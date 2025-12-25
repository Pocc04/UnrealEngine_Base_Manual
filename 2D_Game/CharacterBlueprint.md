# Character blueprint

Quando creaiamo un PaperZDCharacter sarà uguale a creare un Paper2D con l'aggiunta di Animetion Component.
Utiliziamo una logica object oriented basata sulla ereditarietà. Creiamo prima il personaggio base e da li andiamo a specializzare (es. nemico, eroe, npc). Tutte le modifiche apportate al parent si riversano ai child

- **Creazione del CharBase**
Cerca e seleziona PaperZDCharacter, da qui lavora sul blueprint appena creato.

- **Creazione del CharChild**
Crea un child partendo da CharBase

- **Impostare il personaggio allo start iniziale**
Nel GameMode apriamo il blueprint e nei Ddetails impostiamo in **Default Pawn Class** il blueprint del personaggio da cui vogliamo iniziare 

## Agire nel character blueprint
- **Impostare losprite**  
Seleziona il component Sprite e imposta lo sprite desiderato in Details (Ricorda di ruotarlo nella direzione giusta)

- **Impostiamo la camera**
Selezioniamo il Capsule Component e aggiungiamo **Spring Arm**, poi partendo da questo componente aggiugiamo una **Camera**. Poi impstiamo la spring arm in maniera che la camera sia rivolta verso il personaggio nella maniera corretta.

- **Collision test**
Come ottimizzazione in giochi 2D diabilitiamo nei Details di Spring Arm **Do Collision Test**.

- **Dettagli Camera**
    - Impostiamo la **Projection Mode** in Orthographic per il giochi 2D.
    - La **Ortho Width** imposta la distanza della camera dallo soggetto su cui punta.