# Conditional

## C

### if

```cpp
if (cond){
    statement;
}
```

Run `statement` if `cond` is `true`.

if `cond` is `false` then they do not run `statement`, jumping over to the end of the if block.

### if-else

```cpp
if (cond){
    statement1;
}
else{
    statement2;
}
```

Run `statement1` if `cond` is `true`, `statement2` otherwise.

### if-else if-else

```cpp
if (cond1){
    statement1;
}
else if (cond2){
    statement2;
}
else{
    statement3;
}
```

Run `statement1` if `cond1` is `true`.

Run `statement2` if `cond1` is `false` and `cond2` is `true`.

Run `statement3` if both `cond1` and `cond2` is `false`.

You can nest more `else if`s.

#### Tip: Parenthesis

if the `statement` is a single statement (that is, represented with 1 `;`), then you can remove `{` and `}`.

```cpp
if (cond1) return 1217;
```

### switch-case

// TODO