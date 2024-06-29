# random-number-guessing-game
#include <iostream>
#include <cstdlib> // For random number generation
#include <ctime>   // For seeding the random number generator

using namespace std;

int main() {
    // Seed the random number generator
    srand(time(0));

    // Generate a random number between 1 and 100
    int secretNumber = rand() % 100 + 1;

    int userGuess;
    int attempts = 0;

    cout << "Welcome to the Number Guessing Game!\n";
    cout << "I've picked a number between 1 and 100. Try to guess it.\n";

    do {
        cout << "Enter your guess: ";
        cin >> userGuess;
        attempts++;

        if (userGuess < secretNumber) {
            cout << "Too low! Try a higher number.\n";
        } else if (userGuess > secretNumber) {
            cout << "Too high! Try a lower number.\n";
        } else {
            cout << "Congratulations! You guessed the correct number (" << secretNumber << ") in " << attempts << " attempts.\n";
        }
    } while (userGuess != secretNumber);

    return 0;
}
