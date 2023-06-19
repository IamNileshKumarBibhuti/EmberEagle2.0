# EmberEagle2.0
Fire Fighting Robot
<h1 align="center">Fire Fighting Robot Arduino Code</h1>

<p align="center">
</p>
![EmberEagle](https://github.com/IamNileshKumarBibhuti/EmberEagle2.0/assets/76257165/9f229da9-b1c1-4314-98b6-136fe746a35e)

<p align="center">Welcome to the Fire Fighting Robot Arduino Code repository! This code will unleash the power of a robot that detects and extinguishes fires. Get ready for some fiery action!</p>

## Getting Started

Once you have all the necessary hardware components assembled, you're just a few steps away from witnessing the robot in action! To upload the Arduino code and bring this hero to life, follow these simple instructions:

1. Connect your Arduino board to your computer. Make sure it's wearing its cape!
2. Open the Arduino IDE and summon your programming powers.
3. Copy and paste the complete program provided at the end of this page into the Arduino IDE. The robot loves reading its code!
4. Verify and upload the code to your Arduino board. Watch as the robot springs into action to save the day!

## How It Works

As you know, the robot possesses a keen fire-detection sense. When a fire is detected, it exclaims "HIGH!" with excitement. When there is no fire, it whispers a timid "LOW." The robot is quite the drama queen!

The code continuously monitors the fire sensors to determine if any fire is present. If the robot doesn't sense any fire, it stays put, refusing to budge an inch. You know how stubborn robots can be!

```arduino
if (digitalRead(Left_S) == 1 && digitalRead(Right_S) == 1 && digitalRead(Forward_S) == 1) {
  // No fire detected, the robot remains stoic
  digitalWrite(LM1, HIGH);
  digitalWrite(LM2, HIGH);
  digitalWrite(RM1, HIGH);
  digitalWrite(RM2, HIGH);
}



On the other hand, if a fire is detected straight ahead, the robot should move towards the fire. 
We achieve this by rotating the respective motors. We also set a variable named fire to true to 
indicate that the robot is in action:

else if (digitalRead(Forward_S) == 0) {
  // Fire detected straight ahead, the robot boldly advances
  digitalWrite(LM1, HIGH);
  digitalWrite(LM2, LOW);
  digitalWrite(RM1, HIGH);
  digitalWrite(RM2, LOW);
  fire = true;
}



Once the robot's fire-fighting instincts are activated, it won't stop until the fire is extinguished. 
It tirelessly repeats the put_off_fire() function until peace is restored:

while (fire == true) {
  put_off_fire();
}



Inside the put_off_fire() function, the robot demonstrates its water-bending skills. 
It stops, activates the water pump, and gracefully wields its servo motor to disperse water evenly. 
It's like watching a choreographed dance!

void put_off_fire() {
  delay(500);
  digitalWrite(LM1, HIGH);
  digitalWrite(LM2, HIGH);
  digitalWrite(RM1, HIGH);
  digitalWrite(RM2, HIGH);

  digitalWrite(pump, HIGH);
  delay(500);

  for (pos = 50; pos <= 130; pos += 1) {
    myservo.write(pos);
    delay(10);
  }

  for (pos = 130; pos >= 50; pos -= 1) {
    myservo.write(pos);
    delay(10);
  }

  digitalWrite(pump, LOW);
  myservo.write(90);
  fire = false;
}
```
Now, sit back, relax, and let the Fire Fighting Robot save the world from fiery disasters! Please exercise caution while enjoying the show and keep a safe distance from both the flames and the robot.

Disclaimer: This code is purely for educational and entertainment purposes. The robot's fire-fighting capabilities are not intended for real-life emergencies, so please rely on professional fire-fighting services for actual fires.

So, are you ready to bring this heroic robot to life? Clone the repository, upload the code, and let the fire-fighting adventure begin!

🔥🤖💪
