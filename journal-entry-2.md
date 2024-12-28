# Scheme Journal Day 2
2024-12-28

## 10 commandments

I'm starting to really know the 10 commandments of little schemer. I am trying not to treat it like memorization, but more just learning it. I might get the number wrong, but pretty sure I have a couple, so here's a little test of the memory

### #1
the first question of a function is always null?

### #2
to add an atom to a list use __*cons*__

### #3
????

Oof I've already lost track, better luck tomorrow.

## What I focused on.

So, I had already read the first 70 pages, but was starting to get lost, and decided to go back and reread. 

This was a great choice, this time around I really was grasping how to build a function, how to pass arguments, and how to create recursions.

A few that I worked on, I am going to try and rebuild them here.

#### atom?
```
(define atom?
    (lambda (a)
        (cond
        ((null? a)( '()) ;something might be missing, but I can't remember, also pretty sure I am aiming for false, but not sure.
        (eq? a (not (pair x)) #f))
        (else (atom? (Cdr a)))))))
```
The intent of *atom?* is to determine if the argument *a* is an atom and not a list.

#### insertR
```
(define insertR
    (lambda (new old lat)
        (cond
        ((null? lat )'())
        ((eq? (car lat) old)(cons old (cons new (cdr lat))))
        (else (cons old (insertR new old (cdr lat)))))))
```
The intent of insertR is to add the argument *new* to the right side of argument *old* in the list of atoms.

#### insertL
```
(define insertL
    (lambda (new old lat)
        (cond
        ((null? lat)('()))
        ((eq? (car lat) old)(cons new (lat)))
        (else (cons old)(insertL new old (cdr lat))))))
```        
the intent of insertL is to add the argument *new* to the right side of argument *old* in the list of atoms.

#### rember
```
(define rember
    (lambda (a lat)
        (cond
        ((null? lat)('()))
        ((eq? (car lat) a)(cons a (cdr lat)))
        (else (cons (car lat)(rember a (cdr lat)))))))
```
the intent of rember is to remove member *a*, or another way to say it is build a new list without atm *a*

###The day's conclusion
I learned a few other example functions, but can't remember them. I was also a bit shakey on the syntax. I think I may have added to many parenteses for null? but I am not sure.

I am also not as confident i know the commandments as I though I was. There's a few that are on the tip of my tongue but can't quite recall them. A chance to improve for tomorrows Journal entry.

Signing off - *Honkytonk Robot*