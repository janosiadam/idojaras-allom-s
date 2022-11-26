#include <dht.h>
#define dataPin 2 // a dataPin nevű változó definiálása (a 2-es lábra kötöttük)
dht DHT; // Létrehozzuk a DHT szenzorunkat
void setup() {
Serial.begin(9600);  
}
void loop() {
  delay(10000);
  
  int readData = DHT.read11(dataPin); // Kiolvassuk a szenzorból az értéket
  float t = DHT.temperature; // Megkapjuk a hőmérséklet értékét
  float h = DHT.humidity; // Megkapjuk a páratartalom értékét
                              
  Serial.print("Homerseklet:");// kiíratjuk az értékeket a soros monitorra
  Serial.print(t);
  Serial.println(" *C  ");
  Serial.print("paratartalom: ");
  Serial.print(h);
  Serial.println(" %");
  
  delay(1000); 
 
  int szel = analogRead(A0); //kiolvassuk a szélsebesség értéket
  Serial.print("Szel sebesseg:");Serial.print(szel); Serial.println(" km/h  " ); //kiiratjuk a szélsebesség értéket a soros monitorra
 
  delay(1000);

  double csap = analogRead(A4); // kiolvassuk a csapadék szint értékét
  Serial.print("csapadek:");// kiírjuk a csapadék szintet a soros monitorra
   if (csap < 23 ){Serial.print("0");}
   if (csap >= 23 && csap < 30){Serial.print("1");}
   if (csap >= 30 && csap < 34){Serial.print("2");} 
   if (csap >= 34 && csap < 38){Serial.print("3");}
   if (csap >= 38 && csap < 42){Serial.print("4");}
   if (csap >= 42 && csap < 46){Serial.print("5");} 
   if (csap >= 46 && csap < 51){Serial.print("6");}
   if (csap >= 51 && csap < 56){Serial.print("7");} 
   if (csap >= 56 && csap < 61){Serial.print("8");}   
   if (csap >= 61 && csap < 66){Serial.print("9");}   
   if (csap >= 66 && csap < 71){Serial.print("10");}  
   if (csap >= 71 && csap < 72){Serial.print("11");} 
   if (csap >= 72 && csap < 73){Serial.print("12");}   
   if (csap >= 73 && csap < 77){Serial.print("13");}   
   if (csap >= 77 && csap < 81){Serial.print("14");}   
   if (csap >= 81 && csap < 85){Serial.print("15");} 
   if (csap >= 85 && csap < 87){Serial.print("16");} 
   if (csap >= 87 && csap < 89){Serial.print("17");}   
   if (csap >= 89 && csap < 91){Serial.print("18");}   
   if (csap >= 91 && csap < 93){Serial.print("19");}   
   if (csap >= 93 && csap < 95){Serial.print("20");}   
   if (csap >= 95 && csap < 97){Serial.print("21");} 
   if (csap >= 97 && csap < 99){Serial.print("22");}   
   if (csap >= 99 && csap < 101){Serial.print("23");}   
   if (csap >= 101 && csap < 103){Serial.print("24");}   
   if (csap >= 103 && csap < 105){Serial.print("25");}   
   if (csap >= 105 && csap < 107){Serial.print("26");}   
   if (csap >= 107 && csap < 109){Serial.print("27");}   
   if (csap >= 109 && csap < 111){Serial.print("28");}   
   if (csap >= 111 && csap < 113){Serial.print("29");}   
   if (csap >= 113 && csap < 115){Serial.print("30");}   
 Serial.println(" mm ");

delay(1000);

int feny = analogRead(A2); // fény érzékelő értékének olvasása
Serial.print("fenyerosseg:");                      // fényerősség kiírása a soros monitorra
if (feny > 800){Serial.println("NAGYON FÉNYES");} 
if (600 < feny && feny < 800){Serial.println("FÉNYES");}
if (62 < feny && feny < 600){Serial.println("VILÁGOS");}
if (feny < 60 && feny > 2){Serial.println("SZÜRKÜLET");}
if (feny < 2){Serial.println("SÖTÉT");}
 }
