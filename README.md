# EmberEagle2.0
Fire Fighting Robot
<h1 align="center">Fire Fighting Robot Arduino Code</h1>

<p align="center">
  <img src="robot_image.jpg" alt="Fire Fighting Robot" width="400" height="300">
</p>

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
}```

On the other hand, if a fire is detected straight ahead, the robot should move towards the fire. We achieve this by rotating the respective motors. We also set a variable named fire to true to indicate that the robot is in action:
