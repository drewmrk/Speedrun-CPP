# Speedrun C++

Tips and tricks to speedrun C++!

## Information

### About

A collection of tips and tricks to make writing C++ faster. Really for no reason in particular other than for fun. Some of the tips/tricks here are most certainly not good styling or coding practice but rather something that is more interesting to know, than to actually use.

### Styling

These tips/tricks will adhere to being legible so there should be no need to worry about that. For example, if a trick is describing an `if` statement with no braces, it will not look like this:

```cpp
if(1==1)return 3;
```

It will instead look like following:

```cpp
if (1 == 1) return 3;
```

## Tips/Tricks

### No braces

Some statements and control operators allow you to completely omit braces under certain circumstances.

Examples:

```cpp
// Before
if (x == y) {
  return true;
}

// After
if (x == y) return true;
```

```cpp
// Before
while (x == y) {
  cout << "This is correct";
}

// After
while (x == y) cout << "This is correct";
```

### Initialization

Instead of explicity assigning values to variables when creating them, one can initialize them, saving characters.

Examples:

```cpp
// Before
vector<string> words = {"This", "is", "correct"};
int index = 0;

// After
vector<string> words{"This", "is", "correct"};
int index{};
```

```cpp
// Before
for (int i = 0; i < 64; i++) {
  cout << i;
}

// After
for (int i{}; i < 64; i++) {
  cout << i;
}

// Combination
for (int i{}; i < 64; i++) cout << i;
```

### Type conversion

Sometimes C++ can be annoying, and it requires certain types to be converted. Luckily, there are shortcuts.

Examples:

```cpp
vector<int> ints = {1, 2, 3};

// Before
for (int i = 0; i < static_cast<int>(ints.size()); i++) {
  cout << ints[i];
}

// After
for (int i = 0; i < (int) ints.size(); i++) {
  cout << ints[i];
}

// Combination
for (int{}; i < (int) ints.size(); i++) cout << ints[i];
```
