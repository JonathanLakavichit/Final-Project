var Gameover = 0; 
var temp = 0;
var score = 0;
var Beaver = function(x, y) {
    this.x = x;
    this.y = y;
    this.img = getImage("space/rocketship");
    this.sticks = 0;
};

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
                    
Gameover = 1;}
     
    else if (!stick.isTop &&  this.y >stick.height+100-(stick.height/2)){
           
Gameover =2;}

}
    
};

draw = function() {
    // static
    if (Gameover === 0){
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
    beaver.draw();}
    if(Gameover===1){
        background(0, 0, 0);
        fill(0, 0, 0);
        text("1",200,200);
    }
    if(Gameover===2){
        background(255, 0, 0);
        fill(0, 0, 0);
        textSize(40);
        text(" Game Over :(",100,105);
        text("Final Score:",100,205);
        text("2",210,250);
    }
};
