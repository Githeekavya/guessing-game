#include <iostream>
#include <cstdlib>  // For rand() and srand()
#include <ctime>    // For time()
using namespace std;

int main() {
    srand(time(0));  // Seed for random number generator

    int randomNumber = rand() % 100 + 1;  // Random number between 1 and 100
    int guess;
    int attempts = 0;

    cout << "Welcome to the Guessing Game!" << endl;
    cout << "I have selected a number between 1 and 100." << endl;

    // Game loop
    do {
        cout << "Enter your guess: ";
        cin >> guess;
        attempts++;

        if (guess > randomNumber) {
            cout << "Too high! Try again." << endl;
        } else if (guess < randomNumber) {
            cout << "Too low! Try again." << endl;
        } else {
            cout << "Congratulations! You guessed the correct number." << endl;
            cout << "It took you " << attempts << " attempts." << endl;
        }
    } while (guess != randomNumber);

    return 0;
}
