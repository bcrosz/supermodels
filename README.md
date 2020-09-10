# Working with Git

Practice working with Git.

## Description

Except for opening the Git Bash shell program, all following steps assume that you will be using command line,

Peform the following steps using appropriate commands.

You will add command lines, using [GitHub Flavored Markdown (GFM)](https://guides.github.com/features/mastering-markdown/) for each step in this file to the corresponding step in [commands.md](commands.md).

Example code is from <https://github.com/mdn/learning-area/tree/master/javascript/introduction-to-js-1/first-splash>

## Task

When you

- complete each step in this README file
- add command line for the step in the file [commands.md](commands.md)

You will then make a commit.

Command lines for step 1-7 are already provided for you.

## Steps

1. Open Git Bash shell.

   `No command line`

2. Change into the directory that you have clone this repo to, e.g. /d/working/A01

   ```bash
   cd /d/working/A01
   ```

3. Config your name and email **locally** for this repo. Replace `xxxxxxxxxx` with your Student ID.

   ```bash
   git config --local user.name "your_name your_surname"
   git config --local user.email "xxxxxxxxxx@cn330"
   ```

4. Edit the `AUTHORS` file.

   - Add your information in appropriate section.
   - Add the following information under your team name:

     - your name and surname
     - your (mock-up) email address, use format: <xxxxxxxxxx@cn330>

   ```bash
   code AUTHORS
   ```

   or

   ```bash
   nano AUTHORS
   ```

   or

   ```bash
   vim AUTHORS
   ```

5. Add and commit `AUTHORS` to repo.

   ```bash
   git add AUTHORS
   git commit -m "complete step 5"
   ```

6. Create an emtpty file named `index.html`.

   ```bash
   touch index.html
   ```

   Or create the file using your editor (don't forget to save the file).

   ```bash
   code index.html
   ```

7. Check worktree status, add file(s) and commit to repo.

   ```bash
   git status
   git add index.html
   git commit -m "Complete step 7"
   ```

8. Edit `index.html` so it has the following connent:

   ```html
   <!DOCTYPE html>
   <html lang="en">
     <head>
       <meta charset="UTF-8" />
       <meta name="viewport" content="width=device-width, initial-scale=1.0" />
       <title>Document</title>
     </head>
     <body></body>
   </html>
   ```

   - Add the command lines to the file `commands.md`.
   - Check worktree status.
   - Add file(s).
   - Commit to repo.

   ```bash
   code index.html
   code commands.md
   git status
   git add index.html commands.md
   git commit -m "complete step 8"
   ```

9. Modify `index.html` to add `<script>` tag between the `<body>` tag

   ```html
   <!DOCTYPE html>
   <html lang="en">
     <head>
       <meta charset="UTF-8" />
       <meta name="viewport" content="width=device-width, initial-scale=1.0" />
       <title>Document</title>
     </head>
     <body>
       <script></script>
     </body>
   </html>
   ```

   - Add the command lines to the file `commands.md`.
   - Check worktree status.
   - See the difference between worktree and staging area.
   - Add file(s).
   - Commit to repo.

   ```bash
   code index.html
   code commands.md
   git diff
   git status
   git add index.html commands.md
   git commit -m "complete step 9"
   ```

10. Create a new file named `topics.md` with the following contents

    ```markdown
    # Basic JavaScript

    Recommended place to start is on [Mozilla Developer Network (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

    - Case sensitivity
    - Semicolons

    ## Comments

    ## Variables

    - declaration
    - initialisation
    - assignment
    - uninitialised variables

    ## Data Types

    - Primitive types
    - Objects

    ## Some Native Objects

    - Array
    - Date
    - Error
    - Math
    - Regular Expression
    - Function
    - String
    - ...

    ## Operators

    - Arithmetic
      - binary
      - unary
    - Relational
    - Logical
    - Bitwise
    - Assignment
    - Spread/Rest

    ## Statements

    - _expression_
    - if, if-else
    - switch
    - for, for ... in ...
    - while
    - do-while
    - continue
    - break
    - labels
    - return
    - try/throw

    ## Functions

    - declaration
    - return
    - scope
    - hoisting

    ## Objects

    - constructor
    - method
    - inheritance
    ```

    - Add the command lines to the file `commands.md`.
    - Check worktree status.
    - Add file(s).
    - Commit to repo.

11. Create empty file `script.js` and `stype.css`.

    - Add the command lines to the file `commands.md`.
    - Check worktree status.
    - Add file(s).
    - Commit to repo.

12. Modify the `head` element, replacing the `title` element in `index.html` with

    ```html
    <title>Number guessing game</title>

    <style>
      html {
        font-family: sans-serif;
      }

      body {
        width: 50%;
        max-width: 800px;
        min-width: 480px;
        margin: 0 auto;
      }

      .lastResult {
        color: white;
        padding: 3px;
      }
    </style>
    ```

    - Add the command lines to the file `commands.md`.
    - Check worktree status.
    - Add file(s).
    - Commit to repo.

13. Modify the `body` element in `index.html` to become

    ```html
    <body>
      <h1>Number guessing game</h1>
      <p>
        We have selected a random number between 1 and 100. See if you can guess
        it in 10 turns or fewer. We'll tell you if your guess was too high or
        too low.
      </p>

      <div class="form">
        <label for="guessField">Enter a guess: </label
        ><input type="text" id="guessField" class="guessField" />
        <input type="submit" value="Submit guess" class="guessSubmit" />
      </div>

      <div class="resultParas">
        <p class="guesses"></p>
        <p class="lastResult"></p>
        <p class="lowOrHi"></p>
      </div>

      <script></script>
    </body>
    ```

    - Add the command lines to the file `commands.md`.
    - Check worktree status.
    - Add file(s).
    - Commit to repo.

14. Modify the `script` element in `index.html` to become

    ```html
    <script>
      let randomNumber = Math.floor(Math.random() * 100) + 1;
      const guesses = document.querySelector(".guesses");
      const lastResult = document.querySelector(".lastResult");
      const lowOrHi = document.querySelector(".lowOrHi");
      const guessSubmit = document.querySelector(".guessSubmit");
      const guessField = document.querySelector(".guessField");
      let guessCount = 1;
      let resetButton;

      function checkGuess() {
        let userGuess = Number(guessField.value);
        if (guessCount === 1) {
          guesses.textContent = "Previous guesses: ";
        }

        guesses.textContent += userGuess + " ";

        if (userGuess === randomNumber) {
          lastResult.textContent = "Congratulations! You got it right!";
          lastResult.style.backgroundColor = "green";
          lowOrHi.textContent = "";
          setGameOver();
        } else if (guessCount === 10) {
          lastResult.textContent = "!!!GAME OVER!!!";
          lowOrHi.textContent = "";
          setGameOver();
        } else {
          lastResult.textContent = "Wrong!";
          lastResult.style.backgroundColor = "red";
          if (userGuess < randomNumber) {
            lowOrHi.textContent = "Last guess was too low!";
          } else if (userGuess > randomNumber) {
            lowOrHi.textContent = "Last guess was too high!";
          }
        }

        guessCount++;
        guessField.value = "";
        guessField.focus();
      }

      guessSubmit.addEventListener("click", checkGuess);

      function setGameOver() {
        guessField.disabled = true;
        guessSubmit.disabled = true;
        resetButton = document.createElement("button");
        resetButton.textContent = "Start new game";
        document.body.appendChild(resetButton);
        resetButton.addEventListener("click", resetGame);
      }

      function resetGame() {
        guessCount = 1;
        const resetParas = document.querySelectorAll(".resultParas p");
        for (let i = 0; i < resetParas.length; i++) {
          resetParas[i].textContent = "";
        }

        resetButton.parentNode.removeChild(resetButton);
        guessField.disabled = false;
        guessSubmit.disabled = false;
        guessField.value = "";
        guessField.focus();
        lastResult.style.backgroundColor = "white";
        randomNumber = Math.floor(Math.random() * 100) + 1;
      }
    </script>
    ```

    - Add the command lines to the file `commands.md`.
    - Check worktree status.
    - Add file(s).
    - Commit to repo.

15. Modify the `head` element in `index.html`, by moving the text of the `style` element into `style.css`, and add a `link` element to `index.html`

    The `head` element in `index.html` should become

    ```html
    <head>
      <meta charset="UTF-8" />
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
      <link href="./style.css" rel="stylesheet" type="text/css" />
      <title>Number guessing game</title>
    </head>
    ```

    The file `style.css` should become

    ```css
    html {
      font-family: sans-serif;
    }
    body {
      width: 50%;
      max-width: 800px;
      min-width: 480px;
      margin: 0 auto;
    }
    .lastResult {
      color: white;
      padding: 3px;
    }
    ```

    - Add the command lines to the file `commands.md`.
    - Check worktree status.
    - Add file(s).
    - Commit to repo.

16. Modify the `script` element in `index.html`, by moving its text into `script.js`, and add a `src` attribute to the `script` tag in `index.html`

    The `script` element in `index.html` should become

    ```html
    <script defer src="./script.js"></script>
    ```

    The file `script.js` should become

    ```js
    let randomNumber = Math.floor(Math.random() * 100) + 1;
    const guesses = document.querySelector(".guesses");
    const lastResult = document.querySelector(".lastResult");
    const lowOrHi = document.querySelector(".lowOrHi");
    const guessSubmit = document.querySelector(".guessSubmit");
    const guessField = document.querySelector(".guessField");
    let guessCount = 1;
    let resetButton;

    function checkGuess() {
      let userGuess = Number(guessField.value);
      if (guessCount === 1) {
        guesses.textContent = "Previous guesses: ";
      }

      guesses.textContent += userGuess + " ";

      if (userGuess === randomNumber) {
        lastResult.textContent = "Congratulations! You got it right!";
        lastResult.style.backgroundColor = "green";
        lowOrHi.textContent = "";
        setGameOver();
      } else if (guessCount === 10) {
        lastResult.textContent = "!!!GAME OVER!!!";
        lowOrHi.textContent = "";
        setGameOver();
      } else {
        lastResult.textContent = "Wrong!";
        lastResult.style.backgroundColor = "red";
        if (userGuess < randomNumber) {
          lowOrHi.textContent = "Last guess was too low!";
        } else if (userGuess > randomNumber) {
          lowOrHi.textContent = "Last guess was too high!";
        }
      }

      guessCount++;
      guessField.value = "";
      guessField.focus();
    }

    guessSubmit.addEventListener("click", checkGuess);

    function setGameOver() {
      guessField.disabled = true;
      guessSubmit.disabled = true;
      resetButton = document.createElement("button");
      resetButton.textContent = "Start new game";
      document.body.appendChild(resetButton);
      resetButton.addEventListener("click", resetGame);
    }

    function resetGame() {
      guessCount = 1;
      const resetParas = document.querySelectorAll(".resultParas p");
      for (let i = 0; i < resetParas.length; i++) {
        resetParas[i].textContent = "";
      }

      resetButton.parentNode.removeChild(resetButton);
      guessField.disabled = false;
      guessSubmit.disabled = false;
      guessField.value = "";
      guessField.focus();
      lastResult.style.backgroundColor = "white";
      randomNumber = Math.floor(Math.random() * 100) + 1;
    }
    ```

    - Add the command lines to the file `commands.md`.
    - Check worktree status.
    - Add file(s).
    - Commit to repo.
