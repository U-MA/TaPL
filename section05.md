# Section 5

## 5.2.1

```ocaml
or = lambda b. lambda c. b tru c;
not = lambda b. b fls tru;
```

## 5.2.2

```ocaml
scc' = lambda n. lambda s. lambda z. n s (s z);
```

## 5.2.3

```ocaml
times' = lambda m. lambda n. lambda s. lambda z. m (n s) z;
```

## 5.2.4

```ocaml
c1 = lambda s. lambda z. s z;
exp = lambda m. lambda n. n (times m) c1;
```

## 5.2.5

```ocaml
sub = lambda m. lambda n. n prd m;
```

## 5.2.6

O(n) steps.  
  
```prd``` creates n pairs by n steps.  
Finally ```prd``` return first element of last pair.  
So, ```prd``` needs O(n) steps.  

## 5.2.7

```ocaml
equal = lambda m. lambda n. and (iszro (m prd n)) (iszro (n prd m));
```

## 5.2.8

```ocaml
nil = lambda c. lambda n. n;
cons = lambda h. lambda t. lambda c. lambda n. c h (t c n);
isnil = lambda l. l (lambda h. lambda t. fls) tru;
head = lambda l. l tru nil;
tail = lambda l.
  fst (l (lambda x. lambda p. pair (snd p) (cons x (snd p)))
         (pair nil nil));
```

## 5.2.9

```test``` evaluates all arguments because evaluation strategy is call-by-value.  

gの定義の中で、```test``` を使用すると、発散するので```if``` を使用した。  
具体的には```factorial c0``` を評価する際に```test``` のすべての引数を評価し、
```test``` の第3引数の評価時に再び```factorial c0``` が現れる。  
そのため、```test``` を用いると発散する。  
```test``` の第3引数を評価しないようにするために、
元の第3引数をラムダ抽象で覆う必要がある。
第3引数をラムダ抽象で覆うと同時に第2引数もラムダ抽象で覆う必要がある。

```ocaml
g' = lambda fct. lambda n. test (iszro n c0)
      (lambda x. c1)
      (lambda x. (times n (fct (prd n)))) c0;
```

## 5.2.10

```ocaml
cn = lambda f. lambda m. if iszero m then zero else scc (f (pred m));
churchnat = fix ch;
```

## 5.2.11

```ocaml
ss = lambda s. lambda l. test (isnil l)
  (lambda x. c0)
  (lambda x. plus (head l) (s (tail l))) c0;
listsum = fix ss;
```

## 5.3.3

項```t```のサイズに対する帰納法を用いて、証明する。  
1. ```t = x```の場合  
```|FV(t)| = |FV(x)| = |{x}| = size(t) = 1```
2. ```t = λx. t1```の場合  
帰納法の仮定より、```|FV(t1)| <= size(t1)```  
```|FV(t)| = |FV(t1)\{x}| < |FV(t1)| <= size(t1) < size(t)```
3. ```t = t1 t2```の場合  
帰納法の仮定より、```|FV(t1)| <= size(t1)``` かつ ```|FV(t2)| <= size(t2)```  
```|FV(t)| = |FV(t1) ∪ FV(t2)| <= |FV(t1)| + |FV(t2)| <= size(t1) + size(t2) <= size(t)```  
  
よって、任意の項```t```について```|FV(t)| <= size(t)```

## 5.3.6

Not answered yet.

## 5.3.7

Not answered yet.

## 5.3.8

Not answered yet.
