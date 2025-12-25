# Tile Map

## Creazione della Tile Map
Per creare l'ambiente di gioco, seguiamo questo processo logico:

1. **Texture**
   È l'immagine grezza (es. un file `.png`) che hai importato. Immaginala come il "foglio" che contiene tutti i disegni grezzi.

2. **Tile Set**
   È la "tavolozza" creata dalla texture.
   * È una collezione di regole (non ancora una mappa).
   * Qui definisci la grandezza della griglia (es. 32x32 pixel).
   * Qui imposti le collisioni.

3. **Tile Map**
   È la **"Tela dipinta"**, ovvero il risultato finale della composizione.
   * Quando crei questo asset, inizialmente vedi una griglia vuota.
   * Qui utilizzi il *Tile Set* per "dipingere" effettivamente strade, muri ed erba.
   * È questo l'elemento che devi **trascinare nella Viewport** (la scena di gioco) per vederlo apparire 
   realmente nel mondo.
   * Ruota la Tile Map sul piano orizzontale (XY) per il gameplay Top-Down.