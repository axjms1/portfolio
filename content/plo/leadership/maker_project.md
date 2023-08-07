---
title: "Arduino Maker Project"
description: "Leadership - Artifact 3"
date: 2023-07-01
draft: false
tags: ["Leadership", "EDTECH 538", "Arduino", "Maker"]
weight: 30
---
This artifact is the final mini-project in the Maker Project Proposal I completed in EDTECH 538. It extends the simple circuit projects from earlier in the instructional unit by adding an [Arduino](https://www.arduino.cc/) program to control the circuit with software, a snippet of which is displayed below. Extending the Maker Project Proposal beyond [Scratch](https://scratch.mit.edu/) was a lot of fun and I really enjoyed learning more about microcontrollers.  Being given the latitude to explore this topic made the entire course more applicable to my current professional practice.

I have been invited to talk more about this project and others during an Hour of Code Week this fall in the Treasure Valley and am looking forward to it immensely.

{{< paige/code lang="c" >}}
 if (switchstate == LOW) {
    digitalWrite(3, HIGH);  // turn the green LED on pin 3 on
    digitalWrite(4, LOW);   // turn the red LED on pin 4 off
    digitalWrite(5, LOW);   // turn the red LED on pin 5 off
}
else {
    digitalWrite(3, LOW);   // turn the green LED on pin 3 off
    digitalWrite(4, LOW);   // turn the red LED on pin 4 off
    digitalWrite(5, HIGH);  // turn the red LED on pin 5 on
    // wait for a quarter second before changing the light
    delay(250);
    digitalWrite(4, HIGH);  // turn the red LED on pin 4 on
    digitalWrite(5, LOW);   // turn the red LED on pin 5 off
    // wait for a quarter second before changing the light
    delay(250);
  }
{{< /paige/code >}}

**[Arduino Maker Project](https://docs.google.com/document/d/1bFjoCCxGs849b87OtL7BdgAY6Qk8bupAH4GwhgUtrko/preview#bookmark=id.qqhb8aj8hi5r)**

{{< paige/gallery align="center" >}}
{{< paige/figure caption="Arduino Maker Project - Completed" >}}
{{< paige/image src="./plo/leadership/project_3_completed.jpg" width="80%" title="Arduino Maker Project - Completed" alt="BArduino Maker Project - Completed" >}}
{{< /paige/figure >}}
{{< paige/figure caption="Arduino Maker Project - In Action" >}}
{{< paige/image src="./plo/leadership/project_3_action.GIF" width="103%" title="Arduino Maker Project - In Action" alt="Arduino Maker Project - In Action" >}}
{{< /paige/figure >}}
{{< /paige/gallery >}}