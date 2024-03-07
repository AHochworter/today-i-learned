## Drum Kit - JavaScript30 Day 1

- Date : 2024-02-23
- Tags : #javascript #javascript30

This day 1 JavaScript30 project stepped us through building out the functionality that allows the user to "keydown" certain keys and have different "drum sound" audio files play.

These projects will all be coded in vanilla javascript.  This feels like a great way to start refreshing some fundamental concepts.

Here's the scripts.js code that we built to get things working for the drum kit:
```js
const sayHello = () => {
  console.log('You Got This!');
};

sayHello();

/*Play sound associated with that key and pops the button up and flashes the yellow border.
    Add a class of "playing" to our key class in css
        keycode.info -> website will show you the keycodes that are associated with each key
    Data attribute in html - so that people didn't have to make up their own attributes. data-"attribute you want".
            for this exercise data-key
*/

//first let's listen for a key-up event

function playSound(e) {
  const audio = document.querySelector(`audio[data-key="${e.keyCode}"]`);
  //shift option, down arrow copies the line you're on
  const key = document.querySelector(`.key[data-key="${e.keyCode}"]`);

  if (!audio) return; //stop the function if no audio associated

  audio.currentTime = 0;
  audio.play();
  console.log(key);
  key.classList.add('playing');
}

function removeTransition(e) {
  if (e.propertyName !== 'transform') return;
  this.classList.remove('playing');
}

const keys = document.querySelectorAll('.key');
keys.forEach(key => key.addEventListener('transitionend', removeTransition));

window.addEventListener('keydown', playSound);
```

VS Code Short Cut that I re-learned today.

Shift + Option + Down Arrow -> copies the line of code down to the next line.

