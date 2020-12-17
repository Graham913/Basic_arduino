# Basic_arduino

## LED blink revisited

Makes an LED fade in an out

### code

```C++

int led = 9;        
int brightness = 0; 
int fadeAmount = 5;


void setup() {

  pinMode(led, OUTPUT);
}


void loop() {

  analogWrite(led, brightness);


  brightness = brightness + fadeAmount;

  
  if (brightness <= 0 || brightness >= 255) {
    fadeAmount = -fadeAmount;
  }

  delay(10);
}


```

### Wiring
![Graham.circuit](images/graham.LEDblink.PNG)

### Reflection
 At the beginning it was easy until I reached the spicy part to make the LED fade in and out. I read through a couple forums to find the righttype of thing to use then it was just trial and error.






## finite LED blinker

make one LED blink 5 times then switch to another LED to blink 5 times then stop

### code

```c++
/*

*/
int ledPin = 9;
int maxnum = 5;
int counter = 0;
void setup() {

  pinMode(13, OUTPUT);
  pinMode(9, OUTPUT);
}

void loop()
{
  if (counter < maxnum) {
    digitalWrite(13, HIGH);

    delay(250);

    digitalWrite(13, LOW);

    delay(250);

    counter++;
  } else if (counter < (maxnum * 2)) {
    digitalWrite(9, HIGH);

    delay(250);

    digitalWrite(9, LOW);

    delay(250);

    counter++;
  } else {
  counter=0;
  }
}


```

### wiring

![Graham.circuit](images/Graham.5blink.png)


### reflection

This one was much more difficult then the last one because of I didnt really understand how code works at first then I got it explained to me so after a bit of problem solving I finally got it.
