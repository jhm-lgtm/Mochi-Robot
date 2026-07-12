#include <Wire.h>
#include <Adafruit_GFX.h>
#include <Adafruit_SSD1306.h>

#define SCREEN_WIDTH 128
#define SCREEN_HEIGHT 64

// OLED pins
#define SDA_PIN 8
#define SCL_PIN 9

// Touch sensor pin
#define TOUCH_PIN 4

Adafruit_SSD1306 display(SCREEN_WIDTH, SCREEN_HEIGHT, &Wire, -1);

void setup() {
  Serial.begin(115200);

  pinMode(TOUCH_PIN, INPUT);

  // Initialize I2C
  Wire.begin(SDA_PIN, SCL_PIN);

  // Initialize OLED (change 0x3C to 0x3D if needed)
  if (!display.begin(SSD1306_SWITCHCAPVCC, 0x3C)) {
    Serial.println("OLED not found!");
    while (true);
  }

  display.clearDisplay();
  display.setTextSize(2);
  display.setTextColor(SSD1306_WHITE);
  display.setCursor(15, 10);
  display.println("HELLO!");
  display.setTextSize(1);
  display.setCursor(10, 45);
  display.println("ESP32-C3 Super Mini");
  display.display();

  Serial.println("OLED Started!");
}

void loop() {

  if (digitalRead(TOUCH_PIN) == HIGH) {

    display.clearDisplay();
    display.setTextSize(2);
    display.setCursor(20, 25);
    display.println("TOUCHED!");
    display.display();

    Serial.println("Touched!");

    delay(1000);

    display.clearDisplay();
    display.setTextSize(2);
    display.setCursor(15, 10);
    display.println("HELLO!");
    display.setTextSize(1);
    display.setCursor(10, 45);
    display.println("ESP32-C3 Super Mini");
    display.display();
  }
}
