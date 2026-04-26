
# Smart-streetlight-system
Title: Smart Street Light using LDR  Description: Built a simple automatic street light system using an LDR sensor and Arduino. The system turns lights ON/OFF based on ambient light conditions. This helped me understand sensor interfacing and basic microcontroller programming.



# CODE :

int ldrPin = A0;      // LDR connected to analog pin A0
int ledPin = 9;       // LED connected to digital pin 9

int ldrValue = 0;     // Variable to store LDR value

void setup() {
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  ldrValue = analogRead(ldrPin);  // Read LDR value
  Serial.println(ldrValue);       // Print value (for debugging)

  if (ldrValue < 500) {  
    digitalWrite(ledPin, HIGH);   // Turn ON LED (dark condition)
  } else {
    digitalWrite(ledPin, LOW);    // Turn OFF LED (light condition)
  }

  delay(500);
}
