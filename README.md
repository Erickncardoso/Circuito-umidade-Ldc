![image](https://github.com/user-attachments/assets/9517fba5-9c30-4304-a1f1-598d4ab6ddd1)



#include <LiquidCrystal_I2C.h>
LiquidCrystal_I2C lcd(0x27,16,2);
int status = 0;
String  texto = "";

void setup() {
  Serial.begin(9600);
  Serial.println("Digite algo");
 lcd.init();
 lcd.backlight();
 lcd.setCursor(3, 0);
 lcd.print("Bem - vindo");
 lcd.setCursor(0, 1);
 lcd.print("vinheria Agnello");
 delay(3000);
lcd.clear();
delay(1000);
lcd.setCursor(0,0);
lcd.print(".");
delay(500);
lcd.setCursor(1,0);
lcd.print(".");
delay(500);
lcd.setCursor(2,0);
lcd.print(".");
delay(500);
lcd.setCursor(3,0);
lcd.print(".");
delay(500);
lcd.setCursor(4,0);
lcd.print(".");
delay(4000);

}


void loop() {
lcd.clear();
lcd.setCursor(0, 0);
lcd.print("Temperatura: 28*");
lcd.setCursor(0, 1);
lcd.print("Umidade: 60%");
delay(2000);

if((Serial).available()>0){
  texto = Serial.readString();
  lcd.clear();
  lcd.setCursor(0,0);
  lcd.print(texto);
  delay(2000);
}
}
