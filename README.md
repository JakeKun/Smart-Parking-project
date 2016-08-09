# Smart-Parking-project

#include <LiquidCrystal.h>

// initialize the library with the numbers of the interface pins
LiquidCrystal lcd(12, 11, 5, 4, 3, 2);

#define trigPin 6
#define echoPin 7
#define led 13
#define led2 8
int readSen;

void setup() {
  lcd.begin(16, 2);
  //lcd.print("B1 is FULL!");
  Serial.begin (9600);
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  pinMode(led, OUTPUT);
  pinMode(led2, OUTPUT);
  // set up the LCD's number of columns and rows:
  
  }

void loop() {
  // set the cursor to column 0, line 1
  // (note: line 1 is the second row, since counting begins with 0):
  lcd.setCursor(0, 1);
  
  readSen=digitalRead( trigPin );
  readSen++;
  if(readSen>=5)  
  {
    lcd.print("B1 is FULL!");
    lcd.print("Drive to B2.");
  }
  else
  {
    lcd.print("Drive IN!");
  }
  
}

 
