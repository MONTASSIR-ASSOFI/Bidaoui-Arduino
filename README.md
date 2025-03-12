# Bidaoui-Arduino
learning programming Arduino with C# forms

code arduino : 
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
<img src="https://www.google.com/url?sa=i&url=https%3A%2F%2Flearn.sparkfun.com%2Ftutorials%2Fserial-communication%2Fuarts&psig=AOvVaw1VN9wnfoxS79S2qvwuLQ4D&ust=1741833845986000&source=images&cd=vfe&opi=89978449&ved=0CBQQjRxqFwoTCKjpyZXEg4wDFQAAAAAdAAAAABAZ" width="150">
