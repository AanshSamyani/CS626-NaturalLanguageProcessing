
## Assignment 1 - Hidden Markov Model (HMM) based Part of Speech Tagging (POS - Tagging)
This is my imlementation for POS Tagging on Brown's Dataset using HMMs. The above implementation makes use of the **'universal_tagset'** for POS tagging. The HMMs were solved by Viterbi's Algorithm. POS Tagging is a basic Sequence to Sequence Mapping NLP Technique. A couple of examples of POS Tagging are:
1) Input --> "Reading is an essential skill."
   Output --> "Reading" - "NN" (Noun)
              "is" - "BEZ" (Auxilary Verb)
              "an" - "AT" (Article)
              "essential" - "JJ" (Adjective)
              "skill" - "NN" (Noun)

2) Input --> "The grand jury said."
   Output --> "The" - "AT" (Article)
              "grand" - "JJ" (Adjective)
              "jury" - "NN" (Noun)
              "said" - "VBD" (Verb - Past Tense)   

This implementation makes the following standard assumptions:
1) Bigram Assumption --> The probability of next tag is only dependent on the tag before that. Mathematically, P(t{i}|t{1},t{2},....t{i-1}) can be assumed to be almost equal to P(t{i}|t{i-1}). These probabilities are called transition probabilities (transition from 1 tag to the other)
   
2) Lexical Independence --> The probability that a word will appear given the prior tags of sequence, the probability can be found assuming the word depends only on the current tag. Mathematically, P(w{i}|t{1},t{2}...t{i}) can be assumed to be almost equal to P(w{i}|t{i}). These probabilities are called emission probabilities.

**Implementation Details:**
1) Used NLTK for tokenization and accessing the Brown Dataset for (POS Tagging).
2) Processed the dataset to convert everything to lowercase (For POS Tagging, "The" and "the" are considered the same (both are articles))
3) The dictionary 'probability_tags_bigram' contains the **transition probabilities** (P(t{i}|t{i-1}).
4) The dictionary 'emission_probabilities_dict' contains the **emission probabilites** (P(w{i}|t{i}).
5) The algorithm used to compute the best/optimal sequence of tags is the Viterbi Algorithm. The Viterbi Algorithm is based on Markov Assunmptions and is a Dynamic Programming based algorithm that helps us reduce our search space. Given there are S tags and L words in the input sequence, the initial search space is $S^{L}$ which can be reduced to $S^{2}L$ using the Viterbi's Algorithm.


**Visualization of Viterbi's Algorithm:**


![Viterbi](https://github.com/user-attachments/assets/10752843-54a3-43e5-a022-9370b63fc9d1)



**Training and Evaluation:** The HMM was trained on the Brown dataset corpus, the evaluation involved a 5-fold cross validation. The training resulted in an average accuracy of **0.738** per fold. The confusion matrix after 5 folds of validation looks like this:

<div align="center">
   <img width="800" alt="Screenshot 2024-08-17 194620" src="https://github.com/user-attachments/assets/8249be93-a95a-45f1-ac80-b52d94bcbecf">
</div>


**Problems faced in HMM based POS Tagging:**
All problems are due to **SPARSITY**. Kinds of Sparsity:
1) Unseen words ('delay' in training corpus but not 'procrastination' - even though both the words have more or less the same meaning the later is not recognized)
2) Different form of the word is used (Word Morphology Problem - corpus has 'predictable' but not 'unpredictable')
3) Language Code Mixing ('aap mujhe advice dedo please' - 'Please give me advice') (Hindi + English mixing)
4) Corpus doesn't have a particular word-tag combination (Example - 'people' as verb)



