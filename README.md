#include <stdio.h>
#include <stdlib.h>
#include <time.h>

void numberGuessingGame() {
    int lower, upper, guess, secretNumber, attempts = 0;

    // Seed the random number generator
    srand(time(0));

    printf("Welcome to the Number Guessing Game!\n");
    printf("Enter the lower limit of the range: ");
    scanf("%d", &lower);
    printf("Enter the upper limit of the range: ");
    scanf("%d", &upper);

    // Generate a random number within the range
    secretNumber = (rand() % (upper - lower + 1)) + lower;

    printf("Guess the number between %d and %d.\n", lower, upper);

    while (1) {
        printf("Enter your guess: ");
        scanf("%d", &guess);
        attempts++;

        if (guess < lower || guess > upper) {
            printf("Please guess a number within the range %d to %d.\n", lower, upper);
        } else if (guess < secretNumber) {
            printf("Too low! Try again.\n");
        } else if (guess > secretNumber) {
            printf("Too high! Try again.\n");
        } else {
            printf("Congratulations! You guessed the number %d in %d attempts.\n", secretNumber, attempts);
            break;
        }
    }
}

int main() {
    numberGuessingGame();
    return 0;
}
