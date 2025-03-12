# Bidaoui-Arduino
learning programming Arduino with C# forms

Code C# (WinForms) :
```
using System;
using System.IO.Ports;
using System.Windows.Forms;

namespace ArduinoControl
{
    public partial class Form1 : Form
    {
        SerialPort serialPort = new SerialPort("COM3", 9600); // Remplace COM3 par le bon port

        public Form1()
        {
            InitializeComponent();
            serialPort.Open();  // Ouvre la connexion série
        }

        private void btnOn_Click(object sender, EventArgs e)
        {
            serialPort.Write("1");  // Envoie '1' pour allumer la LED
        }

        private void btnOff_Click(object sender, EventArgs e)
        {
            serialPort.Write("0");  // Envoie '0' pour éteindre la LED
        }

        private void Form1_FormClosing(object sender, FormClosingEventArgs e)
        {
            if (serialPort.IsOpen)
                serialPort.Close();  // Ferme le port série à la fermeture du programme
        }
    }
}

```
Code arduino : 
```
int ledPin = 13;  // LED sur la broche 13
char command;  

void setup() {
    pinMode(ledPin, OUTPUT);
    Serial.begin(9600);  // Communication série avec le PC
}

void loop() {
    if (Serial.available() > 0) {  // Vérifie si une commande est reçue
        command = Serial.read();  // Lit la commande
        if (command == '1') {
            digitalWrite(ledPin, HIGH);  // Allumer la LED
        } else if (command == '0') {
            digitalWrite(ledPin, LOW);   // Éteindre la LED
        }
    }
}

```

[library I/O ports](https://learn.microsoft.com/en-us/dotnet/api/system.io.ports.serialport?view=net-9.0-pp) - serial io library



## Structure d'un câble USB

####  Un câble USB standard contient 4 à 5 fils, selon la version :
<table>
    <tr>
        <td><img src="image_2025-03-12_075322231.png" alt="Schéma Arduino" width="400"></td>
        <td>
            <table >
                    <tr>
                        <th>Fil</th>
                        <th>Couleur</th>
                        <th>Fonction</th>
                    </tr>
                    <tr>
                        <td><code>VCC (5V)</code></td>
                        <td>Rouge</td>
                        <td>Alimentation (5V DC)</td>
                    </tr>
                    <tr>
                        <td><code>D+</code></td>
                        <td>Vert</td>
                        <td>Transmission de données</td>
                    </tr>
                    <tr>
                        <td><code>D-</code></td>
                        <td>Blanc</td>
                        <td>Réception de données</td>
                    </tr>
                    <tr>
                        <td><code>GND</code></td>
                        <td>Noir</td>
                        <td>Masse électrique</td>
                    </tr>
            </table>
        </td>
    </tr>
</table>


### Convertisseurs USB-UART :
<div>
<img src="image_2025-03-12_044107297.png" width="400" height="300">
<img src="image_2025-03-12_050647562.png" width="400" height="300">
<div>
