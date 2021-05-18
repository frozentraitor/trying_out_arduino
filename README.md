# trying_out_arduino
int state=0;
int button=0;

void setup()
{
  pinMode(13, OUTPUT);
  pinMode(12, OUTPUT);
  pinMode(11, OUTPUT);
  pinMode(3,INPUT);
}

void loop()
{

button=digitalRead(3);
  if(button==HIGH)
  {delay (50);
   button=digitalRead(3);
   if(button==LOW)
   {
    state=state+1;
   }  
  }
  else
  {delay(100);
  }  

switch(state)
{
case 1 :
  digitalWrite(13,HIGH);
  digitalWrite(12,LOW);
  digitalWrite(11,LOW);
  break;
case 2 :
  digitalWrite(13,LOW);
  digitalWrite(12,HIGH);
  digitalWrite(11,LOW);
  break;
case 3 :
  digitalWrite(13,LOW);
  digitalWrite(12,LOW);
  digitalWrite(11,HIGH);
  state=0;
  break;
}
}  
