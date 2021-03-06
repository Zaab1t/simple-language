# simple-language

This is a very simple programming language and interpreter.

## Hello World!

Save this to `hello.simple`:

```python
const msg = "hello world";
print msg;
```

Here `print` is a function, not a keyword. Functions are just called without
parentheses.

Run the code like this:

    $ python3 -m simplelang hello.simple

My favorite feature with this language is blocks. Anything between `{`
and `}` is a block, and blocks have a `.run` method that works like
this:

```python
const helloblock = {
    print "hello world";
};

# run it 3 times
helloblock.run;
helloblock.run;
helloblock.run;
```

Of course, every block gets a new scope; variables defined in `{ }` are
not visible outside of the `{ }`:

```python
{
    const a = "hello";
    print a;    # prints hello
}.run;
print a;    # error!
```

See [the examples directory](examples/) for more!

## Tests

At the time of writing this README, I have a good test coverage.

    $ python3 -m coverage run -m pytest
    $ python3 -m coverage html
    $ yourfavoritebrowser htmlcov/index.html
