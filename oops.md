# Preferring kwarg over positional 

Existing function. 

```python
foo(a, b, c=10):
  pass
  
#  somewhere else....
foo(1, 2)
```

Now we need a d paramter. Just add it right?


```python
# add d
foo(a, b, c=10, d=20):
  pass
```

In one of the client code we now need to pass in d. Just add it in?

```
foo(1, 2, 100)
```

Whoops if the above code is written because caller was relying on C's default parameter. You passed 100 to c instead of d. 

Avoid this by being specific...

```python
foo(1, 2, d=100)
```

Even better, for non-well known functions e.g. not a standard of well known third party module, be specific for all your args.

```python
foo(a=1, b=2, d=100)
```

