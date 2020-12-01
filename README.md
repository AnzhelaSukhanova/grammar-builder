# Grammar_builder by Sukhanova and Afonina
Program constructing a free grammar and a context sensitive grammar from Тuring machine. Grammars generate a language of correct mathematical expressions for a multiplication in an unary number system.
____
To check if grammars generate a word, ***use*** `python src/main.py`.  
After that you can enter the word and if the grammars generate it, you will see an output of this word from the start nonterminal. If the word is not generated by the grammars, you will receive messages about it. Note that the output for free grammar contains the boundary characters (**#** and **$**) but you do not need to type them.  
You can continue checking or ***enter*** `:q` ***to stop the program***.

## Input format
Input symbols: 1, \*, =.  
Word's examples: 1\*1=1, 1\*=, 111\*11=111111, 1\*1111=1111, \*1=, etc.

## Output examples
**1*1=1**

Free grammar generation:

 S -> Q0 S1 -> Q0 N1 S1 -> Q0 N1 N3 S1 -> Q0 N1 N3 N4 S1 -> Q0 N1 N3 N4 N3 S1 -> Q0 N1 N3 N4 N3 N5 S1 -> Q0 N1 N3 N4 N3 N5 N3 S1 -> Q0 N1 N3 N4 N3 N5 N3 N2 S1 -> Q0 N1 N3 N4 N3 N5 N3 N2 S2 -> Q0 N1 N3 N4 N3 N5 N3 N2 N S2 -> Q0 N1 N3 N4 N3 N5 N3 N2 N -> N1 Q0 N3 N4 N3 N5 N3 N2 N -> N1 N3 Q0 N4 N3 N5 N3 N2 N -> N1 N3 N4 Q1 N3 N5 N3 N2 N -> N1 N3 N4 N30 Q2 N5 N3 N2 N -> N1 N3 N4 Q2 N30 N5 N3 N2 N -> N1 N3 Q2 N4 N30 N5 N3 N2 N -> N1 Q3 N3 N4 N30 N5 N3 N2 N -> N1 N30 Q4 N4 N30 N5 N3 N2 N -> N1 N30 N4 Q4 N30 N5 N3 N2 N -> N1 N30 N4 N30 Q4 N5 N3 N2 N -> N1 N30 N4 N30 N5 Q5 N3 N2 N -> N1 N30 N4 N30 Q2 N5 N30 N2 N -> N1 N30 N4 Q2 N30 N5 N30 N2 N -> N1 N30 Q2 N4 N30 N5 N30 N2 N -> N1 Q3 N30 N4 N30 N5 N30 N2 N -> Q3 N1 N30 N4 N30 N5 N30 N2 N -> N1 Q6 N30 N4 N30 N5 N30 N2 N -> N1 N3 Q6 N4 N30 N5 N30 N2 N -> N1 N3 N4 Q7 N30 N5 N30 N2 N -> N1 N3 N4 N30 Q7 N5 N30 N2 N -> N1 N3 N4 Q8 N30 N5 N30 N2 N -> N1 N3 Q8 N4 N3 N5 N30 N2 N -> N1 N3 N4 Q9 N3 N5 N30 N2 N -> N1 N3 N4 N3 Q9 N5 N30 N2 N -> N1 N3 N4 N3 N5 Q10 N30 N2 N -> N1 N3 N4 N3 N5 N3 Q10 N2 N -> N1 N3 N4 N3 N5 N3 N2 Q11 N -> N1 N3 N4 N3 N5 N3 N2 Q11 Q11 -> N1 N3 N4 N3 N5 N3 Q11 $ Q11 Q11 -> N1 N3 N4 N3 N5 Q11 1 Q11 $ Q11 Q11 -> N1 N3 N4 N3 Q11 = Q11 1 Q11 $ Q11 Q11 -> N1 N3 N4 Q11 1 Q11 = Q11 1 Q11 $ Q11 Q11 -> N1 N3 Q11 * Q11 1 Q11 = Q11 1 Q11 $ Q11 Q11 -> N1 Q11 1 Q11 * Q11 1 Q11 = Q11 1 Q11 $ Q11 Q11 -> Q11 # Q11 1 Q11 * Q11 1 Q11 = Q11 1 Q11 $ Q11 Q11 -> # Q11 1 Q11 * Q11 1 Q11 = Q11 1 Q11 $ Q11 Q11 -> # 1 Q11 * Q11 1 Q11 = Q11 1 Q11 $ Q11 Q11 -> # 1 * Q11 1 Q11 = Q11 1 Q11 $ Q11 Q11 -> # 1 * 1 Q11 = Q11 1 Q11 $ Q11 Q11 -> # 1 * 1 = Q11 1 Q11 $ Q11 Q11 -> # 1 * 1 = 1 Q11 $ Q11 Q11 -> # 1 * 1 = 1 $ Q11 Q11 -> # 1 * 1 = 1 $ Q11 -> # 1 * 1 = 1 $

Context-sensitive grammar generation:

 S -> S12 S1 -> S12 S5 S1 -> S12 S5 S13 S1 -> S12 S5 S13 S9 S1 -> S12 S5 S13 S9 S14 -> S824 S5 S13 S9 S14 -> S177 S435 S13 S9 S14 -> S177 S5 S556 S9 S14 -> S177 S5 S168 S110 S14 -> S177 S5 S169 S9 S14 -> S177 S48 S168 S9 S14 -> S344 S5 S168 S9 S14 -> S170 S259 S168 S9 S14 -> S170 S5 S349 S9 S14 -> S170 S5 S168 S307 S14 -> S170 S5 S168 S9 S203 -> S170 S5 S168 S110 S186 -> S170 S5 S169 S9 S186 -> S170 S48 S168 S9 S186 -> S340 S5 S168 S9 S186 -> S768 S5 S168 S9 S186 -> S769 S5 S168 S9 S186 -> S177 S291 S168 S9 S186 -> S177 S5 S359 S9 S186 -> S177 S5 S168 S317 S186 -> S177 S5 S208 S9 S186 -> S177 S108 S13 S9 S186 -> S177 S5 S502 S9 S186 -> S177 S5 S13 S471 S186 -> S177 S5 S13 S9 S187 -> S177 S5 S13 S9 S791 -> S177 S5 S13 S9 S821 -> S177 S5 S13 S9 1 -> S177 S5 S13 = 1 -> S177 S5 1 = 1 -> S177 * 1 = 1 -> 1 * 1 = 1
 
 
**11*1=11**

Free grammar generation:

 S -> Q0 S1 -> Q0 N1 S1 -> Q0 N1 N3 S1 -> Q0 N1 N3 N3 S1 -> Q0 N1 N3 N3 N4 S1 -> Q0 N1 N3 N3 N4 N3 S1 -> Q0 N1 N3 N3 N4 N3 N5 S1 -> Q0 N1 N3 N3 N4 N3 N5 N3 S1 -> Q0 N1 N3 N3 N4 N3 N5 N3 N3 S1 -> Q0 N1 N3 N3 N4 N3 N5 N3 N3 N2 S1 -> Q0 N1 N3 N3 N4 N3 N5 N3 N3 N2 S2 -> Q0 N1 N3 N3 N4 N3 N5 N3 N3 N2 N S2 -> Q0 N1 N3 N3 N4 N3 N5 N3 N3 N2 N -> N1 Q0 N3 N3 N4 N3 N5 N3 N3 N2 N -> N1 N3 Q0 N3 N4 N3 N5 N3 N3 N2 N -> N1 N3 N3 Q0 N4 N3 N5 N3 N3 N2 N -> N1 N3 N3 N4 Q1 N3 N5 N3 N3 N2 N -> N1 N3 N3 N4 N30 Q2 N5 N3 N3 N2 N -> N1 N3 N3 N4 Q2 N30 N5 N3 N3 N2 N -> N1 N3 N3 Q2 N4 N30 N5 N3 N3 N2 N -> N1 N3 Q3 N3 N4 N30 N5 N3 N3 N2 N -> N1 N3 N30 Q4 N4 N30 N5 N3 N3 N2 N -> N1 N3 N30 N4 Q4 N30 N5 N3 N3 N2 N -> N1 N3 N30 N4 N30 Q4 N5 N3 N3 N2 N -> N1 N3 N30 N4 N30 N5 Q5 N3 N3 N2 N -> N1 N3 N30 N4 N30 Q2 N5 N30 N3 N2 N -> N1 N3 N30 N4 Q2 N30 N5 N30 N3 N2 N -> N1 N3 N30 Q2 N4 N30 N5 N30 N3 N2 N -> N1 N3 Q3 N30 N4 N30 N5 N30 N3 N2 N -> N1 Q3 N3 N30 N4 N30 N5 N30 N3 N2 N -> N1 N30 Q4 N30 N4 N30 N5 N30 N3 N2 N -> N1 N30 N30 Q4 N4 N30 N5 N30 N3 N2 N -> N1 N30 N30 N4 Q4 N30 N5 N30 N3 N2 N -> N1 N30 N30 N4 N30 Q4 N5 N30 N3 N2 N -> N1 N30 N30 N4 N30 N5 Q5 N30 N3 N2 N -> N1 N30 N30 N4 N30 N5 N30 Q5 N3 N2 N -> N1 N30 N30 N4 N30 N5 Q2 N30 N30 N2 N -> N1 N30 N30 N4 N30 Q2 N5 N30 N30 N2 N -> N1 N30 N30 N4 Q2 N30 N5 N30 N30 N2 N -> N1 N30 N30 Q2 N4 N30 N5 N30 N30 N2 N -> N1 N30 Q3 N30 N4 N30 N5 N30 N30 N2 N -> N1 Q3 N30 N30 N4 N30 N5 N30 N30 N2 N -> Q3 N1 N30 N30 N4 N30 N5 N30 N30 N2 N -> N1 Q6 N30 N30 N4 N30 N5 N30 N30 N2 N -> N1 N3 Q6 N30 N4 N30 N5 N30 N30 N2 N -> N1 N3 N3 Q6 N4 N30 N5 N30 N30 N2 N -> N1 N3 N3 N4 Q7 N30 N5 N30 N30 N2 N -> N1 N3 N3 N4 N30 Q7 N5 N30 N30 N2 N -> N1 N3 N3 N4 Q8 N30 N5 N30 N30 N2 N -> N1 N3 N3 Q8 N4 N3 N5 N30 N30 N2 N -> N1 N3 N3 N4 Q9 N3 N5 N30 N30 N2 N -> N1 N3 N3 N4 N3 Q9 N5 N30 N30 N2 N -> N1 N3 N3 N4 N3 N5 Q10 N30 N30 N2 N -> N1 N3 N3 N4 N3 N5 N3 Q10 N30 N2 N -> N1 N3 N3 N4 N3 N5 N3 N3 Q10 N2 N -> N1 N3 N3 N4 N3 N5 N3 N3 N2 Q11 N -> N1 N3 N3 N4 N3 N5 N3 N3 N2 Q11 Q11 -> N1 N3 N3 N4 N3 N5 N3 N3 Q11 $ Q11 Q11 -> N1 N3 N3 N4 N3 N5 N3 Q11 1 Q11 $ Q11 Q11 -> N1 N3 N3 N4 N3 N5 Q11 1 Q11 1 Q11 $ Q11 Q11 -> N1 N3 N3 N4 N3 Q11 = Q11 1 Q11 1 Q11 $ Q11 Q11 -> N1 N3 N3 N4 Q11 1 Q11 = Q11 1 Q11 1 Q11 $ Q11 Q11 -> N1 N3 N3 Q11 * Q11 1 Q11 = Q11 1 Q11 1 Q11 $ Q11 Q11 -> N1 N3 Q11 1 Q11 * Q11 1 Q11 = Q11 1 Q11 1 Q11 $ Q11 Q11 -> N1 Q11 1 Q11 1 Q11 * Q11 1 Q11 = Q11 1 Q11 1 Q11 $ Q11 Q11 -> Q11 # Q11 1 Q11 1 Q11 * Q11 1 Q11 = Q11 1 Q11 1 Q11 $ Q11 Q11 -> # Q11 1 Q11 1 Q11 * Q11 1 Q11 = Q11 1 Q11 1 Q11 $ Q11 Q11 -> # 1 Q11 1 Q11 * Q11 1 Q11 = Q11 1 Q11 1 Q11 $ Q11 Q11 -> # 1 1 Q11 * Q11 1 Q11 = Q11 1 Q11 1 Q11 $ Q11 Q11 -> # 1 1 * Q11 1 Q11 = Q11 1 Q11 1 Q11 $ Q11 Q11 -> # 1 1 * 1 Q11 = Q11 1 Q11 1 Q11 $ Q11 Q11 -> # 1 1 * 1 = Q11 1 Q11 1 Q11 $ Q11 Q11 -> # 1 1 * 1 = 1 Q11 1 Q11 $ Q11 Q11 -> # 1 1 * 1 = 1 1 Q11 $ Q11 Q11 -> # 1 1 * 1 = 1 1 $ Q11 Q11 -> # 1 1 * 1 = 1 1 $ Q11 -> # 1 1 * 1 = 1 1 $

Context-sensitive grammar generation:

 S -> S12 S1 -> S12 S13 S1 -> S12 S13 S5 S1 -> S12 S13 S5 S13 S1 -> S12 S13 S5 S13 S9 S1 -> S12 S13 S5 S13 S9 S13 S1 -> S12 S13 S5 S13 S9 S13 S14 -> S824 S13 S5 S13 S9 S13 S14 -> S177 S492 S5 S13 S9 S13 S14 -> S177 S13 S435 S13 S9 S13 S14 -> S177 S13 S5 S556 S9 S13 S14 -> S177 S13 S5 S168 S110 S13 S14 -> S177 S13 S5 S169 S9 S13 S14 -> S177 S13 S48 S168 S9 S13 S14 -> S177 S343 S5 S168 S9 S13 S14 -> S177 S168 S259 S168 S9 S13 S14 -> S177 S168 S5 S349 S9 S13 S14 -> S177 S168 S5 S168 S307 S13 S14 -> S177 S168 S5 S168 S9 S202 S14 -> S177 S168 S5 S168 S110 S168 S14 -> S177 S168 S5 S169 S9 S168 S14 -> S177 S168 S48 S168 S9 S168 S14 -> S177 S339 S5 S168 S9 S168 S14 -> S344 S168 S5 S168 S9 S168 S14 -> S170 S349 S5 S168 S9 S168 S14 -> S170 S168 S259 S168 S9 S168 S14 -> S170 S168 S5 S349 S9 S168 S14 -> S170 S168 S5 S168 S307 S168 S14 -> S170 S168 S5 S168 S9 S198 S14 -> S170 S168 S5 S168 S9 S168 S203 -> S170 S168 S5 S168 S9 S169 S186 -> S170 S168 S5 S168 S110 S168 S186 -> S170 S168 S5 S169 S9 S168 S186 -> S170 S168 S48 S168 S9 S168 S186 -> S170 S339 S5 S168 S9 S168 S186 -> S340 S168 S5 S168 S9 S168 S186 -> S768 S168 S5 S168 S9 S168 S186 -> S769 S168 S5 S168 S9 S168 S186 -> S177 S369 S5 S168 S9 S168 S186 -> S177 S13 S291 S168 S9 S168 S186 -> S177 S13 S5 S359 S9 S168 S186 -> S177 S13 S5 S168 S317 S168 S186 -> S177 S13 S5 S208 S9 S168 S186 -> S177 S13 S108 S13 S9 S168 S186 -> S177 S13 S5 S502 S9 S168 S186 -> S177 S13 S5 S13 S471 S168 S186 -> S177 S13 S5 S13 S9 S185 S186 -> S177 S13 S5 S13 S9 S13 S187 -> S177 S13 S5 S13 S9 S13 S791 -> S177 S13 S5 S13 S9 S13 S821 -> S177 S13 S5 S13 S9 S13 1 -> S177 S13 S5 S13 S9 1 1 -> S177 S13 S5 S13 = 1 1 -> S177 S13 S5 1 = 1 1 -> S177 S13 * 1 = 1 1 -> S177 1 * 1 = 1 1 -> 1 1 * 1 = 1 1
