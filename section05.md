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
