# Bidaoui-Arduino
learning programming Arduino with C# forms

Code arduino : 
```
int incomingByte = 0; // for incoming serial data

    void setup() {
      Serial.begin(9600); // opens serial port, sets data rate to 9600 bps
    }

    void loop() {
      // reply only when you receive data:
      if (Serial.available() > 0) {
        // read the incoming byte:
        incomingByte = Serial.read();

        // say what you got:
        Serial.print("I received: ");
        Serial.println(incomingByte, DEC);
      }
    }
```

[library I/O ports](https://learn.microsoft.com/en-us/dotnet/api/system.io.ports.serialport?view=net-9.0-pp) - serial io library

### Convertisseurs USB-UART :
<div>
<img src="image_2025-03-12_044107297.png" width="500" height="300">
<img src="image_2025-03-12_050647562.png" width="500" height="300">
<div>


# Structure d'un câble USB

Le câble USB est constitué de plusieurs composants qui assurent sa fonctionnalité, y compris l'alimentation et la transmission de données. Voici la structure typique d'un câble USB :

## Tableau de structure

| Composant                | Description                                      | Couleur des fils | Fonction                                       |
|--------------------------|--------------------------------------------------|------------------|-----------------------------------------------|
| **Gaine extérieure**      | Protection contre les dommages physiques et EMI  | -                | Isolation et protection contre l'usure et la chaleur |
| **Blindage (Shielding)**  | Couche en aluminium ou cuivre pour éviter les interférences électromagnétiques (EMI) | -                | Réduction des bruits et interférences         |
| **Fil d'alimentation + (Vcc)** | Fil pour l'alimentation en tension positive (5V)  | Rouge            | Fournit l'alimentation pour le périphérique    |
| **Fil d'alimentation - (GND)** | Fil de masse (retour de courant)                  | Noir             | Sert de référence de masse                    |
| **Fil de données (D+)**   | Fil de transmission de données (ligne positive)  | Vert             | Utilisé pour la transmission des données      |
| **Fil de données (D-)**   | Fil de transmission de données (ligne négative)  | Blanc            | Utilisé pour la transmission des données      |

## Fonctionnement général

- **Alimentation** : Les fils Vcc (rouge) et GND (noir) sont utilisés pour fournir l'alimentation nécessaire au périphérique USB.
- **Transmission de données** : Les fils D+ (vert) et D- (blanc) sont utilisés pour l'échange de données entre les appareils connectés.
- **Protection** : Le blindage protège les fils internes contre les interférences électromagnétiques et garantit la stabilité du signal.

## Types de connecteurs USB

Le câble USB peut avoir différents types de connecteurs selon le modèle utilisé, tels que :
- **USB-A**
- **USB-B**
- **USB-C**
- **Micro-USB**
