#ifndef RECCHECK
// For debugging
#include <iostream>
// For std::remove
#include <algorithm> 
#include <map>
#include <set>
#endif

#include "wordle.h"
#include "dict-eng.h"
using namespace std;


// Add prototypes of helper functions here

void generateWords(const string& in, int index, string& current, string floating, map<char, int>& usedCount, set<string>& results, const set<string>& dict, int dashCount);

set<string> wordle(
    const string& in,
    const string& floating,
    const set<string>& dict)
{
    set<string> results;
    string current = in;
    map<char, int> usedCount;

    for (char c : floating) {
        usedCount[c]--;
    }

    int dashCount = count(in.begin(), in.end(), '-');
    generateWords(in, 0, current, floating, usedCount, results, dict, dashCount);
    return results;
}

// Define any helper functions here
void generateWords(const string& in, int index, string& current, string floating, map<char, int>& usedCount, set<string>& results, const set<string>& dict, int dashCount) {
    if (index == in.size()) {
        if (floating.empty()) {
            if (dict.find(current) != dict.end()) {
                results.insert(current);
            }
        }
        return;
    }

    if (in[index] == '-') {
        if (floating.size() == dashCount) {  
            for (size_t i = 0; i < floating.size(); i++) {
                current[index] = floating[i];
                string newFloating = floating;
                newFloating.erase(i, 1); 
                generateWords(in, index + 1, current, newFloating, usedCount, results, dict, dashCount - 1);
            }
        } 
        
        else { 
            for (char c = 'a'; c <= 'z'; c++) {
                current[index] = c;
                if (usedCount[c] < 0) {
                    string newFloating = floating;
                    size_t pos = newFloating.find(c);
                    if (pos != string::npos) newFloating.erase(pos, 1);
                    generateWords(in, index + 1, current, newFloating, usedCount, results, dict, dashCount - 1);
                } 
                
                else {
                    generateWords(in, index + 1, current, floating, usedCount, results, dict, dashCount - 1);
                }
            }
        }
        current[index] = '-';
    } 
    else {
        current[index] = in[index];
        generateWords(in, index + 1, current, floating, usedCount, results, dict, dashCount);
    }
}