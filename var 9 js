let mistakes = 0;
let checkLength = 0;
let str = [" "];
let wordAux = "";
let things = ['hanging', 'warrior', 'christmas', 'elephant', 'summer'];
let thing = things[Math.floor(Math.random() * things.length)];

function chooseWord() {
    thing = things[Math.floor(Math.random() * things.length)];
    for (let i = 0; i < thing.length; ++i) {
        wordAux += "*";
    }
    btn0.textContent = wordAux;
}

String.prototype.replaceAt = function(index, replacement) {
    if (index >= this.length)
        return this.valueOf();
    return this.substring(0, index) + replacement + this.substring(index + 1);
}

function pickLetter(clickedId) {
    let letter = "";
    letter += document.getElementById("searchTxt").value;
    if (letter.length == 1) {
        let aux = 0;
        for (let i = 0; i < str.length; ++i) {
            if (str[i] == letter[0])
                ++aux;
        }
        str += letter;
        if (aux == 0) {
            let guessLetter = 0;
            for (let i = 0; i <= wordAux.length - 1; ++i) {
                if (thing[i] == letter) {
                    wordAux = wordAux.replaceAt(i, letter);
                    btn0.textContent = wordAux;
                    ++guessLetter;
                }
            }
            if (guessLetter > 0) {
                checkLength += guessLetter;
            } else {
                ++mistakes;
                if (mistakes >= 6){
                    let display=document.getElementById("p");
                    display.textContent="Game Over!";
                } else {
                    let tries = 6 - mistakes;
                    let display=document.getElementById("p");
                    display.textContent="Mai ai " + tries + " vieti. Litera ,," + letter + "'' nu apare in cuvant.";
                }
            }
        }
    }
}
