# Rock/Paper/Scissors

let gameOver = false;
let computerChoices = ["scissors", "rock", "paper"];

function randomFrom(array) {
  return array[(Math.floor(Math.random()*2))];
}

function checkInput(input, computerChoices) {
  if (input === "quit".toLowerCase()) {
    return true;
  } else if (input != "quit"){
    console.log("Please enter type")
  }
  
  let computerChoice = randomFrom(computerChoices);
  console.log("Computer's choice", computerChoice);
  console.log("Player's choice", input);

  if (computerChoice === "rock" && input === "scissors".toLowerCase()){
    alert("Computer wins!");
    return false;
  } else if (computerChoice === "scissors" && input === "paper".toLowerCase()){
    alert("Computer wins!");
    return false;
  } else if (computerChoice === "paper" && input === "rock".toLowerCase()){
    alert("Computer wins!");
    return false;
  } else if(!computerChoices.includes(input)) {
    alert('Wrong input')
    return false;
  } else if(computerChoice === input){
    alert('Tied game')
  } else {
  alert("Player wins");
  return false;
  }
}

function start(gameOver, computerChoices) {
  while (!gameOver){
    let playerInput = prompt("Hi! Enter rock/paper/scissors to play, or quit to stop playing.");
    playerInput = playerInput.toLowerCase();
    gameOver = checkInput(playerInput, computerChoices);
  } 
  return "Game ended by the user" // Line added by Joan
}



start(gameOver, computerChoices)  


# Decode/Encode


function encode(word) {
  //somewhere to setore the converted caracters
  let result = [];
  //next we loop over each character in the string.
for(let position in word){
  //and save the charcode to the array
  result.push(word.charCodeAt(position));
}
// and return that list of codes, separated by colons
return result.join(':');
}

function decode(hash) {
  //split the code by semicolons!
let arr = hash.split(':');
// again somewhere to put our codes
let result = [];
//loop over the codes
for(let code of arr){
  //change the ode back to the string character equivalent
  result.push(String.fromCharCode(code));
  }
  return result.join('');
}


let message = "I'm trying to send this secret message.";
let encodedMessage = encode('My Name is Jeff');
let decodedMessage = decode(encodedMessage);


console.log(message);
console.log(encodedMessage);
console.log(decodedMessage);

