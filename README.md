#include <WiFi.h>
#include <HTTPClient.h>
const char* ssid = "Aa";
const char* password = "12345678";
String apiKey = "L81BJCZL5ESG29YV";  
const charserver = "http://api.thingspeak.com/update";
void setup() {
  Serial.begin(115200);
  WiFi.begin(ssid, password);
  Serial.print("Connecting");
  while (WiFi.status() != WL_CONNECTED) {
    delay(500);
    Serial.print(".");
  }
  Serial.println("\Connected to WiFi!");
}
void loop() {
  if (WiFi.status() == WL_CONNECTED) {
    HTTPClient http;
    int randomValue = random(0, 1023); 
    String url = server;
    url += "?api_key=" + apiKey + "&field1=" + String(randomValue);
    http.begin(url);
    int httpCode = http.GET();
    if (httpCode > 0) {
      String payload = http.getString();
      Serial.print("Response: ");
      Serial.println(payload);
    } else {
      Serial.print("Error code: ");
      Serial.println(httpCode);
    }
    http.end();
  }
  delay(15000); 
}
