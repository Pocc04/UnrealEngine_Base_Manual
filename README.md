# UnrealEngine_Base_Manual
Manuale per la creazione di un progetto in UnrealEngine

## Poject Settings Consigliati
TO-DO

## Diagramma delle Directory in Unreal Content Drawer Consigliato
```text
Content/
├── Blueprints/
│   ├── Characters                  #Contiene i **Blueprint** per il comportamento dei personaggi
│   └── GameMode.uasset             #Blueprint per Impostare le Regole del Gioco
├── Fonts/                          #Contiene i Font per i Testi
├── Input/
│   ├── Actions/                    #Contiene tutte le **Input Actions**
│   └── InputMappingCotext.uasset
├── Maps/                           #Contiene la mappa del mondo
├── PaperAssets/
│   ├── Characters/                 #Contiene **Sprite**, **Texture**, **Sprite Sheet** and **Flipbook** per ogni Character
│   ├── Environment/                #Contiene **Sprite**, **Texture**, **Sprite Sheet** and **Flipbook** per ogni Ambiente di gioco
│   ├── Props/                      #Contiene **Sprite**, **Texture**, **Sprite Sheet** and **Flipbook** per ogni Oggetto
│   └── VFX/                        #Contiene **Sprite**, **Texture**, **Sprite Sheet** and **Flipbook** per ogni VFX
├── Sounds/                         #Contiene i suoni
└── UI/                             #Contiene le User Inerface
```

## Azioni Iniziali Consigliate
- **Ruota la Tile Map sul piano orizzontale (XY) per il gameplay Top-Down.**

- **Seleziona tutte le texture, tasto destro -> Sprite Actions -> Apply Paper 2D Texture Settings**  
Ottimizza le immagini per la Pixel Art:
    * Filtro: Linear -> Nearest  
    * Compressione: Default -> UserInterface2D  
    * Mipmaps: On -> Off

- **Impostiamo 'Pixels Per Unit'**
Per garantire un rapporto 1:1 tra i pixel disegnati e le unità di gioco, evitando di dover ridimensionare manualmente gli oggetti (Scale) dopo l'importazione.

- **Imposta manualmente il filtro nearest alle texture**  
Forziamo manualmente il filtro su 'Nearest' per garantire che i pixel rimangano nitidi anche nel gioco esportato (build finale), prevenendo casi in cui il 'Texture Group' predefinito potrebbe fallire e applicare sfocature indesiderate.

- **Piano con cui collidiamo per non cadere nel vuoto**
Usa un unico piano di collisione per il pavimento per evitare intoppi fisici (ghost collisions) sulle giunture dei tile e migliorare le prestazioni. Deve essere allineato e grande almeno quanto la **TileMap**. Impostare il campo **Visible** su false per non avere problemi di **Z-War**. 

- **Creare una "Condition Tile Sheet Texture" partendo dal Tile Set**
// Applica un'imbottitura (padding) alla texture per evitare il "bleeding" (sbavature), impedendo che i pixel dei tile adiacenti appaiano ai bordi durante il movimento.

- **Aggiungere il Player Start(Basic)**
//Dall'add object aggiungi player start e posizioanlo nel mondo