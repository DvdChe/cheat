# Vim tricks

## Shortcut :


## Misc:

```
> = indent
. = repeat last operation
d = delete
c = change
y = yank
```

## Nouns:

 - `w` = Jump to word
 - `b` = Jump back word
 - `j` = Jump line
 - `k` = jump backward line
 - `h,l` = right, left
 - `ip` = inner paragraph 
 - `iw` = inner word
 - `it` = inner tag (html/xml stuff)


## Delete stuffs:

### Delete till something :
  
 - dt[nouns] = delete untill [nouns]
 - dtl = delete untill letter l

### Delete innter something

  - `di[nouns]` = delete inner element.
  - `di'` = delete inner quote
  - `diw` = delete inner word
  - `dip` = delete inner paragraph
  - `dit` = delete inner tags

## Buffers ( opens many files in one vim ) :

  Create buffer : ```:badd <buffer name>```
  List buffers : ```:bls``` 
  Go to buffer : ```:b <buffer number>```

## Play with number

  ctrl+a : goto first number in current line and increment
  creating list number : ```:put range(int start, int stop)``` 


## Save to clipboard

```
 :w !xclip -selection clipboard 
```
