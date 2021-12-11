# CodeChallenge
CodeChallenge for job application
#include <iostream>
#include <vector>
#include <ctime>

int main() {
    std::cout << "Welcome to Hangman!" << std::endl;
    //list of ten words : banana, grinch, Christmas, dog, gingerbread,snow, fire, chocolate, cougars, finals.
    std::string banana;
    std::string christmas;
    std::string grinch;
    std::string dog;
    std::string gingerbread;
    std::string snow;
    std::string fire;
    std::string chocolate;
    std::string cougars;
    std::string finals;
    std::vector <std::string> listOfWords;
    listOfWords.push_back(banana);
    listOfWords.push_back(christmas);
    listOfWords.push_back(grinch);
    listOfWords.push_back(dog);
    listOfWords.push_back(gingerbread);
    listOfWords.push_back(snow);
    listOfWords.push_back(fire);
    listOfWords.push_back(chocolate);
    listOfWords.push_back(cougars);
    listOfWords.push_back(finals);

    srand(time(0));
    int randomNum = rand() %10;
    std::string keyword;
    keyword = listOfWords.at(randomNum);
    int numGuesses =0;
    bool gameLength = false;

    while(!gameLength){
        std::cout << "The word has " << keyword.length() << " characters." << std::endl;
        std::cout << "Please guess a letter:" << std::endl;
        char userGuess;
        std::cin >> userGuess;
        numGuesses++;
        std::string newWord;
        newWord = keyword;
        bool guess;

        for(int j =0; j < newWord.length();j++){
            newWord.at(j)= '_';
        }

        for(int i =0; i < keyword.length(); i++){
            if(userGuess == keyword.at(i)){
                guess = true;
                if(guess == true){
                    newWord.at(i) == userGuess;
                    std::cout << newWord;
                }
            }
            else {

            }
        }
        if (newWord == keyword){
            gameLength = true;
        }

    }
    std::cout << "Would you like to try again or quit?" << std::endl;
    std::string userString;
    std::getline(std::cin, userString);
    if(userString == "try again" ){
        gameLength = false;
    }
    else {
        std::exit;
    }


    return 0;
}
