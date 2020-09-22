## Natural deforestation

Deforestation can happen when natural disasters such as drought, forest fire and tornados devastate an area of land. This can be particularly deadly as, in the wide area  affected, entire species can disappear with the destruction of their habitats.

Simulate the impact of natural disasters randomly moving through the forest.

--- task ---

When flag clicked hide.

```blocks3
when flag clicked
hide
```

--- /task ---

--- task ---

Forever go to show glide.

```blocks3
when flag clicked
hide
+ forever
go to x:(0) y:(200)
show
glide (3) secs to x:(0) y:(-200)
+ end
```

--- /task ---

--- task ---

Test.

--- /task ---

--- task ---

Hide next costume.

```blocks3
when flag clicked
hide
forever
go to x:(0) y:(200)
show
glide (3) secs to x:(0) y:(-200)
+ hide
+ next costume
end
```

--- /task ---

--- task ---

Wait random.

```blocks3
when flag clicked
hide
forever
+ wait (pick random (10) to (20)) seconds
go to x:(0) y:(200)
show
glide (3) secs to x:(0) y:(-200)
hide
next costume
end
```

--- /task ---

--- task ---

Move random.

```blocks3
when flag clicked
hide
forever
wait (pick random (10) to (20)) seconds
+ go to x:(pick random (-200) to (200)) y:(200)
show
+ glide (3) secs to x:(pick random (-200) to (200)) y:(-200)
hide
next costume
end
```

--- /task ---

--- task ---

Test.

--- /task ---
