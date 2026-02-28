# Pedestrian and Vehicle Orientation Detection on PiCar-X 🚗🚶‍♂️

**Corso:** Fondamenti di Visione Artificiale e Biometria 2024/2025  
**Autori:** Andrea Salurso e Francesca Avallone  

## Obiettivo del Progetto
Questo progetto implementa un sistema efficiente e funzionale di Object Detection per il riconoscimento di pedoni e l'orientamento dei veicoli. È stato progettato per operare in tempo reale su una piattaforma hardware embedded (Raspberry Pi) integrata nel robot autonomo **PiCar-X**. Il sistema è in grado di rilevare pedoni, distinguere la prospettiva dei veicoli (fronte, retro e lato) e attivare le azioni appropriate in base al contesto stradale.

## Architettura e Modello
Per l'implementazione finale è stata utilizzata l'architettura **YOLOv11s**, selezionata per via delle sue ottime performance (bilanciamento tra velocità e precisione) rispetto ad altre versioni testate.
* **Dataset:** I dataset utilizzati per l'addestramento sono stati creati interamente da zero e annotati manualmente tramite lo strumento **Label-Studio**, garantendo una rappresentazione accurata e specifica delle classi di interesse.
* **Hardware:** Inferenza eseguita su Raspberry Pi a bordo del PiCar-X, dimostrando l'adattabilità del modello a dispositivi con risorse computazionali limitate (Edge AI).

## Risultati e Sviluppi Futuri
Il sistema ha dimostrato di essere rapido e preciso per applicazioni real-time. Come analizzato nel report, le direzioni future per migliorare ulteriormente il progetto includono:
* L'arricchimento del dataset con immagini raccolte in contesti non controllati e reali per migliorare la generalizzazione del modello.
* L'esplorazione di tecniche avanzate di **pruning** e **quantizzazione** del modello.
* L'impiego di acceleratori hardware dedicati (es. Edge TPU) per incrementare ulteriormente il framerate e ridurre i consumi energetici.

## Struttura della Repository
* `yolo_detect.py`: Script Python principale per eseguire l'inferenza su immagini, video o flussi video in tempo reale (es. webcam o PiCamera).
* `best.pt`: Pesi del modello YOLOv11s addestrato sul nostro custom dataset.
* `Object_Detection_Pedestrian_and_Vehicle_Orientation.pdf`: Relazione dettagliata del progetto.
* `requirements.txt`: Elenco delle dipendenze necessarie per eseguire il codice.

## Installazione e Utilizzo

1. Clona questa repository:
   ```bash
   git clone [https://github.com/TUO-USERNAME/picar-x-yolo-detection.git](https://github.com/TUO-USERNAME/picar-x-yolo-detection.git)
   cd picar-x-yolo-detection
2. Installa le dipendenze:
    ```bash
    pip install -r requirements.txt
3. Esegui lo script
    ```bash
   # Utilizzando la webcam standard (source 0)
    python yolo_detect.py --model best.pt --source 0

   # Utilizzando un file video
   python yolo_detect.py --model best.pt --source testvid.mp4
