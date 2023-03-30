# Tímaverkefni 4

## Kóði

```cpp
// Motor A
int pwmA = 5;
int in1A = 3;
int in2A = 4;

// Motor B
int pwmB = 6;
int in1B = 7;
int in2B = 8;

// Stanby
int standby = 9;

// Motor Speed Values: 0 to 255
int MotorSpeed1 = 150;
int MotorSpeed2 = 150;


int fani = 1;

void setup()
{
  // Set all the motor control pins to outputs
  pinMode(standby, OUTPUT);
  pinMode(pwmA, OUTPUT);
  pinMode(pwmB, OUTPUT);
  pinMode(in1A, OUTPUT);
  pinMode(in2A, OUTPUT);
  pinMode(in1B, OUTPUT);
  pinMode(in2B, OUTPUT);
}

void loop()
{
  digitalWrite(standby, HIGH);

  if(fani==1) {
    // 1    
    fram(150);
    delay(1000);

    // 2
    stopp();
    delay(500);

    // 3    
    haegri(75);
    delay(665);

    // 4
    fram(100);
    delay(1000);

    // 5
    stopp();
    delay(500);

    // 6
    haegri(75);
    delay(665);

    // 7
    fram(150);
    delay(1000);

    // 8
    vinstri(75);
    delay(665);

    // 9
    aftur(100);
    delay(1000);

    // 10
    stopp();
    delay(500);

    // 11
    vinstri(75);
    delay(665);

    stopp();
    fani++;
  }
}


void fram(int hradi) {
	digitalWrite(in1A, HIGH);
	digitalWrite(in2A, LOW);
	digitalWrite(in1B, HIGH);
	digitalWrite(in2B, LOW);
	analogWrite(pwmA, hradi);
	analogWrite(pwmB, hradi + 5);
};

void aftur(int hradi) {
	digitalWrite(in1A, LOW);
	digitalWrite(in2A, HIGH);
	digitalWrite(in1B, LOW);
	digitalWrite(in2B, HIGH);
	analogWrite(pwmA, hradi);
	analogWrite(pwmB, hradi + 1);
};

void stopp() {
	digitalWrite(in1A, LOW);
	digitalWrite(in2A, LOW);
	digitalWrite(in1B, LOW);
	digitalWrite(in2B, LOW);
};

void haegri(int hradi) {
	digitalWrite(in1A, HIGH);
	digitalWrite(in2A, LOW);
	digitalWrite(in1B, LOW);
	digitalWrite(in2B, HIGH);
	analogWrite(pwmA, hradi);
	analogWrite(pwmB, hradi);
};

void vinstri(int hradi) {
	digitalWrite(in1A, LOW);
	digitalWrite(in2A, HIGH);
	digitalWrite(in1B, HIGH);
	digitalWrite(in2B, LOW);
	analogWrite(pwmA, hradi);
	analogWrite(pwmB, hradi);
};
```

## Myndband

![Myndband](https://user-images.githubusercontent.com/117899282/228880923-8092c10f-b39a-4e36-b005-1a96f9673baa.mp4)