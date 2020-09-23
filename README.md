## Quick Links

**[Array](#array)**

1. [Filter falsy](#falsy) Create an array with all falsy values removed
1. [Concat](#concat) Create a new array concatenating array with any additional arrays and/or values

## Array

### Falsy

Creates an array with all falsy values removed

  ```js
  [0, 1, false, 2, '', 3].filter(Boolean)
  ```

### Concat

Creates a new array concatenating array with any additional arrays and/or values

  ```js
  var array = [1]
  var other = array.concat(2, [3], [[4]])

  console.log(other)
  // output: [1, 2, 3, [4]]
  ```

**[⬆ back to top](#quick-links)**