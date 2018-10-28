# Udacity-Lesson-2-Quiz-Challenge-Question
My solution to the Udacity Lesson 2 Quiz Challenge. It decodes two messages encrypted with a one-time pad.

This is my solution to the Udacity Lesson 2 Quiz Cryptography Challenge. I took an interactive approach that does not require lots of computing power. The user interface works like this:

1. Select one of the encrypted messages, 1 or 2.

2. Make a guess at a word that might be in the message. Start with the most common word in the English language "the" but since three characters does not produce meaningful compares, expand your guess to five characters by adding spaces befor and after the word (" the "). Notice that we have done this for message 2.

3. The program XORs your guess with each character position (7 bits per character) through the entire message. This produces a key at each position which is XORed with the other message at the same position. The program presents a list possible words or partial words along with their character offset into the message. The program ignores any sequences that do not produce likely words (unprintable ASCII values, certain punctuation).

4. The user reads the list of possible word fragments and types the position number of a likely find. The program then prints both messages populating the guess in the target message as well as the text in the other message.

5. Notice that the word " the " in message 2 produced "state" in message 1. Now we use our proficiency in English to wonder whether "state" is a whole word in the message or whether it might be part of "estate" or "statement". We can select message 1 and try " state " (notice the spaces) and we see that we have likely valid text "r the m" at position 88. This is validation that "state" is indeed the whole word. If we had tried other word options and didn't like the result, we can type "u" at the prompt to undo our choice.

6. When we think about how the word "state" is used in the English language, it is usually combined with " a state of " or " the state of ". We try these and get more clues.

7. Proceed as above but try to guess common words that have at least six characters to get more meaningful clues. Put spaces before and after the guessed word but not if it's possible that the word could be the final word of a sentence followed by a period.

My code can be run from an Anaconda window with: jupyter notebook Lesson2Quiz.ipynb

The Challenge instructions were to assume that the messages are English and that character encoding is seven-bit ASCII. We also assume that the same one-time pad key was used to encode both messages -- something a wise cryptographer would avoid.
