# mad018
basic roughedge loop

![mad018](https://github.com/nicolasbaez/mad018/blob/master/mad018.gif)

```processing
int cantidad=360;
float[] xVert1 = new float[cantidad];
float[] xVert2 = new float[cantidad];
float[] xVert3 = new float[cantidad];
float[] yVert1 = new float[cantidad];
float[] yVert2 = new float[cantidad];
float[] yVert3 = new float[cantidad];
int[] rr = new int[cantidad];
int[] gg = new int[cantidad];
int[] bb = new int[cantidad];
float dVert=2;
float dColor=64;
float maxVertW;
float angStart=270;
float j=angStart;
void setup() {
  size(512, 256);
  background(255);
  noStroke();
  for (int i=0; i<cantidad; i++) {
    rr[i]=int(random(255));
    gg[i]=int(random(255));
    bb[i]=int(random(255));
  }
}
void draw() {
  background(255);
  maxVertW=map(sin(radians(j)), -1, 1, 4, 128);
  for (int i=0; i<cantidad; i++) {
    float radio=height*0.32;
    float xx=radio*cos(radians(j+map(i, 0, cantidad, 0, 360)))+width/2;
    float yy=radio*sin(radians(j+map(i, 0, cantidad, 0, 360)))+height/2;
    xVert1[i]=xVert1[i]+random(-dVert, dVert);

    if (xVert1[i]>maxVertW) {
      xVert1[i]-=dVert*2;
    }
    if (xVert1[i]<-maxVertW) {
      xVert1[i]+=dVert*2;
    }
    yVert1[i]=yVert1[i]+random(-dVert, dVert);
    if (yVert1[i]>maxVertW) {
      yVert1[i]-=dVert*2;
    }
    if (yVert1[i]<-maxVertW) {
      yVert1[i]+=dVert*2;
    }
    xVert2[i]=xVert2[i]+random(-dVert, dVert);
    if (xVert2[i]>maxVertW) {
      xVert2[i]-=dVert*2;
    }
    if (xVert2[i]<-maxVertW) {
      xVert2[i]+=dVert*2;
    }
    yVert2[i]=yVert2[i]+random(-dVert, dVert);
    if (yVert2[i]>maxVertW) {
      yVert2[i]-=dVert*2;
    }
    if (yVert2[i]<-maxVertW) {
      yVert2[i]+=dVert*2;
    }
    xVert3[i]=xVert3[i]+random(-dVert, dVert);
    if (xVert3[i]>maxVertW) {
      xVert3[i]-=dVert*2;
    }
    if (xVert3[i]<-maxVertW) {
      xVert3[i]+=dVert*2;
    }
    yVert3[i]=yVert3[i]+random(-dVert, dVert);
    if (yVert3[i]>maxVertW) {
      yVert3[i]-=dVert*2;
    }
    if (yVert3[i]<-maxVertW) {
      yVert3[i]+=dVert*2;
    }
    rr[i]=rr[i]+int(random(-dColor, dColor));
    if (rr[i]>255) {
      rr[i]-=dColor*2;
    }
    if (rr[i]<0) {
      rr[i]+=dColor*2;
    }
    gg[i]=gg[i]+int(random(-dColor, dColor));
    if (gg[i]>255) {
      gg[i]-=dColor*2;
    }
    if (gg[i]<0) {
      gg[i]+=dColor*2;
    }
    bb[i]=bb[i]+int(random(-dColor, dColor));
    if (bb[i]>255) {
      bb[i]-=dColor*2;
    }
    if (bb[i]<0) {
      bb[i]+=dColor*2;
    }
    fill(rr[i], gg[i], bb[i] );
    beginShape();
    vertex(xx+xVert1[i], yy+yVert1[i]);
    vertex(xx+xVert2[i], yy+yVert2[i]);
    vertex(xx+xVert3[i], yy+yVert3[i]);
    vertex(xx+xVert1[i], yy+yVert1[i]);
    endShape();
  }
  j+=1;
  if (j<=(360*2)+angStart) {
    saveFrame("gif/mad018-######.png");
  }
}
```
