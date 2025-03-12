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
<img src="image_2025-03-12_044107297.png" width="400" height="300">
<img src="image_2025-03-12_050647562.png" width="400" height="300">
<div>

## Structure d'un câble USB

####  Un câble USB standard contient 4 à 5 fils, selon la version :

<img src="image_2025-03-12_075322231.png" width="400" height="300">


|  Fil|   Couleur   |     Fonction            |
| :-------- | :------- | :------------------------- |
| `VCC (5V)` | Rouge  |Alimentation (5V DC) |
| `D+` | Vert |Transmission de données|
| `D-` | Blanc |		Réception de données|
| `GND` | Noir |Masse électrique|
