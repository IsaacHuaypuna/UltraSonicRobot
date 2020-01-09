#Isaac & Liams Ultrasonic Flip Car

(ahem, write your planning and documentation here)

# The planning and the making of the utrasonic flip car

## The planning
When me and my partner got this assighnment it didn't take us long to think of a upside down driving flip car. The designe of the interior was pretty simple. 4 servos spinning the tires, battery powers the Arduino and the Arduino will have the program to make the sensor and servos work. Simple right? WRONG! The designe was pretty complicated but simple at the same time. The way the car looks affects the way on how the interior will look. I thought of a WW1 british tank would be cool but were would the tires go? An F1 car but it wouldn't realy look like an F1 without all of the spoilers. But eventually we turned our heads to just a simple look. A small look a like car with big wheeels. And that was it our car designe.

(adding a picture here later)

## The Coding
We had three main gaols. Working interior, code, and simple but fast car shell. The coding was a lot more simple than we thought. We thought that the car shell and wiring would be quick but the coding was the first thing we finished between the three. We were surprised about how quick it was.
Heres the code:

 #include <Servo.h>

Servo servoFR;
Servo servoFL;
Servo servoBR;
Servo servoBL;
int trigPin = 9;
int echoPin = 8;
long distance;
long duration;

void setup()
{
  servoFR.attach(7);
  servoFL.attach(6);
  servoBR.attach(5);
  servoBL.attach(4);
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);// put your setup code here, to run once:
}

void loop() {
  ultra();

  if (distance <= 10) {
    servoFR.write(180);
    servoFL.write(180);
    servoBR.write(180);
    servoBL.write(180);
  }
  else {
    servoFR.write(90);
    servoFL.write(90);
    servoBR.write(90);
    servoBL.write(90); 
  }
}


void ultra() {
  digitalWrite(trigPin, LOW);
  delayMicroseconds(0);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(0);
  digitalWrite(trigPin, LOW);
  duration = pulseIn(echoPin, HIGH);
  distance = duration * 0.034 / 2;
}



