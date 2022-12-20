var stillPlaying = true;
var cScene = 1; 
var temp = 0;
var score = 0;
var Beaver = function(x, y) {
    this.x = x;
    this.y = y;
    this.img = getImage("space/rocketship");
    this.sticks = 0;
};

//Jonathan's Bitmoji
 var yPos = 100;//yPos+ or yPos-
 var xPos = 100;//xPos+ or XPos-
 var Heightbitmoji = 150;// (Heightbitmoji/150* )
var drawBitmoji = function(xPos, yPos, Heightbitmoji)
{
noStroke();
fill(255,205,148);// Skin Color
ellipse(xPos+(Heightbitmoji/150*200), yPos+(Heightbitmoji/150*149), Heightbitmoji/150*92, Heightbitmoji/150*107);// Head

fill(3, 3, 3); // Hair Color
arc(xPos+(Heightbitmoji/150*200), yPos+(Heightbitmoji/150*121), Heightbitmoji/150*113, Heightbitmoji/150*-93, 41, 132);
arc(xPos+(Heightbitmoji/150*242), yPos+(Heightbitmoji/150*133), Heightbitmoji/150*91, Heightbitmoji/150*-89, 91, 124);
arc(xPos+(Heightbitmoji/150*156), yPos+(Heightbitmoji/150*129), Heightbitmoji/150*100, Heightbitmoji/150*-87, 41, 82);

fill(10, 9, 9);// Headphones
ellipse(xPos+(Heightbitmoji/150*147), yPos+(Heightbitmoji/150*140), Heightbitmoji/150*25, Heightbitmoji/150*24);
ellipse(xPos+(Heightbitmoji/150*253), yPos+(Heightbitmoji/150*139), Heightbitmoji/150*22, Heightbitmoji/150*24);
rect(xPos+(Heightbitmoji/150*144), yPos+(Heightbitmoji/150*71), Heightbitmoji/150*8, Heightbitmoji/150*79);
rect(xPos+(Heightbitmoji/150*147), yPos+(Heightbitmoji/150*71), Heightbitmoji/150*108, Heightbitmoji/150*7);
rect(xPos+(Heightbitmoji/150*250), yPos+(Heightbitmoji/150*76), Heightbitmoji/150*7, Heightbitmoji/150*69);

fill(10, 9, 9);// Eye brown color
ellipse(xPos+(Heightbitmoji/150*179), yPos+(Heightbitmoji/150*130), Heightbitmoji/150*16, Heightbitmoji/150*4); // Eye Brown Shape
ellipse(xPos+(Heightbitmoji/150*218), yPos+(Heightbitmoji/150*130), Heightbitmoji/150*16,Heightbitmoji/150*4); // Eye Brown Shape

fill(245, 242, 245);// Eye color
ellipse(xPos+(Heightbitmoji/150*180), yPos+(Heightbitmoji/150*142), Heightbitmoji/150*17, Heightbitmoji/150*10);// Eye Shape
ellipse(xPos+(Heightbitmoji/150*218), yPos+(Heightbitmoji/150*142), Heightbitmoji/150*17, Heightbitmoji/150*10);// Eye Shape

fill(5, 4, 4);
ellipse(xPos+(Heightbitmoji/150*180), yPos+(Heightbitmoji/150*142), Heightbitmoji/150*8, Heightbitmoji/150*5);// Eyeball Shape
ellipse(xPos+(Heightbitmoji/150*218), yPos+(Heightbitmoji/150*142), Heightbitmoji/150*8, Heightbitmoji/150*5);// Eyeball Shape

fill(255, 255, 255);// Teeth
arc(xPos+(Heightbitmoji/150*200), yPos+(Heightbitmoji/150*169), 38, 31, -16, 187);

fill(255,205,148);
stroke(10, 10, 10);// nose
arc(xPos+(Heightbitmoji/150*200), yPos+(Heightbitmoji/150*136), Heightbitmoji/150*33, Heightbitmoji/150*52, 61, 121);

fill(255, 255, 255);// Teeth
stroke(0, 0, 0);
arc(xPos+(Heightbitmoji/150*200), yPos+(Heightbitmoji/150*168), Heightbitmoji/150*35, Heightbitmoji/150*17, 2, 162);

noStroke();
fill(120, 111, 120);// Shirt
rect( xPos+(Heightbitmoji/150*154), yPos+(Heightbitmoji/150*201), Heightbitmoji/150*82,Heightbitmoji/150*83);
arc( xPos+(Heightbitmoji/150*147), yPos+(Heightbitmoji/150*259), Heightbitmoji/150*113, Heightbitmoji/150*117, 187, 283);
arc( xPos+(Heightbitmoji/150*240), yPos+(Heightbitmoji/150*269), Heightbitmoji/150*137, Heightbitmoji/150*137, -95, -3);
};

//Duck Model
var xPosition = 100;
var yPosition = 100;
var HeightDuck = 150;

var FlappyDuck = function(xPosition, yPosition, HeightDuck){
    
//Duck Head   
noStroke();
fill(255, 234, 0);
ellipse(xPosition+(HeightDuck/125*200), yPosition+(HeightDuck/296*149), HeightDuck/133*92, HeightDuck/150*107);

//Duck Face(Eyes and Beak)
stroke(0, 0, 0);
fill(255, 255, 255);
ellipse(xPosition+(HeightDuck/122*200), yPosition+(HeightDuck/373*149), HeightDuck/541*92, HeightDuck/601*107);
fill(0, 0, 0);
ellipse(xPosition+(HeightDuck/122*200), yPosition+(HeightDuck/370*149), HeightDuck/785*92, HeightDuck/876*107);
noStroke();
fill(255, 132, 0);
rect(xPosition+(HeightDuck/110*200), yPosition+(HeightDuck/303*149), HeightDuck/341*92, HeightDuck/852*107);

//Duck Body 
noStroke();
fill(255, 234, 0);
ellipse(xPosition+(HeightDuck/150*200), yPosition+(HeightDuck/153*149), HeightDuck/89*92, HeightDuck/150*107);
stroke(0, 0, 0);
ellipse(xPosition+(HeightDuck/142*193), yPosition+(HeightDuck/160*149), HeightDuck/145*95, HeightDuck/297*107);
};

// Lj's Bitmoji
var drawHead = function(x,y,bitH){

noStroke();
fill(241, 194, 125); // skintone fill
ellipse(x + bitH/100,y + bitH/100,bitH/100*79,bitH/100*100); //head
fill(197, 212, 36); // white fill
arc(x- bitH/100*42,y+bitH/100*37,bitH/100*36,bitH/100*60,0,360); //left chisel
fill(197, 212, 36); // white fill
arc(x+bitH/100*40,y+bitH/100*37,bitH/100*36,bitH/100*60,0,360); //right chisel
fill(36,28,17); //brown hair fill
quad(x-bitH/100*44,y+bitH/100*6, x-bitH/100*29, y-bitH/100*35, x-bitH/100*10, y-bitH/100*50, x-bitH/100*24, y-bitH/100*28); // leftside hair
fill(36, 28, 17); // brown hair fill
quad(x+bitH/100*40,y+bitH/100*8, x+bitH/100*35, y-bitH/100*25, x+bitH/100*13, y-bitH/100*50,x+bitH/100*35, y-bitH/100*10); // rightside hair
fill(36, 28, 17); // brown hair fill
ellipse(x + bitH/100, y-bitH/100*42,bitH/100*48,bitH/100*15); // top hair
fill(99,57,15); // hazel eye fill
ellipse(x-bitH/100*11,y-bitH/100*8,bitH/100*7,bitH/100*7); // left eye
fill(99,57,15); // hazel eye fill
ellipse(x+bitH/100*15,y-bitH/100*6,bitH/100*7,bitH/100*7); // right eye
stroke(10, 10, 10);
fill (0,0,0);//glasses
rect (x-bitH/100*14, y-bitH/100*11, bitH/100*7, bitH/100*9) ; // left lens
rect (x+bitH/100*11, y-bitH/100*11, bitH/100*7,bitH/100*9) ; // right lens
fill (4, 0, 250); // glasses color
rect (x+bitH/100*13,y-bitH/100*10, bitH/100*-20,bitH/100*4) ; //center of glasses
rect(x+bitH/100*37,y-bitH/100*8,bitH/100*-19,bitH/100*3,bitH/100*-6);// right wing for glasses
rect(x-bitH/100*15,y-bitH/100*9,bitH/100*-19,bitH/100*3,bitH/100*6); //left wing for glasses
fill(241,194,125); // skintone fill for nose
bezier(x+bitH/100,y-bitH/100*9,x+bitH/100*20,y+bitH/100*21,x-bitH/100*9,y+bitH/100*19,x-bitH/100*3,y+bitH/100*16); //nose
fill(255,255,255); // white fill for mouth
arc(x+bitH/100*3,y+bitH/100*25,bitH/100*30,bitH/100*13,1,180); //mouth
line(x-bitH/100*14,y+bitH/100*24,x+bitH/100*19,y+bitH/100*24); // top lip
};
var drawBody = function(x,y,bitH){
noStroke();
fill(240, 26, 26);
rect(x-bitH/100*50,y+bitH/100*46,bitH/100*100,bitH/100*100); //shirt
stroke(20, 17, 17);
arc(x+bitH/100*49,y+bitH/100*69,bitH/100*28,bitH/100*43,0,374); //left chisel
arc(x-bitH/100*45,y+bitH/100*69,bitH/100*28,bitH/100*43,0,374); //right chisel
noStroke();
fill(197, 212, 36);
rect(x+bitH/100*37,y+bitH/100*91,bitH/100*48,bitH/100*75);
rect(x-bitH/100*80,y+bitH/100*91,bitH/100*48,bitH/100*75);
fill(20, 18, 18);
text("LJ",x-bitH/100*10,y+bitH/100*65,bitH/100*130,bitH/100*50);
};
var drawBit = function(x,y,bitH){
    drawHead(x,y,bitH);
     drawBody(x,y,bitH);
};

//khan button class
var Button = function(config) {
    this.x = config.x || 0;
    this.y = config.y || 0;
    this.width = config.width || 150;
    this.height = config.height || 50;
    this.label = config.label || "Click";
    this.onClick = config.onClick || function() {};
    this.text = config.text || 19;
};

Button.prototype.draw = function() {
    noStroke();
    fill(255, 0, 0);
    rect(this.x, this.y, this.width, this.height,5);
    fill(255, 255, 255);
    textSize(this.text);
    textAlign(LEFT,TOP);
    text(this.label, this.x+10, this.y+this.height/4);
};

Button.prototype.isMouseInside = function() {
    return mouseX > this.x &&
           mouseX < (this.x + this.width) &&
           mouseY > this.y &&
           mouseY < (this.y + this.height);
};

Button.prototype.handleMouseClick = function() {
    if (this.isMouseInside()) {
        this.onClick();
    }
};

var startBtn = new Button 
    ({
    x: 120,
    y:291,
    label: "     START",
    onClick : function() {
        cScene = 0;
    }
    });

Beaver.prototype.draw = function() {
    fill(255, 0, 0);
    this.y = constrain(this.y,0, height-40);
    image(this.img, this.x, this.y, 60, 60);
};

Beaver.prototype.hop = function() {
    this.img = getImage("space/rocketship");
    this.y -= 5;
};

Beaver.prototype.fall = function() {
    this.img = getImage("space/rocketship");
    this.y += 5;
};

var Stick = function(x, height, isTop) {
    this.x = x;
    this.height = height;
    this.isTop = isTop;
};

Stick.prototype.draw = function() {
    fill(62, 161, 0);
    rectMode(CENTER);
    if(this.isTop) {
        rect(this.x, this.height-this.height, 5, this.height); }
        else {rect(this.x, this.height+200, 5, this.height+100);}
};

var beaver = new Beaver(205, 55);

var sticks = [];
for (var i = 0; i < 40; i++) { 
    if(sticks[i] <=40){
        this.sticks++;
    }
    var pipeHeight= random(100,430);
    temp = pipeHeight;
    sticks.push(new Stick(i * 105 + 305, pipeHeight, true));
    sticks.push(new Stick(i * 110 + 290, pipeHeight, false));
}

var grassXs = [];
for (var i = 0; i < 25; i++) {grassXs.push(i*20);}

Beaver.prototype.checkForStickPass = function(stick) {
    if(stick.x === 194){this.sticks++;score = this.sticks/2;}
};

Beaver.prototype.checkForStickGrab = function(stick) {
    if ((stick.x >= this.x && stick.x <= (this.x + 42))) {
        
    if(stick.isTop && this.y > 0 && this.y < (stick.height/2)-10) {
                    
cScene = 1;}
     
    else if (!stick.isTop &&  this.y >stick.height+100-(stick.height/2)){
           
cScene = 2;}

}
    
};



 var game = function() 
{
 background(255, 0, 43);
    fill(102, 60, 33);
    rectMode(CORNER);
    rect(0, height*0.90, width, height*0.10);
    
    for (var i = 0; i < grassXs.length; i++) {
        image(getImage("cute/GrassBlock"), grassXs[i], height*0.85, 25, 25);
        grassXs[i] -= 2;
        if (grassXs[i] <= -25) {grassXs[i] = width;}
    }
    
    for (var i = 0; i < sticks.length; i++) {
       
        sticks[i].draw();
        beaver.checkForStickGrab(sticks[i]);
        beaver.checkForStickPass(sticks[i]);
       if(sticks[10].x < 0){ // how fast he goes at 10
            sticks[i].x -=2;}
            else if (sticks[15].x < 0) { // how fast he goes at 15
            sticks[i].x -= 3;}
            else {
            sticks[i].x -= 1;} // how fast he goes before 10
    }
    
    textSize(20);
    text("Score = " + score, 18, 35);
    if (beaver.sticks/sticks.length >= 0.95) {
        textSize(36);
        text("Winner!", 105, 205);}
    if (keyIsPressed && keyCode === 0) {
        beaver.hop();}
        else {
        beaver.fall();}
    beaver.draw();};
var GameMenu = function() {
    stillPlaying = false;
    background(197, 212, 36);
    fill(247, 30, 48);
    textSize(28);
    text("Flappy Duck",111,50);//text
    textSize(20);
    text("Jonathan Lakavichit",195,380);//Jon's Name
    text("Lj Tirado", 38, 379);// Lj's Name
    drawBitmoji(232, 207, 69);
    FlappyDuck(18,106,127);
    drawBit(67,246,62);
    startBtn.draw();
    
};
var splashScreen = function(){
 startBtn.draw();
 GameMenu();

};

if(cScene === 1)
{splashScreen();}

var gameOver = function(){
        background(255, 0, 0);
        fill(0, 0, 0);
        textSize(40);
        text(" Game Over :(",100,105);
        text("Final Score:",100,205);
        text(score,210,250);
};

draw = function() {
    // static
    //0: game 1:Splash Screen  2: Game Over Screen
if(cScene === 0) 
{game();}

if(cScene===2){
gameOver();
    }


mouseClicked = function () 
{
if (cScene === 1)
{
    startBtn.handleMouseClick();
}
};




    };
    
    

