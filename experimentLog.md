# TicTacToe:
## Parameters
 - Number of epoches: 8000

## Result
 -  Value Distribution: {-1: 23, 0: 18, 1: 59}
 -  Some Predicates:
    ```
    '0.739: invented(X,Y):-invented2(Y,X),invented2(Y,X)'
    '0.978: invented2(X,Y):-opponent(Z,Z),empty(X,Y)'
    '0.138: invented3(X):-opponent(Y,Y),succ(X,Y)'
    '0.997: invented4(X):-opponent(X,Y),mine(Z,Z)'
    '0.239: place(X,Y):-empty(X,Y),empty(X,Y)'
    '0.401: place(X,Y):-empty(X,Y),empty(X,Z)'
    '0.174: place(X,Y):-empty(X,Y),empty(Z,Y)'
    '0.121: place(X,Y):-empty(X,Y),zero(Z)'
    ```

## Discussion
There is no connection among invented predicates, thus no interpretable predicates have been found. For example, for <'invented3(X):-opponent(Y,Y),succ(X,Y)'>, what all know is if opponent occupies (Y,Y) (cell on diagonal) and 'X +1 = Y', we can perform an operation for X. What we need is a predicates chain which points to "Place" like < pred1,pred2 -> pred3 -> place >