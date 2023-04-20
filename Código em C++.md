// C++ code
int celsius = 0;
int sensor = 0;
int motor = 2;
int led = 4;
int buzzer = 13;

void setup(){pinMode(A0, INPUT);
             pinMode(motor, OUTPUT);
             pinMode(led, OUTPUT);
             pinMode(buzzer, OUTPUT);
             Serial.begin(9600); 
            }
void loop(){
  //medir a temperatura em Celsius
  sensor=analogRead(A0);//este valor será digital de o 0 a 1023
  celsius=map(((analogRead(A0)- 20)*3.04),0,1023,-40,125);
  
  Serial.print ("Medida do Sensor =");
  Serial.println(sensor);
  Serial.print("Temperatura =");
  Serial.print(celsius);
  Serial.println("C. ");
  Serial.println(" ");
  delay(500);
  
  if(celsius<30){digitalWrite(motor, LOW);}
  if(celsius>=30){digitalWrite(motor, HIGH);}
  if(celsius>50){
  digitalWrite(led, HIGH);
  digitalWrite(buzzer, HIGH);}
  else{
   digitalWrite(led, LOW);
   digitalWrite(buzzer,LOW);
   delay (300);
   
  }
  }

