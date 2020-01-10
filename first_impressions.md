## Go!

### Types

#### Typing functions

You can type the return types of functions like this:

```go
// As you might expect
func add(x int, y int) int {
  return x + y
}

// Go functions can return multiple values though, so you
// Can type each of the return values
func swap(x, y string) (string, string) {
  return y, x
}

// But you can also name the return values.
func swap(x, y string) (left string, right string) {
  return y, x
}

// More than that, those named return values become variables you
// can use in the function. (They are already declared and typed)
func swap(x, y string) (left string, right string) {
  left = y
  right = x
  return left, right
}

// If you just write a bare return, the function will return the
// named return values (in this case left and right). So this
// is equivalent to above:
func swap(x, y string) (left string, right string) {
  left = y
  right = x
  return
}

// This might be a gotcha...
func swap(x, y string) (left string, right string) {
  original_x := x
  x = y
  y = original_x
  return
}

// In the above function although we swap, we end up returning two empty strings
// because a bare `return` will return all named return values. Because they are
// not re-assigned in the function, they get evaluated to their default type
// values. They are strings, so the default value is an empty string.
```
