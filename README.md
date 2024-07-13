# RockPaperScissorsGame
const game = () => {
  let computerScore = 0;
  let playerScore = 0;

  const playRound = (playerChoice) => {
      const choices = ["rock", "paper", "scissors"];
      const computerChoice = choices[Math.floor(Math.random() * choices.length)];

      let result;
      if (playerChoice === computerChoice) {
          result = "It's a tie!";
      } else if (
          (playerChoice === "rock" && computerChoice === "scissors") ||
          (playerChoice === "paper" && computerChoice === "rock") ||
          (playerChoice === "scissors" && computerChoice === "paper")
      ) {
          result = "You win!";
          playerScore++;
      } else {
          result = "You lose!";
          computerScore++;
      }

      console.log("Player choice:", playerChoice);
      console.log("Computer choice:", computerChoice);
      console.log(result);
      console.log("Computer score:", computerScore);
      console.log("Player score:", playerScore);
  };

  return { playRound };
};

// Example usage:
const myGame = game();
myGame.playRound("paper");
