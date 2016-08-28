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

Not answered yet.

## 5.2.10

Not answered yet.

## 5.2.11

Not answered yet.

## 5.3.3

Not answered yet.

## 5.3.6

Not answered yet.

## 5.3.7

Not answered yet.

## 5.3.8

Not answered yet.
