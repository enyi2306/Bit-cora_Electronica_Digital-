float rotationAngle = 0;
float pos = 0;
PFont f;
String fullText = "La sangre que va al corazón. Es témpera roja que endurece el tiempo.";
String afullText = "Gigante. Gigante. Gigante. Gigante. Gigante.";

float pos2Max = 1000; // duración del recorrido — ajustable


void setup(){
  //fullScreen();
    size(1920,1000);
f= createFont("Soviet", 48);
  
  
  
}

void draw(){
  background(#EADCC9);


 





  //Letras
  pos += 5; // velocidad de movimiento

  float angle = radians(60.5);
  float dx = cos(angle);
  float dy = sin(angle);

  // punto de partida (dentro del área negra) menos el desplazamiento
  float startX = 1146;
  float startY = 832;
  float xPos = startX - pos * dx;
  float yPos = startY - pos * dy;

  pushMatrix();
  textFont(f);
  translate(xPos, yPos);
  rotate(angle);
  textSize(100);
  textAlign(LEFT, CENTER);
  fill(0);
  text(fullText, 0, 0);
  popMatrix();


if (pos > 3700) pos = 0;
 
 
  //Circulo rojo
  rotationAngle += 2;
  

  float wobble = sin(radians(frameCount * 4)) * 5; 
  float finalAngle = rotationAngle + wobble;

  pushMatrix();
  translate(1493, 555);
  rotate(radians(finalAngle));
  fill(#9D0E11);
  noStroke();
  arc(0, 0, 400, 400, radians(20), radians(340), PIE);
  popMatrix();




//triangulo rojo
  fill(#9D0E11);
  triangle(1, height*1/2, 1, 1, width*1/2, 1);


//triangulo negro
fill (#000000);
   triangle(width -1, height*1/3, width -1, height-1, width*1/3, height-1);
   
   
     pos += 5; // velocidad de movimiento

  float aangle = radians(331.5);
  float adx = cos(aangle);
  float ady = sin(aangle);

  // punto de partida (dentro del área negra) menos el desplazamiento
  float astartX = 768;
  float astartY = 1010;
  float xaPos = astartX - pos * adx;
  float yaPos = astartY - pos * ady;

  pushMatrix();
  textFont(f);
  translate(xaPos, yaPos);
  rotate(aangle);
  textSize(100);
  textAlign(LEFT, CENTER);
  fill(250);
  text(afullText, 0, 0);
  popMatrix();


if (pos > 3700) pos = -800;
 

 
 
 

}
  
