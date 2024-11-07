// Chloe Andrews

let bg;
let showText = true;
let showText2 = false;
let showText3 = false;
let showText4 = false;
let showText5 = false;
let startButton;
let gameStartButton;
let gameStartButton1;
let readyButton2;
let scoreButton;
let homeButton;
let PlayAgainButton;
let displaySymbolsWords = false;
let displaySingleWord = false;
let showSymbolPage = false;
let val = 0;
let i;
let imageList = [" "," "," "," "," "];
let firstSymbol, secondSymbol, thirdSymbol, fourthSymbol, fifthSymbol, sixSymbol;
// Word list of possible symbols
let wordList = ["pumpkin", "leaf", "cat", "apple", "bat", "owl", "moon", "pie", "acorn", "candy corn", "hedgehog", "turkey", "fox", "corn", "gnome"];
// make image buttons
let pumpButton, leaf, cat, apple, bat, owl, moon, pie, acorn, candy, headgehog, turkey, fox, corn, gnome;

let pumpButtonn, leafButton, catButton, appleButton, batButton, owlButton, moonButton, pieButton, acornButton, candyButton, headgehogButton, turkeyButton, foxButton, cornButton, gnomeButton;

function preload() {
  bg = loadImage('wood.jpg');
  pumpImage = loadImage('pump.png');
  leaf = loadImage('leaf.png');
  cat = loadImage('cat.png');
  apple = loadImage('apple.png');
  bat = loadImage('bat.png');
  owl = loadImage('owl.png');
  moon = loadImage('moon.png');
  pie = loadImage('pie.png');
  acorn = loadImage('acorn.png');
  candy = loadImage('candycorn.png');
  headgehog = loadImage('headgeHog.png');
  turkey = loadImage('turkey.png');
  fox = loadImage('fox.png');
  corn = loadImage('corn.png');
  gnome = loadImage('gnome.png');
  //mushroom = loadImage('mushroom.png') 
  //scarecrow = loadImage('scarecrow.png');
  //sunflower = loadImage('sunflower.png');
  //jackOLantern = loadImage('jackOLatern.png');
}

function setup() {
  createCanvas(600, 400);
  bg.resize(600, 400);

  //resize the images - 20 total
  pumpImage.resize(80, 80);
  leaf.resize(90, 90);
  cat.resize(90, 90);
  apple.resize(90, 90);
  bat.resize(90, 90);
  owl.resize(90, 90);
  moon.resize(80, 80);
  pie.resize(80, 80);
  acorn.resize(70, 70);
  candy.resize(80, 80);
  headgehog.resize(80, 80);
  turkey.resize(80, 80);
  fox.resize(90, 90);
  corn.resize(90, 90);
  gnome.resize(100, 100);
  //mushroom.resize(80, 80);
  //scarecrow.resize(80, 80);
  //sunflower.resize(80, 80);
  //jackOLanters.resize(80, 80);


  // image buttons 
  pumpButton = new Button(50, 10, pumpImage); // start of row 1
  leafButton = new Button(150, 10, leaf);
  catButton = new Button(260, 10, cat);
  appleButton = new Button(370, 10, apple);
  batButton = new Button(470, 10, bat);
  owlButton = new Button(50, 120, owl); // start of row 2
  moonButton = new Button(150, 120, moon);
  pieButton = new Button(260, 120, pie);
  acornButton = new Button(370, 120, acorn);
  candyCornButton = new Button(470, 120, candy);
  headgehogButton = new Button(50, 230, headgehog); // start of row 3
  turkeyButton = new Button(150, 230, turkey);
  foxButton = new Button(260, 230, fox);
  cornButton = new Button(370, 230, corn);
  gnomeButton = new Button(470, 230, gnome);

  //showing the buttons
  
  // Start button
  startButton = createButton("Begin");
  startButton.position(250, 200);
  startButton.size(150, 80);
  startButton.mousePressed(homePage);
  //noLoop();

  // Game start button
  gameStartButton = createButton("Hard");
  gameStartButton.position(340, 320);
  gameStartButton.size(80, 80);
  gameStartButton.mousePressed(gameStartPage);
  gameStartButton.hide();

  // Game start button new easy level
  gameStartButton1 = createButton("Easy");
  gameStartButton1.position(200, 320);
  gameStartButton1.size(80, 80);
  gameStartButton1.mousePressed(gameStartPage1)
  gameStartButton1.hide();

  // // Ready button
  // readyButton = createButton("Ready"); // is this going anywhere?
  // readyButton.position(280, 320);
  // readyButton.size(80, 80);
  // readyButton.mousePressed(handleReadyButton);
  // readyButton.hide();

  // Score Button
  /*scoreButton = createButton("Ready"); // what is this doing?
  scoreButton.position(280, 320);
  scoreButton.size(150, 80);
  scoreButton.mousePressed(gamePage1);
  scoreButton.hide();*/

  doneButton = createButton("Done");
  doneButton.position(250, 320);
  doneButton.size(150, 80);
  doneButton.mousePressed(compareMyArray); // to calculate score
  doneButton.mousePressed(finalPageWin);
  doneButton.hide();

  playAgainButton = createButton("Play Again")
  playAgainButton.position(280, 320);
  playAgainButton.size(150, 80);
  playAgainButton.mousePressed(homePage);
  playAgainButton.hide();

  homeButton = createButton("Home");
  homeButton.position(250, 320);
  homeButton.size(150, 80);
  homeButton.mousePressed(homePage);
  homeButton.hide();
  
}

function homePage() {
  console.log("instructions page");
  showSymbolPage = false;
  startButton.hide();
  showText = false;
  showText2 = true;
  showText3 = true;
  showText4 = false;
  showText5 = false;
  //loop();
  gameStartButton.show(); // show hard button
  gameStartButton1.show(); // show easy button

  playAgainButton.hide();
  homeButton.hide();
}

function gameStartPage1() {
  console.log("word list page easy");
  showSymbolPage = false;
  gameStartButton.hide();
  gameStartButton1.hide();
  showText = false;
  showText2 = false;
  showText3 = false;

  // Ready button
  readyButton2 = createButton("Ready");
  readyButton2.position(280, 320);
  readyButton2.size(80, 80);
  readyButton2.mousePressed(handleReadyButton);

  firstSymbol = random(wordList);

  displaySingleWord = true;

  //loop();
}

function gameStartPage() {
  console.log("word list page");
  //testing here true->false
  showSymbolPage = false;
  gameStartButton.hide();
  gameStartButton1.hide();
  showText = false;
  showText2 = false;
  showText3 = false;
  //readyButton.show();

  // Ready button
  readyButton2 = createButton("Ready");
  readyButton2.position(280, 320);
  readyButton2.size(80, 80);
  readyButton2.mousePressed(handleReadyButton);

  firstSymbol = random(wordList);

  secondSymbol = random(wordList);
  while (secondSymbol === firstSymbol) {
    secondSymbol = random(wordList);
  }

  thirdSymbol = random(wordList);
  while (thirdSymbol === firstSymbol || thirdSymbol === secondSymbol) {
    thirdSymbol = random(wordList);
  }

  fourthSymbol = random(wordList);
  while (fourthSymbol === firstSymbol || fourthSymbol === secondSymbol || fourthSymbol === thirdSymbol) {
    fourthSymbol = random(wordList);
  }

  fifthSymbol = random(wordList);
  while (fifthSymbol === firstSymbol || fifthSymbol === secondSymbol || fifthSymbol === thirdSymbol || fifthSymbol === fourthSymbol) {
    fifthSymbol = random(wordList);
  }

  displaySymbolsWords = true;

  //loop();
}

function draw() {
  background(bg);
  if (showSymbolPage) {   
   drawSymbols();
  }
  
  // pumpButton, leafButton, catButton, appleButton, batButton, owlButton, moonButton, pieButton, acornButton, candyButton, headgehogButton, turkeyButton, foxButton, cornButton, gnomeButton, deadTreesButton, mushroomButton, scarecrowButton, sunflowerButton, jackOLantersButton
  

  if (showText) {
    textSize(50);
    fill(255);
    text("Symbol Match", 150, 100);
    //console.log ("done 3")
  }

  if (showText2) {
      textSize(50);
      fill(255);
      text("Instructions", 180, 90);
  }
  
  if (showText3) {
      textSize(20);
      fill(255);
      text("Memorize the words in the list.", 180, 150);
      text("Press the button when you are ready to begin the", 80, 200);
      text("game. You will select which of the displayed", 105, 250);
      text("symbols represents the words that you saw.", 110, 300);
  }

  if (showText4) {
    textSize(80);
    fill(255);
    text("You Won!", 150, 200);
  }
  
  if (showText5) {
    textSize(50);
    fill(255);
    text("You Lost", 180, 90);
  }
    //console.log ("done 2")

  if (displaySymbolsWords) {
    textSize(50);
    fill(255);
    text("Symbols:", 200, 70);
    textSize(27);
    fill(255);
    text(firstSymbol, 260, 120);
    text(secondSymbol, 260, 160);
    text(thirdSymbol, 260, 200);
    text(fourthSymbol, 260, 240);
    text(fifthSymbol, 260, 290);
    //console.log ("done 4")
  }

  if (displaySingleWord) {
    textSize(50);
    fill(255);
    text("Symbols:", 200, 70);
    textSize(27);
    fill(255);
    text(firstSymbol, 260, 120);
  }

  //console.log ("end of draw")
  
}

function handleReadyButton(){
  console.log("clicked on ready button - shows images")
  showSymbolPage = true;
  showText3 = false;
  displaySymbolsWords = false;
  readyButton2.hide();
  doneButton.show();
  // symbols = false
}

function showScorePage() {
  console.log("score page")
  showSymbolPage = false;
}

function drawSymbols(){
    console.log("drawing symbols")
    pumpButton.display();
    leafButton.display();
    catButton.display();
    appleButton.display();
    batButton.display();
    owlButton.display();
    moonButton.display();
    pieButton.display();
    acornButton.display();
    candyCornButton.display();
    headgehogButton.display();
    turkeyButton.display();
    foxButton.display();
    cornButton.display();
    gnomeButton.display();
    //console.log ("done 1")

    displaySingleWord = false;
    displaySymbolsWords = false;

  //["pumpkin", "leaf", "cat", "apple", "bat", "owl", "moon", "pie", "acorn", "candy corn", "hedgehog", "turkey", "fox", "corn", "gnome"]
  // need to be able to click multiple times so the user can select different buttons

for (i = 0; i < 5; i++) {
    if (pumpButton.over() && mouseIsPressed){
      console.log("pressed on pumpkin")
      imageList[i] = "pumpkin";
      val+=1;
    }
    else if (leafButton.over() && mouseIsPressed){
    console.log("pressed on leaf")
      imageList[i] = "leaf";
      val+=1;
    }
    else if (catButton.over() && mouseIsPressed){
      console.log("pressed on cat")
      imageList[i] = "cat";
      val+=1;
    }
    else if (appleButton.over() && mouseIsPressed){
      console.log("pressed on apple")
      imageList[i] = "apple";
      val+=1;
    }
    else if (batButton.over() && mouseIsPressed) {
      console.log("pressed on bat")
      imageList[i] = "bat";
      val+=1;
    }
    else if (owlButton.over() && mouseIsPressed) {
      console.log("pressed on owl")
      imageList[i] = "owl";
      val+=1;
    }
    else if (moonButton.over() && mouseIsPressed) {
      console.log("pressed on moon")
      imageList[i] = "moon";
      val+=1;
    }
    else if (pieButton.over() && mouseIsPressed) {
      console.log("pressed on pie")
      imageList[i] = "pie";
      val+=1;
    }
    else if (acornButton.over() && mouseIsPressed) {
      console.log("pressed on acorn")
      imageList[i] = "acorn";
      val+=1;
    }
    else if (candyCornButton.over() && mouseIsPressed) {
      console.log("pressed on candy corn")
      imageList[i] = "candy corn";
      val+=1;
    }
    else if (headgehogButton.over() && mouseIsPressed) {
      console.log("pressed on headgehog")
      imageList[i] = "headgehog";
      val+=1;
    }
    else if (turkeyButton.over() && mouseIsPressed) {
      console.log("pressed on turkey")
      imageList[i] = "turkey";
      val+=1;
    }
    else if (foxButton.over() && mouseIsPressed) {
      console.log("pressed on fox")
      imageList[i] = "fox";
      val+=1;
    }
    else if (cornButton.over() && mouseIsPressed) {
      console.log("pressed on corn")
      imageList[i] = "corn";
      val+=1;
    }
    else if (gnomeButton.over() && mouseIsPressed) {
      console.log("Presseed on gnome")
      imageList[i] = "gnome";
      val+=1;
    }
  }

  if (val === 5) {
    console.log("going to next function to compare array")
    compareMyArray();
  }

}

function compareMyArray() {
  let i;
  let score = 0;
  
  
  for(i = 0; i < imageList.length; ++i) {
    if (imageList[i] === firstSymbol) {
      score++;
    }
    if (imageList[i] === secondSymbol) {
      score++;
    }
    if (imageList[i] === thirdSymbol) {
      score++;
    }
    if (imageList[i] === fourthSymbol) {
      score++;
    }
    if (imageList[i] === fifthSymbol) {
      score++;
    }
  }
  
  if (score === 5) {
    console.log("you win");
    finalPageWin();
  }
  else {
    finalPageLose();
  }
  //doneButton.mousePressed(finalPage);
}

function finalPageWin() {
  console.log("yay final pageWin");
  showSymbolPage = false;
  doneButton.hide();
  showText4 = true;
  homeButton.show();
}

function finalPageLose() {
  console.log("yay final pageLose");
  playAgainButton.show();
  showSymbolPage = false;
  doneButton.hide();
  showText5 = true;
  
}

// symbol pge
function symbolPage() {
  //draw symbols
  showSymbolPage = true;
 
  
  startButton.hide();
  gameStartButton.hide();
  gameStartButton1.hide();
  //readyButton.hide();
  showText = false;
  showText2 = false;
  showText3 = false;
  displaySymbolsWords = false;
  //loop();
  

  // Continue with symbol logic...
}

// function gamePage1() {
//   startButton.hide();
//   gameStartButton.hide();
//   gameStartButton1.hide();
//   //readyButton.hide();
//   showText = false;
//   showText2 = false;
//   showText3 = false;
//   displaySymbolsWords = false;
//   //scoreButton.show();
// }

class Button {  
  
  constructor(inX, inY, inImg) {
    this.x = inX;
    this.y = inY;
    this.img = inImg;
  }

  display() {
    stroke(0);
    image(this.img, this.x, this.y);
  }
  
  over() {
    if (mouseX > this.x && mouseX < this.x + this.img.width
        && mouseY >
        this.y && mouseY < this.y + this.img.height) {
      return true;
    } else {
      return false;
    }
  }
  hide(){
    this.alpha = 0;
  }
}
