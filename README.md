java c
Language Feature
The user manual of this language is listed.
Keywords:
·   “let”: initiates a variable declaration.
·   “be”: acts as the assignment operator in other programming language.
·   “int”: specifies the variable is of integer type   during its declaration.
·   “set”: specifies the variable is of set type   during its declaration.
·   “show”: acts as the main function in other programming languages, which initialize a calculation.
Data types:
·   Integer:
o   Basic data type
o   A single-digit integer is an arbitrary decimal number.
o   A multi-digit integer starts with a non-zero decimal number and followed by any sequence of arbitrary decimal numbers.
o   Users can only declare non-negative integers. Negative integers are constructed through subtraction operations.   
·   Arithmetic expression:
o   Constructed data type
o   Users are not   allowed to declare   an arithmetic expression. There is no specific data type keyword for arithmetic expressions in the language. This data type only exists in the compiler. You can also check the keywords. There is no data type keyword for arithmetic expressions.
o   An atomic arithmetic expression   is either an integer constant or an integer variable.
o   A compound arithmetic expression consists of two arithmetic expressions connected by an arithmetic operator (addition “+”, subtraction “-”, multiplication “*”). And parentheses are used to define substructures within expression. For example,1 + 2 – 3 * 4
is parsed as:( 1 + 2 ) - ( 3 * 4 )
·   Predicates
o   Constructed data type
o   Same as arithmetic expression, predicates are not   directly declared   by users but are instead managed within the compiler.
o   An atomic predicate   is a relational comparison, which can be of two types:
-   Integer value comparison: involving the comparison of two integers using relational operator less than (“<”), greater than (“>”), or equality (“=”); or
-   Membership testing: used to determine if an element is a member of a set using the membership operator “@”.
o   A compound predicate   is formed by combining “smaller” predicates (either atomic or compound) using logical operators:
-   Binary logical operators: two (atomic or compound) predicates connected by a conjunction (“”) or disjunction (“|”)
-   Unary logical operators: Negation (“!”) which precedes another predicate.
For example,P  Q
and! R
where P, Q, and R are predicates.
o   Parentheses are also used to define substructures in predicates. Parentheses are essential for defining the precedence and grouping of operations within predicates, ensuring the correct evaluation of complex expressions.
·   Bool:
o   Basic data type
o   Cannot   be declared by users
o   Has only two constants: “true” and “false”
o   A Boolean is produced by the evaluation on a predication without uninitialized variables. For example,x > 5
is a predicate if variable x has not been initialized. But if x has been initialized as 3 previously, then the predicate becomes3 > 5
and can be evaluated to be Boolean “false”. The behavior. of “>” will be explained later in this document.
·   Set:
o   Constructed data type
o   Can be declared by users
o   A set is defined in using this syntax within the language{ x : P(x) }
where
-   a set defnition is enclosed within curly braces “{ }”;
-   “x” is a variable name called representative, whose scope is limited within this   set   definition;
-   “:” is another punctuation separating the representative x from the rest part of the definition;
-   “P(x)” is a predicate that applies to the variable x, serving as the characteristic function of the set, which performs a logical test on x. If P(x) evaluates to true, then x is an element of the set; otherwise, x is not in the set.
o   代 写Language Feature
代做程序编程语言This project focuses solely on sets of integers. Other types of sets, such as sets of strings, pairs, or sets of sets are not included. This limitation is intentional, aiming to simplify the implementation process. Goliath is trying to make your life easy!
·   Void:
o   Basic data type
o   Cannot   be declared by users
o   For subexpressions without any type
Identifier: arbitrary strings of English letters in lower case   and are not reserved by keywords.
Operators:
·   Arithmetic operators:
o   “+”: integer addition, calculates the sum of two integers
o   “-”: integer subtraction, calculates the difference of two integers
o   “*”: integer multiplication, calculates the product of two integers
o   Multiplication has the highest precedence. Addition and subtraction have equal precedence, which is lower than multiplication.
·   Relational operators (for integers):
o   “<” (Less Than): returns “true” if the left-hand side integer is less than   the integer on the right-hand side
o   “>” (Greater Than): returns “true” if the integer on the left-hand side is greater   than the integer on the right-hand side integer
o   “=”: (Equal), returns “true” if the integer on the left-hand side is equal   to the integer on the right-hand side integer
·   Relational operator (membership):
o   “@”: This operator checks if the element on the left-hand side is a member of the set on the right-hand side. It returns “true” if the element is in   set, otherwise it returns “false”.
·   Logical operators:
o   conjunction “”, disjunction “|”, and negation “!” are behaved as the following.Truth Tables for Logical Operators:truefalse   |truefalse            truetruefalse   truetruetrue   xtruefalsefalsefalsefalse   falsetruefalse   !xfalsetrueConjunction table
   Disjunction table
   Negation table
o   Negation has the highest precedence, then conjunction, and then disjunction.   
·   Set operators:
o   “I”: set intersection, calculates the intersection   of two sets
o   “U”: set union, calculate the union   of two sets
o   Intersection has a higher precedence   than union.   
Sentences:
·   Each source code   contains zero, one, or multiple variable declaration(s); and exactly one calculation expression.
·   Each variable declaration   is in the following syntaxlet T id be E .
where
o   T is a type name (either int or set),
o   id is a variable identifier,
o   E is an expression that assigns a value (a set definition is also a “value”, even it is not a number) of the specific type to the variable.
o   The period “.” Marks the end of the declaration.
For example,let int a be 5 .
defines an integer a whose value is 5. Andlet set s be { x : x = 5 } .
defines a set s which contains only one integer 5.   
·   A calculation expression   starts with keyword “show” and followed by an algebraic expression, which can be an arithmetic expression, a Boolean expression (a predicate with all variables initialized), or a set algebra expression. A calculation expression is also ended by a full stop “.”. For example,
o   To calculates the union of sets S1 and S2:    show S1 U S2 .
o   To calculates the sum of integers 1 and 2: show 1 + 2 .
o   To test if integer 3 in S1 or not: show 3 @ S1 .   
Output: After the calculation, the program prints the outcome on the screen (type and value). (see the examples below). For set operators, the “show” statement does not simplify the characteristic function. For example,show { x : x > 3 } U { x : x > 5 } .
will output{ x : ( x > 3 ) | ( x > 5 ) }
rather than{ x : x > 3 }
even though the two sets are equivalent. This requirement will make this project easy. The simplification of predicates is an advanced feature and will be a bonus and explained later.



         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
