# Lists
A **list** is a data type which can contain a sequence of values.

Lists can be created in Voxel using the following syntax:

```voxel
var item = "banana";

var list = [123, true, null, "hello", item, [3, 2, 1], {object: true}];
```

List items are enclosed in square brackets (`[` and `]`), and are delimeted by commas (`,`). Items can be of any type.

## Reference

### `List`
The list data type.

#### `length: Number`
The number of items in the list.

#### `push(value: *): Number`
Push an item (`value`) onto the end of the list and return the new list length.

#### `pop(): *`
Pop the last item from the list (which removes it) and return that item.

#### `unshift(value: *): Number`
Insert an item (`value`) at the start of the list and return the new list length.

#### `shift(): *`
Remove the first item from the list and return that item.

#### `insert(index: Number, value: *): *`
Insert an item (`value`) onto the list at a specified index (`index`) and return that item.

#### `removeAt(index: Number): *`
Remove an item from the list at a specified index (`index`) and return that item.

#### `indexOf(value: *): Number`
Find the index of the first occurrence of a value (`value`) in the list and return it.

If the item cannot be found, `-1` will be returned instead.

#### `contains(value: *): Boolean`
Return `true` if a value (`value`) is in the list; otherwise, return `false`.

#### `remove(value: *): Boolean`
Remove the first occurrence of a value (`value`) in the list. Return `true` if it was found and removed; otherwise, return `false`.

#### `forEach(callback: function(item: *, index: Number))`
Iterate through the list and call a callback function (`callback`) for every item with arguments that reference the item (`item`) and the item's index (`index`).

#### `map(callback: function(item: *, index: Number): *): List<*>`
Iterate through the list and call a callback function (`callback`) for every item with arguments that reference the item (`item`) and the item's index (`index`).

The callback function must return a new value. A new list will be returned when calling `map` containing all values returned from calling the callback function for every item.

#### `filter(callback: function(item: *, index: Number): Boolean): List<*>`
Iterate through the list and call a callback function (`callback`) for every item with arguments that reference the item (`item`) and the item's index (`index`).

The callback function must return a boolean value. A new list will be returned when calling `filter` containing all values from the original list where the callback function returned `true`.

#### `find(callback: function(item: *, index: Number): Boolean): *`
Iterate through the list until the callback function (`callback`) called for every item returns `true`. Return the list item that caused the callback function to return `true`. The callback function is called with arguments that reference the item (`item`) and the item's index (`index`).

If the callback function never returns `true`, then `null` will be returned instead.

#### `findIndex(callback: function(item: *, index: Number): Boolean): Number`
Iterate through the list until the callback function (`callback`) called for every item returns `true`. Return the index of the list item that caused the callback function to return `true`. The callback function is called with arguments that reference the item (`item`) and the item's index (`index`).

If the callback function never returns `true`, then `-1` will be returned instead.

#### `reduce(callback: function(accumulator: *, item: *, index: Number): *, initialValue: *): *`

Iterate through the list and call a callback function (`callback`) for every item. The callback will be called with arguments for the previous call's return value or the initial provided value (`initialValue`) if it is the first call (`accumulator`), the current list item (`item`) and the item's index (`index`). The last call's return value will be used as the return value of `reduce`.