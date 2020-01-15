#Isaac & Liams Ultrasonic Flip Car

(ahem, write your planning and documentation here)

# The planning and the making of the utrasonic flip car

## The planning
When me and my partner got this assighnment it didn't take us long to think of a upside down driving flip car. The designe of the interior was pretty simple. 4 servos spinning the tires, battery powers the Arduino and the Arduino will have the program to make the sensor and servos work. Simple right? WRONG! The designe was pretty complicated but simple at the same time. The way the car looks affects the way on how the interior will look. I thought of a WW1 british tank would be cool but were would the tires go? An F1 car but it wouldn't realy look like an F1 without all of the spoilers. But eventually we turned our heads to just a simple look. A small look a like car with big wheeels. And that was it our car designe. For now

(adding a picture here later of an RC car)

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

## Wiring
Wiring was in our mines hard but in reality it was easy, well with the right technology it was easy. The coding was the second thing we finished for the flip car. Choosing what we want and need for the wiring was a little difficult but we managed to find out what we need and don't.Before we started on the wiring we need a general idea on how to make four servos work at the same time. So we wnet on the web and found some pictures from the CHS wiki page or whatever it's called about what were looking for. A wiring that has four servos and a UltraSonic sensor working. This was just what we needed. This was the picture we found.

(Picture of wiring that we were inspired.)

Our wiring was somewhat similar to this. This is a picture of our wiring.

(picture of our wiring)


## Car Shell
The shell was the one thing we thought would be easy but actually its the hardest thing out of the three things we did. The model of the shell kept changing. From a WWI British tank to an F1 car to a simple small car with big wheels to now a 1983-88 Chevrolet Monte Carlo with big wheels.
(image of a WWI british tank)
(image of F1 Car)
(image of 1988 Monte Carlo)

The making of the car has been delayed cause my partner isn't here and he has a pice of the car interior that I don't have and I don't know what it looks like. Only my partner has it in his computer. So until my partner comes back and sends me the part he made for the interior I can't really work on the interior or the shell of the car unless I use some guess work and it could make my partners part useless or the part I made useless 
