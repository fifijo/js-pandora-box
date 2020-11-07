# JS Pandora Box 🏗️

## Quick Links

**[Array](#array)**

1. [chunk](#chunk)
1. [compact](compact)
1. [concat](#concat)
1. [difference](#difference)
1. [drop](#drop)
1. [dropRight](#dropRight)
1. [fill](#fill)
1. [find](#find)
1. [findIndex](#findindex)
1. [first](#first)
1. [flatten](#flatten)
1. [flattenDeep](#flattendeep)
1. [fromPairs](#frompairs)
1. [head and tail](#head-and-tail)
1. [indexOf](indexof)
1. [intersection](#intersection)

## Array

### chunk

Creates an array of elements split into groups the length of size.

```js
const chunk = (input, size) => (
  input.reduce((array, item, index) => (
    index % size === 0
      ? [...array, [item]]
      : [...array.slice(0, -1), [...array.slice(-1)[0], item]]
    ), [])
);

chunk(['a', 'b', 'c', 'd'], 3)
// => [['a', 'b', 'c'], ['d']]

```
**[⬆ back to top](#quick-links)**

### compact

Creates an array with all falsy values removed.

  ```js
  [0, 1, false, 2, '', 3].filter(Boolean)
  ```

**[⬆ back to top](#quick-links)**

### concat

Creates a new array concatenating array with any additional arrays and/or values.

  ```js
  var array = [1]
  var other = array.concat(2, [3], [[4]])

  // output: [1, 2, 3, [4]]
  ```
**[⬆ back to top](#quick-links)**

### difference
Similar to [without](#_without), but returns the values from array that are not present in the other arrays.

  ```js
  let arrays = [[1, 2, 3, 4, 5], [5, 2, 10]]
  arrays.reduce((a, b) => a.filter(c => !b.includes(c)))
  // output: [1, 3, 4]
  ```
**[⬆ back to top](#quick-links)**

### drop

Creates a slice of array with n elements dropped from the beginning.

  ```js
  [1, 2, 3].slice(2)
  // => [3]
  ```

**[⬆ back to top](#quick-links)**

### dropRight

Creates a slice of array with n elements dropped at the end.

  ```js
  [1, 2, 3].slice(0, -2)
  // => [1]
  ```

**[⬆ back to top](#quick-links)**

### fill

Fills elements of array with value from start up to, but not including, end.

  ```js
  const array = [1, 2, 3]

  array.fill('a')
  // output: ['a', 'a', 'a']

  Array(3).fill(2)
  // output: [2, 2, 2]

  [4, 6, 8, 10].fill('*', 1, 3)
  // output: [4, '*', '*', 10]
  ```

**[⬆ back to top](#quick-links)**

### find

Returns the value of the first element in the array that satisfies the provided testing function. Otherwise undefined is returned.

  ```js
  const users = [
    { 
        'user': 'Mati', 
        'age': 36, 
        'active': true 
    },
    { 
        'user': 'Seba',
        'age': 40,
         'active': false
    },
    { 
        'user': 'El presidento legacy',
        'age': 1,
        'active': true 
    }
  ]

  users.find(option => option.age < 40)
  ```

**[⬆ back to top](#quick-links)**

### findIndex

Returns the index of the first element in the array that satisfies the provided testing function. Otherwise -1 is returned.

  ```js
 const users = [
    { 
        'user': 'Mati', 
        'age': 36, 
        'active': true 
    },
    { 
        'user': 'Seba',
        'age': 40,
         'active': false
    },
    { 
        'user': 'El presidento legacy',
        'age': 1,
        'active': true 
    }
  ]

  const index = users.findIndex(option => option.age >= 40 )
  // output: 1
  ```
**[⬆ back to top](#quick-links)**

### first

Returns the first element of an array. Passing n will return the first n elements of the array.

  ```js
  [1, 2, 3, 4, 5][0];
  // => 1

  [].concat(1, 2, 3, 4, 5).shift()
  // => 1

  [].concat([1, 2, 3, 4, 5]).shift()
  // => 1

 [].concat(undefined).shift()
  // => undefined

  [1, 2, 3, 4, 5].slice(0, 2);
  // => [1, 2]
  ```

**[⬆ back to top](#quick-links)**

### flatten

Flattens array a single level deep.

  ```js
  // Native(ES2019)
  const flatten = [1, [2, [3, [4]], 5]].flat()
  // => [1, 2, [3, [4]], 5]

  const flatten = [1, [2, [3, [4]], 5]].flatMap(number => number)
  // => [1, 2, [3, [4]], 5]
  ```
**[⬆ back to top](#quick-links)**

### flattenDeep

Recursively flattens array.

  ```js
  // Native(ES2019)
  [1, [2, [3, [4]], 5]].flat(Infinity)
  // => [1, 2, 3, 4, 5]
  
  const flattenDeep = array =>
      array.flatMap((subArray, index) => 
          Array.isArray(subArray)
            ? flattenDeep(subArray)
            : subArray)

  flattenDeep([1, [[2], [3, [4]], 5]])
  // => [1, 2, 3, 4, 5]
  ```
**[⬆ back to top](#quick-links)**

### fromPairs

Returns an object composed from key-value pairs.

  ```js
  Object.fromEntries([['a', 1], ['b', 2]])
  // => { 'a': 1, 'b': 2 }
  ```
**[⬆ back to top](#quick-links)**

### head and tail
Gets the first element or all but the first element.

  ```js
  const array = [1, 2, 3]
  const [ head, ...tail ] = array
  console.log(head)
  // output: 1
  console.log(tail)
  // output [2, 3]
  ```

**[⬆ back to top](#quick-links)**

### indexOf

Returns the first index at which a given element can be found in the array, or -1 if it is not present.

  ```js
  var array = [2, 9, 9]
  var result = array.indexOf(2)
  // output: 0
  ```
**[⬆ back to top](#quick-links)**

### intersection
Returns an array that is the intersection of all the arrays. Each value in the result is present in each of the arrays.

  ```js
  // ES6
  let arrays = [[1, 2, 3], [101, 2, 1, 10], [2, 1]]

  arrays.reduce((a, b) => a.filter(c => b.includes(c)))
  // output: [1, 2]
  ```
**[⬆ back to top](#quick-links)**

# License

MIT