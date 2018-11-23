//CODIGO VAGA ESTACIONAMENTO

/* 

------- Leds Vaga -------
Vaga1 = D52;
Vaga2 = D53;

------- Sensores Vaga -------
Vaga1 = A2;
Vaga2 = A3;

------- Sensores Entrada -------
Entrada_Abre = A6;
Entrada_Fecha = A7;

------- Sensores Saída -------
Saída_Abre = A1;
Saída_Fecha = A0;

*/

#include <Servo.h>

Servo myservo;  // create servo object to control a servo
// twelve servo objects can be created on most boards

Servo myservo1;

//PORTA DE ENTRADA
int valorLDR1; 
int valorLDR2;

//PORTA DE SAIDA
int valorLDR3;
int valorLDR4;

//VAGAS
int valorLDR_LED;
int LED = 52;
int vaga_01;

int valorLDR_LED2;
int LED2 = 53;
int vaga_02;

//Flag de controle
int vagaCheia = 12;
int vagaVazia = 10;


void setup() {


  
  Serial.begin(9600);

//FLAG DE CONTROLE
  pinMode(vagaCheia, OUTPUT);
  digitalWrite(vagaCheia, LOW);

  pinMode(10, OUTPUT);
  digitalWrite(10, HIGH);
//VAGAS  
  pinMode(LED, OUTPUT);
  digitalWrite(LED, LOW);
  vaga_01 = 0;
  
  pinMode(LED2, OUTPUT);
  digitalWrite(LED2, LOW);
  vaga_01 = 0;

  
 //PORTA DE ENTRADA
  myservo.attach(9);  // SERVOMOTOR NO DIGITAL 9
  myservo.write(0);
  myservo.write(90);
  
//PORTA DE SAIDA
  myservo1.attach(4);  // SERVOMOTOR NO DIGITAL 4
  myservo1.write(0);
  myservo1.write(90);
 
  
}

void loop() {


  

//PORTA DE ENTRADA 
  valorLDR1 = analogRead(A0);
  valorLDR2 = analogRead(A1);

 //PORTA DE SAIDA
  valorLDR3 = analogRead(A6);
  valorLDR4 = analogRead(A7);
  
//VAGAS 
  valorLDR_LED = analogRead(A2);
  valorLDR_LED2 = analogRead(A3);
  
//MONITORAR PORTA SAIDA
/*
  Serial.println("LDR_LED1_Saida: ");
  Serial.println(valorLDR1);
  Serial.println("LDR_LED2_Saida: ");
  Serial.println(valorLDR2);
*/

//MONITORAR PORTA ENTRADA
/*  Serial.println("valorLDR3_Entrada: ");
  Serial.println(valorLDR3);
  Serial.println("valorLDR4_Entrada: ");
  Serial.println(valorLDR4);
*/
//MONITORAR VAGAS
 /* Serial.println("LDR_LED_Vaga1: ");
  Serial.println(valorLDR_LED);
  Serial.println("LDR_LED2_Vaga2: ");
  Serial.println(valorLDR_LED2);
*/
//delay(800);
  
if(vaga_01 == 0 || vaga_02 == 0){
  
  digitalWrite(vagaVazia, HIGH);
 digitalWrite(vagaCheia, LOW);

//PORTA DE SAIDA
  if(valorLDR1 <= 20){              
    myservo.write(90);              // tell servo to go to position in variable 'pos'
    delay(15);
    }
    
   if(valorLDR2 <=10){
                myservo.write(0);              // tell servo to go to position in variable 'pos'
                 delay(15); 
   }

//PORTA DE ENTRADA
  if(valorLDR3 <= 30){              
    myservo1.write(180);              // tell servo to go to position in variable 'pos'
    delay(15);
    }
    
   if(valorLDR4 <= 50){
                myservo1.write(90);              // tell servo to go to position in variable 'pos'
                 delay(15); 
   } 

}else{
  digitalWrite(vagaVazia, LOW);
  digitalWrite(vagaCheia, HIGH);
  
}

//vaga
  if(valorLDR_LED < 400){
    digitalWrite(LED, LOW);
    vaga_01 = 1;
  }else{
    digitalWrite(LED, HIGH);
    vaga_01 = 0;
  }

  
  if(valorLDR_LED2 < 150){
    digitalWrite(LED2, LOW);
    vaga_02 = 1;
  }else{
    digitalWrite(LED2, HIGH);
    vaga_02 = 0;  
  }
   
   
}
