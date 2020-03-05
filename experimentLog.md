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


## Result2
 - Value Distribution:  {-1: 27, 0: 9, 1: 64}
 -  Some Predicates:
   ```
   '0.31: invented(X,Y):-invented3(X),mine(Y,Z)'
   '0.384: invented(X,Y):-opponent(X,Z),opponent(Z,Y)'
   '0.167: invented(X,Y):-mine(X,Z),mine(Y,Z)'

   '1.0: invented2(X,Y):-invented(Z,Z),empty(X,Y)'

   '1.0: invented3(X):-mine(Y,X),mine(Y,X)'
   
   '1.0: invented4(X):-opponent(X,Y),mine(Z,Z)'

   '0.9999999: place(X,Y):-empty(X,Z),invented2(X,Y)'
   ```
   
## Result3 
- Different initial value
  ``` x - o
      - - -
      o - x
  ```
- Steps: 1600
- Value Distribution: {1:100}
- Some Predicates:
  ```
   Predicate(name='invented', arity=2)
  '0.183: invented(X,Y):-invented4(X),invented4(Y)'
  '0.229: invented(X,Y):-invented4(X),empty(Y,Y)'
  '0.43: invented(X,Y):-invented4(Y),empty(X,X)'

  Predicate(name='invented2', arity=2)
  '0.623: invented2(X,Y):-invented(X,X),empty(Y,Y)'

  Predicate(name='invented3', arity=1)
  '0.14: invented3(X):-invented4(X),invented4(X)'
  '0.126: invented3(X):-invented4(X),mine(Y,Y)'
  '0.139: invented3(X):-empty(X,X),empty(Y,X)'

  Predicate(name='invented4', arity=1)
  '0.129: invented4(X):-empty(X,X),empty(Y,Z)'
  '0.622: invented4(X):-empty(X,X),succ(X,Y)'

  '0.208: place(X,Y):-invented4(X),invented4(Y)'
 ```

## Result4
-  Steps: 1600
- Value Distribution: {-1: 25, 0: 12, 1: 63}
- Some Predicates:
   ```
     Predicate(name='invented', arity=2)
     '0.858: invented(X,Y):-empty(X,Y),empty(X,Z)'
     '0.119: invented(X,Y):-empty(X,Y),empty(Z,Y)'

     Predicate(name='invented2', arity=2)
     '0.307: invented2(X,Y):-zero(Z),empty(X,Y)'
     '0.418: invented2(X,Y):-empty(X,Y),empty(X,Y)'
     '0.121: invented2(X,Y):-empty(X,Y),empty(X,Z)'
     '0.155: invented2(X,Y):-empty(X,Y),empty(Z,Y)'

     Predicate(name='invented3', arity=1)

     Predicate(name='invented4', arity=1)
     '0.929: invented4(X):-empty(Y,X),empty(Y,X)'

     Predicate(name='place', arity=2)
     '0.186: place(X,Y):-invented2(X,Z),empty(X,Y)'
     '0.166: place(X,Y):-zero(Z),empty(X,Y)'
     '0.458: place(X,Y):-empty(X,Y),empty(X,Y)'
   ```
