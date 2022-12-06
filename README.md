# Final-Project
var stillPlaying = true;
var Button = function(config) {
    this.x = config.x || 0;
    this.y = config.y || 0;
    this.width = config.width || 120;
    this.height = config.height || 45;
    this.label = config.label || "Click";
};
// Prototype
Button.prototype.draw = function() {
    fill(255, 255, 255);
    rect(this.x, this.y, this.width, this.height, 16);
    fill(0, 0, 0);
    textSize(19);
    textAlign(LEFT, TOP);
    text(this.label, this.x+41, this.y+this.height/4);
};
//Button's pressing works
Button.prototype.isMouseInside = function() {
    return mouseX > this.x &&
           mouseX < (this.x + this.width) &&
           mouseY > this.y &&
           mouseY < (this.y + this.height);
};

// makes start button
var button1 = new Button({
    x: 141,
    y: 283,
    label: "Start"
});
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

// Main menu
var GameMenu = function() {
    stillPlaying = false;
    background(197, 212, 36);
    fill(247, 30, 48);
    textSize(28);
    text("Flappy Duck",101,50);//text
    textSize(20);
    text("Press Start to play the game. ", 71,82,305,263);
    textSize(20);
    text("Jonathan Lakavichit",195,380);//Jon's Name
    text("Lj Tirado", 81, 376);// Lj's Name
    button1.draw();
    drawBitmoji(232, 207, 69);
};


GameMenu();
