//Design Lab 2023
//Kinect Sensor Music Tiles
//Mikołaj Grodoń Łukasz Trzaska

import SimpleOpenNI.*;
import ddf.minim.*;
SimpleOpenNI kinect;

int closestValue;
int closestX;
int closestY;

Minim minim;
AudioSnippet player;

void setup() {
  size(640, 480);
  kinect = new SimpleOpenNI (this);
  kinect.enableDepth();
}

void draw() {
  closestValue = 8000;

  kinect.update();

  int[] depthValues = kinect.depthMap();

  for(int y = 0; y < 480; y++) {
    for (int x = 0; x < 640; x++) {
      int i = x + y * 640;
      int currentDepthValue = depthValues[i];

      if(currentDepthValue > 0 && currentDepthValue < closestValue) {

       closestValue = currentDepthValue;

      closestX = x;
      closestY = y;
      }
    }
  }

image(kinect.depthImage(), 0, 0);

  fill(255, 0, 0, 155);
  rect(20, 0, 40, 480);
  fill(255, 128, 0, 155);
  rect(100, 0, 40, 480);
  fill(255, 255, 0, 155);
  rect(180, 0, 40, 480);
  fill(0, 255, 0, 155);
  rect(260, 0, 40, 480);
  fill(0, 255, 255, 155);
  rect(340, 0, 40, 480);
  fill(0, 0, 255, 155);
  rect(420, 0, 40, 480);
  fill(128, 0, 255, 155);
  rect(500, 0, 40, 480);
  fill(255, 0, 255, 155);
  rect(580, 0, 40, 480);

fill(155);
ellipse(closestX, closestY, 20, 20);

if(closestX < 60) {
  if(closestX > 20){
    minim = new Minim(this);
    player = minim.loadSnippet("Sound1.wav");
    player.play();
  }
}

if(closestX < 140) {
  if(closestX > 100){
    minim = new Minim(this);
    player = minim.loadSnippet("Sound2.wav");
    player.play();
  }
}

if(closestX < 220) {
  if(closestX > 180){
    minim = new Minim(this);
    player = minim.loadSnippet("Sound3.wav");
    player.play();
  }
}

if(closestX < 300) {
  if(closestX > 260){
    minim = new Minim(this);
    player = minim.loadSnippet("Sound4.wav");
    player.play();
  }
}

if(closestX < 380) {
  if(closestX > 340){
    minim = new Minim(this);
    player = minim.loadSnippet("Sound5.wav");
    player.play();
  }
}

if(closestX < 460) {
  if(closestX > 420){
    minim = new Minim(this);
    player = minim.loadSnippet("Sound6.wav");
    player.play();
  }
}

if(closestX < 540) {
  if(closestX > 500){
    minim = new Minim(this);
    player = minim.loadSnippet("Sound7.wav");
    player.play();
  }
}

if(closestX < 620) {
  if(closestX > 580){
    minim = new Minim(this);
    player = minim.loadSnippet("Sound8.wav");
    player.play();
  }
}
}

  void stop(){
    player.close();
    minim.stop();

    super.stop();
  }
