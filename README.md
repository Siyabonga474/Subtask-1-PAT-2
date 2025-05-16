# Subtask-1-PAT-2
Subtask 1 PAT 2

#include <iostream>
#include <map>
#include <string>
#include <cctype>

using namespace std;

map<char, string> morseCodeMap = {
    {'A', ".-"},   {'B', "-..."}, {'C', "-.-."}, {'D', "-.."},  {'E', "."},
    {'F', "..-."}, {'G', "--."},  {'H', "...."}, {'I', ".."},   {'J', ".---"},
    {'K', "-.-"},  {'L', ".-.."}, {'M', "--"},   {'N', "-."},   {'O', "---"},
    {'P', ".--."}, {'Q', "--.-"}, {'R', ".-."},  {'S', "..."},  {'T', "-"},
    {'U', "..-"},  {'V', "...-"}, {'W', ".--"},  {'X', "-..-"}, {'Y', "-.--"},
    {'Z', "--.."},
    {'0', "-----"}, {'1', ".----"}, {'2', "..---"}, {'3', "...--"}, 
    {'4', "....-"}, {'5', "....."}, {'6', "-...."}, {'7', "--..."}, 
    {'8', "---.."}, {'9', "----."},
    {' ', "/"} // space between words
};

string toMorseCode(const string& text) {
    string morse = "";
    for (char ch : text) {
        ch = toupper(ch);
        if (morseCodeMap.find(ch) != morseCodeMap.end()) {
            morse += morseCodeMap[ch] + " ";
        }
    }
    return morse;
}

int main() {
    string input;
    cout << "Enter text to convert to Morse Code: ";
    getline(cin, input);

    string morse = toMorseCode(input);
    cout << "Morse Code: " << morse << endl;

    return 0;
}
