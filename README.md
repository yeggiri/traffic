# traffic
#아두이노 신호등
#define A 7

#define B 8

#define C 9

#define D 10

#define E 11

#define F 12

#define G 13

int fnd[7] = {A, B, C, D, E, F, G};

int data[7][7] = {

  {0, 1, 0, 0, 1, 0, 0}, //5

  {1, 0, 0, 1, 1, 0, 0}, //4

  {0, 0, 0, 0, 1, 1, 0}, //3

  {0, 0, 1, 0, 0, 1, 0}, //2

  {1, 0, 0, 1, 1, 1, 1}, //1

  {0, 0, 0, 0, 0, 0, 1}, //0

  {1, 1, 1, 1, 1, 1, 1}, //다 꺼짐

};

int a, b, num = 0, j = 0;

 

 

void setup() {

  for (int i = 0; i < 7; i++)

  {

    pinMode(fnd[i], OUTPUT);

  }

  pinMode(0, OUTPUT); //차량 빨간불

  pinMode(1, OUTPUT); //차량 노란불

  pinMode(2, OUTPUT); //차량 파란불

 

  pinMode(3, OUTPUT); //사람 빨간불

  pinMode(4, OUTPUT); //사람 파란불

 

  pinMode(5, OUTPUT); //부저

}

 

 

 

void loop() {

 

  digitalWrite(0, LOW);

  digitalWrite(1, LOW);

  digitalWrite(2, HIGH);

  digitalWrite(3, HIGH);

  digitalWrite(4, LOW);

  digitalWrite(5, LOW);

  delay(10000);

 

  digitalWrite(0, LOW);

  digitalWrite(1, HIGH);

  digitalWrite(2, LOW);

  digitalWrite(3, HIGH);

  digitalWrite(4, LOW);

  digitalWrite(5, LOW);

  delay(3000);

 

  digitalWrite(0, HIGH);

  digitalWrite(1, LOW);

  digitalWrite(2, LOW);

  digitalWrite(3, HIGH);

  digitalWrite(4, LOW);

  digitalWrite(5, LOW);

  delay(1500);

 

 

  for (b = 1; b <= 5; b++) {

    digitalWrite(0, HIGH);

    digitalWrite(1, LOW);

    digitalWrite(2, LOW);

    digitalWrite(3, LOW);

    digitalWrite(4, HIGH);

    digitalWrite(5, HIGH);

    delay(500);

 

    digitalWrite(0, HIGH);

    digitalWrite(1, LOW);

    digitalWrite(2, LOW);

    digitalWrite(3, LOW);

    digitalWrite(4, HIGH);

    digitalWrite(5, LOW);

    delay(500);

  }

 

  for (a = 0; a <= 6; a++)

  {

    

    digitalWrite(0, HIGH);

    digitalWrite(1, LOW);

    digitalWrite(2, LOW);

    digitalWrite(3, LOW);

    digitalWrite(4, LOW);

    digitalWrite(5, HIGH);

    delay(500);

 

    digitalWrite(0, HIGH);

    digitalWrite(1, LOW);

    digitalWrite(2, LOW);

    digitalWrite(3, LOW);

    digitalWrite(4, HIGH);

    digitalWrite(5, LOW);

    delay(500);

 

    for(int j=0; j<=6; j++) {

    digitalWrite(fnd[j], !data[a][j]); }

  }
