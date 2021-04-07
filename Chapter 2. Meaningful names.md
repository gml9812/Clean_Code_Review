

## 1. Use intention-revealing names ##
- name should answer: why it exists, what it does, and how it is used.
- name should not require comment.
- Ex 1:
```java
// Bad
public List<int[]> getThem() {
    List<int[]> list1 = new ArrayList<int[]>();
    for (int[] x : theList) {
        if (x[0] == 4) {
            list1.add(x);
        }
    }
    return list1;
}
```
 
```java
// Good
public List<int[]> getFlaggedCells() {
    List<int[]> flaggedCells = new ArrayList<int[]>();
    for (int[] cell : gameBoard) {
        if (cell[STATUS_VALUE] == FLAGGED) {
            flaggedCells.add(cell);
        }
    }
    return flaggedCells;
}
```

```java
// Best
public List<Cell> getFlaggedCells() {
 List<Cell> flaggedCells = new ArrayList<Cell>();
 for (Cell cell : gameBoard)
 if (cell.isFlagged())
 flaggedCells.add(cell);
 return flaggedCells;
 }
```

## 2. Avoid disinformation ##
- avoid words whose entrenched meanings vary from our intended meaning.
- Ex 1:
    - naming grouping of accounts as an "accountList"(which is not a list).
- beware of using names which vary in small ways.
- Ex 2:
    - "XYZControllerForEfficientHandlingOfStrings" and "XYZControllerForEfficientStorageOfStrings"
- spell similar concepts similarly. It makes automatic code completion easier to use.
- do not use lower-case L or uppercase O as variable names.
- Ex 3:
```java
int a = l;
if ( O == l )
 a = O1;
else
 l = 01;
```

## 3. Make meaningful distinctions ##
- do not change one name in an arbitrary way to use the same name to refer to two different things in the same scope.
- number-series naming provide no clue to the author's intention.
- Ex 1:
```java
public static void copyChars(char a1[], char a2[]) {
 for (int i = 0; i < a1.length; i++) {
 a2[i] = a1[i];
 }
 }
```
- do not use redundant words.
- Ex 1:
    - already using "Product", but adding "ProductInfo" ,"ProductData".
    - "zork", "thezork"

## 4. Use pronounceable names. ##
- programming is a social activity. You will eventually have to say the variable name.

## 5. Use searchable names. ##
- single-letter names and numeric constants are not easy to locate across a body of text.
- advise: The length of a name should correspond to the size of its scope. 
- If a variable or constant might be seen or used in multiple places in a body of code, give it a search-friendly name.

## 6. Avoid incodings. ##
- encoding type or scope information into names simply adds an extra burden of deciphering. 
- *

## 7. Avoid mental mapping ##
- clarity is king. Do not use names that require your memory(for example, single letter names).
- only exception: single letter variables used inside for loop.

## 8. Class names ##
- should be noun or noun phrase.
- Ex 1: 
    -Customer, WikiPage, Account, AddressParser.
    -avoid Manager, Processor, Data, Info.
- avoid verb.

## 9. Method names ##
- should have verb or verv phrase.
- Ex 1: 
    - postPayment, deletePage, save
- Accessors, mutators, and predicates should be named for their value and prefixed with get, set, and is.
- Ex 2:
```java
string name = employee.getName();
customer.setName("mike");
if (paycheck.isPosted())...
```
- When constructors are overloaded, use static factory methods with names that describe the arguments.
- Ex 3:
```java
Complex fulcrumPoint = Complex.FromRealNumber(23.0); //better than latter one
Complex fulcrumPoint = new Complex(23.0);
```
- *

## 10. Don't be cute ##
- Choose clarity over entertainment value.

## 11. Pick one word per concept ##
- Pick one word for one abstract concept and stick with it (fetch, retrieve, get... choose one).

## 12. Don't pun ##
- Avoid using the same word for two purposes.
- Ex 1:
```java
public static String add(String message, String messageToAppend)  
public List<Element> add(Element element)  
//should use "insert" or "append" for latter one.
```
# 13. Use solution domain names #
- go ahead and use computer science (CS) terms, algorithm names, pattern names, math terms, and so forth.

# 14. Use problem domain names #
- if there is no “programmer-eese” for what you’re doing, use the name from the problem domain. 

# 15. Add meaningful context #
- use classes, namespaces, prefixes ... to express context.
- Ex 1:
```java
// Bad
private void printGuessStatistics(char candidate, int count) {
 String number;
 String verb;
 String pluralModifier;
 if (count == 0) {
 number = "no";
 verb = "are";
 pluralModifier = "s";
 } else if (count == 1) {
 number = "1";
 verb = "is";
 pluralModifier = "";
 } else {
 number = Integer.toString(count);
 verb = "are";
 pluralModifier = "s";
 }
 String guessMessage = String.format(
 "There %s %s %s%s", verb, number, candidate, pluralModifier
 );
 print(guessMessage);
 }
```
 
```java
// Good
// Good
public class GuessStatisticsMessage {
    private String number;
    private String verb;
    private String pluralModifier;

    public String make(char candidate, int count) {
        createPluralDependentMessageParts(count);
        return String.format("There %s %s %s%s", verb, number, candidate, pluralModifier );
    }

    private void createPluralDependentMessageParts(int count) {
        if (count == 0) {
            thereAreNoLetters();
        } else if (count == 1) {
            thereIsOneLetter();
        } else {
            thereAreManyLetters(count);
        }
    }

    private void thereAreManyLetters(int count) {
        number = Integer.toString(count);
        verb = "are";
        pluralModifier = "s";
    }

    private void thereIsOneLetter() {
        number = "1";
        verb = "is";
        pluralModifier = "";
    }

    private void thereAreNoLetters() {
        number = "no";
        verb = "are";
        pluralModifier = "s";
    }
}
```

# 16. Don't add gratuitous context #
- Shorter names are generally better than longer ones, so long as they are clear. Add no more context to a name than is necessary.


