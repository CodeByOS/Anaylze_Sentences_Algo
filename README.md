# AnalyzeSentence Algorithm

This repository contains the pseudocode for the `AnalyzeSentence` algorithm, which processes a sentence to determine its length, word count, and vowel count.

## Algorithm Overview

The `AnalyzeSentence` algorithm performs the following steps:

1. **Initialization**: Sets counters for sentence length, word count, and vowel count. Initializes a flag to track whether the current character is within a word and defines a string of vowel characters.

2. **Character Reading Loop**: Continuously reads characters from the input:
   - Increments the length counter for each character.
   - Checks if the character is a vowel and updates the vowel count accordingly.
   - Detects word boundaries to update the word count.
   - Terminates the loop upon encountering a period (`.`).

3. **Output**: Displays the total length of the sentence (excluding the terminating period), the number of words, and the number of vowels.

## Pseudocode

```plaintext
Algorithm AnalyzeSentence
    // Step 1: Initialize variables
    Variables:
        length ← 0              // Counter for the length of the sentence
        wordCount ← 0           // Counter for the number of words
        vowelCount ← 0          // Counter for the number of vowels
        inWord ← false          // Boolean flag to check if inside a word
        vowels ← "aeiouAEIOU"   // String containing all vowels
        
    // Step 2: Read each character of the sentence
    While true do
        Read character c
        
        // Increment the length counter
        length ← length + 1
        
        // Check for vowels
        If c is in vowels then
            vowelCount ← vowelCount + 1
        End If
        
        // Check for word boundaries
        If c ≠ " " AND c ≠ "." then
            If NOT inWord then
                wordCount ← wordCount + 1
                inWord ← true
            End If
        Else
            inWord ← false
        End If
        
        // Stop when the point is reached
        If c = "." then
            Break
        End If
    End While
    
    // Step 3: Output the results
    Output("Length of the sentence: " + (length - 1)) // Exclude the point
    Output("Number of words: " + wordCount)
    Output("Number of vowels: " + vowelCount)
End Algorithm
