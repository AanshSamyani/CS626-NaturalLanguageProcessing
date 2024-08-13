## Assignment 1 - Hidden Markov Model (HMM) based Part of Speech Tagging (POS - Tagging)
This is my imlementation for POS Tagging on Brown's Dataset using HMMs. The HMMs were solved by Viterbi's Algorithm. This implementation makes the following standard assumptions:
1) Bigram Assumption --> The probability of next tag is only dependent on the tag before that. Mathematically, P(t{i}|t{1},t{2},....t{i-1}) can be assumed to be almost equal to P(t{i}|t{i-1}). These probabilities are called transition probabilities (transition from 1 tag to the other)
   
2) Lexical Independence --> The probability that a word will appear given the prior tags of sequence, the probability can be found assuming the word depends only on the current tag. Mathematically, P(w{i}|t{1},t{2}...t{i}) can be assumed to be almost equal to P(w{i}|t{i}). These probabilities are called emission probabilities.
