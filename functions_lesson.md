# Python Functions

- Context: what are functions? why are they helpful?

## Using Functions

<div style="padding: 1em 3em; border: 1px solid black;">
    <div style="font-weight: bold; font-size: 1.2em; border-bottom: 1px dashed black; padding-bottom: .5em;">
        Vocab
    </div>
    <ul>
        <li>Run/invoke/call</li>
        <li>Argument</li>
        <li>Return Value</li>
    </ul>
</div>

We've already used built-in functions

<div style="background-color: rgba(0, 100, 200, .1); padding: 1em 3em; border-radius: 5px; border: 1px solid black">
    <div style="font-weight: bold; font-size: 1.2em; border-bottom: 1px dashed black; padding-bottom: .5em;">
        Mini Exercise -- Using Functions
    </div>
    <ol>
        <li>
            <p>Take a look at this code snippet:</p>
            <pre><code>max([1, 2, 3])</code></pre>
            <p>What is the function name?</p>
            <p>Where is the function invocation?</p>
            <p>What is the return value?</p>
        </li>
        <li>
            <p>Take a look at this code snippet:</p>
            <pre><code>type(max([1, 2, 3]))</code></pre>
            <p>What will the output be? Why?</p>
        </li>
        <li>
            <p>Take a look at this code snippet:</p>
            <pre><code>type(max)</code></pre>
            <p>What will the output be? Why?</p>
        </li>
        <li>
            <p>What is the difference between the two code blocks below?</p>
            <pre><code>print</code></pre>
            <pre><code>print()</code></pre>
        </li>
        <li>What other built in functions do you know?</li>
    </ol>
</div>

## Defining Functions

<div style="padding: 1em 3em; border: 1px solid black;">
    <div style="font-weight: bold; font-size: 1.2em; border-bottom: 1px dashed black; padding-bottom: .5em;">
        Vocab
    </div>
    <ul>
        <li>Function Definition</li>
        <li>Function Name</li>
        <li>Argument</li>
        <li>Parameter</li>
        <li>Function Body</li>
    </ul>
</div>


```python
def increment(n):
    return n + 1
```

<div style="background-color: rgba(0, 100, 200, .1); padding: 1em 3em; border-radius: 5px; border: 1px solid black">
    <div style="font-weight: bold; font-size: 1.2em; border-bottom: 1px dashed black; padding-bottom: .5em;">
        Mini Exercise -- Defining Functions
    </div>
    <ol>
        <li>What is the difference between calling and defining a function?</li>
        <li>
            <p>What is the difference between the two code blocks below?</p>
            <pre><code>def increment(n):
    return n + 1</code></pre>
            <pre><code>def increment(n):
    print(n + 1)</code></pre>
        </li>
        <li>Create a function named <code>nonzero</code>. It should accept a number and return true if the number is anythong other than zero, false otherwise.</li>
        <li>Use your <code>nonzero</code> function in combination with the built-in <code>input</code> function and an <code>if</code> statement to prompt the user for a number and print a message displaying whether or not the number is zero.</li>
        <li>Transfer the work you have done into a function named <code>explain_nonzero</code>. Calling this function whould prompt the user and display the message as before.</li>
    </ol>
</div>

### Default Parameter Values and Keyword Arguments


```python
def sayhello(name="Easley"):
    return f"Hello, {name}!"
```

## Function Scope

- defining variables inside/outside of functions
- defines where a variable can be referenced

<div style="padding: 1em 3em; border: 1px solid black;">
    <div style="font-weight: bold; font-size: 1.2em; border-bottom: 1px dashed black; padding-bottom: .5em;">
        Vocab
    </div>
    <ul>
        <li>Scope</li>
        <li>Global</li>
        <li>Local</li>
    </ul>
</div>


```python
# NB. function names and variables are very generic here because the concept is very generic
def f():
    x = 123

f()    
print(x)
```


```python
x = 123

def f():
    print(x)

f()    
```


```python
x = 123

def f(x):
    return x + 1

print(f(12))
```

<div style="background-color: rgba(0, 100, 200, .1); padding: 1em 3em; border-radius: 5px; border: 1px solid black">
    <div style="font-weight: bold; font-size: 1.2em; border-bottom: 1px dashed black; padding-bottom: .5em;">
        Mini Exercise -- Function Scope
    </div>
    <ol>
        <li>What is the difference between local and global scope? Which is preferred?</li>
        <li>Take a look at the cell below this one. Before running it, think about what you would expect to happen. Explain step by step how the python code is executing.</li>
    </ol>
</div>


```python
def changeit(x):
    x = x + 1

x = 42
print(x)
changeit(x)
print(x)
```

### Function Scope Example

```python
def fill_nulls(df):
    return df.fillna(0)
    
def drop_outliers(df):
    outlier_cutoff = 3
    return df[df.zscore().abs() < 3]
    
def prep_dataframe(df):
    df = fill_nulls(df)
    df = drop_outliers(df)
    return 
```

[Data Prep example](https://github.com/CodeupClassroom/darden-nlp-exercises/blob/main/nlp_prepare.py). The specifics here aren't important right now, just pay attention to the overall shape of functions and how local scope is used.

## Lambda Functions

- A function as an expression
- used for "throw away", or one-off, functions


```python
def increment(n):
    return n + 1

# same as

increment = lambda n: n + 1
```

**Use case**: sorting (min, max too)

Python doesn't know how to compare dictionaries, but it does know how to compare strings or numbers


```python
students = [
    {"name": "Ada Lovelace", "grade": 87},
    {"name": "Thomas Bayes", "grade": 89},
    {"name": "Christine Darden", "grade": 99},
    {"name": "Annie Easley", "grade": 94},
    {"name": "Marie Curie", "grade": 97},
]
```


```python
# sort by name
sorted(students, key=lambda s: s["name"])
```


```python
# sort by grade
sorted(students, key=lambda s: s["grade"])
```

<div style="background-color: rgba(0, 100, 200, .1); padding: 1em 3em; border-radius: 5px; border: 1px solid black">
    <div style="font-weight: bold; font-size: 1.2em; border-bottom: 1px dashed black; padding-bottom: .5em;">
        Mini Exercise -- Lambda Functions &amp; Sorting
    </div>
    <p>Write the code necessary to sort the list of student dictionaries by student <em>last</em> name.</p>
    <p>Hints:</p>
    <ul>
        <li>You will need to write a function that takes in a student dictionary and returns just the last name.</li>
        <li>You can use the <code>.split</code> string method to seperate the first name and the last name.</li>
    </ul>
</div>
