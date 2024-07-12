#define adc 33
#define gpio 32
#define gpio1 35

void setup() {
  Serial.begin(115200);
  Serial.setTimeout(100);
  Serial.println("App started");
  pinMode(adc, INPUT);
  pinMode(gpio, INPUT);
  pinMode(gpio1, INPUT);
}

void loop() {
  if (Serial.available() > 0) {          
    String cmd = Serial.readStringUntil('\n');  // Đọc dữ liệu từ Serial cho đến khi gặp ký tự xuống dòng
    if (cmd == "T") {
      int analogValue = analogRead(adc);
      String output = "!1:T:" + String(analogValue) + "#";
      Serial.println(output);
    } else if (cmd == "H") {
      int digitalValue = digitalRead(gpio);
      String output = "!1:H:" + String(digitalValue) + "#";
      Serial.println(output);
    } else if (cmd == "S") {
      int digitalValue = digitalRead(gpio1);
      String output = "!1:S:" + String(digitalValue) + "#";
      Serial.println(output);
    }
  }
}
