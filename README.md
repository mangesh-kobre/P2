# P2
// Define pin numbers 
const int sensorPin = A0;  // LM35 connected to analog pin A0 
float temperatureC = 0;    // Variable to store temperature in Celsius 
void setup() { 
Serial.begin(9600);      // Start Serial Monitor at 9600 baud rate 
}
void loop() { 
int sensorValue = analogRead(sensorPin);  // Read analog value (0–1023) 
// Convert analog value to voltage (0–5V) 
float voltage = sensorValue * (5.0 / 1024.0); 
// Convert voltage to temperature in Celsius 
temperatureC = voltage / 0.01;  // LM35 gives 10mV per °C 
// Print result to Serial Monitor 
Serial.print("Temperature: "); 
Serial.print(temperatureC); 
Serial.println(" °C"); 
delay(1000);  // Wait for 1 second before next reading 
}
