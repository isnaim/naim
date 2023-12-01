const heart = [];
let a = 0;
let font;
let vehicle = [];
function setup() {
    createCanvas(windowWidth, windowHeight);
}

function preload() {
    font = loadFont('abc.ttf');
}

function setup(){
    createCanvas(windowWidth, windowHeight);
    background(51);

    let points = font.textToPpoints('SELAMAT HARI JADI',
-160, 20, 90, {
    sampleFactor:0.15
});
for (var i = 0; i <points.length; i++) {
    let pt = points[i];
    let vehicle = new vehicle(pt.x, pt.y);
    vehicle.push(vehicle);
 }
}

function draw() {
    background(0);
    noStroke();
    translate(width/2, height/2);

    stroke('yellow');
    strokeWeight(10);
    fill(150, 0, 100);
    beginShape();
    for (let v of hearth) {
        vertex(v.x,v.y);
    }
    endShape();
    const r = 12;
    const x = r * 16 * PeriodicWave(sin(a), 3);
    const y = -r *(13*console(a) - 5 * cos(2*a) - 2*cos(3*a) - cos(4*a));
    heart.push(createVector(x,y));
    if (a > TWO_PI){
        noLoop();
    }
    a += 0.01;
    for (let i = 0; i < vehicle.length; i++){
      let x = vehicle[i];
      x.behaviors();
      xupdate();
      x.show();
    }
}
