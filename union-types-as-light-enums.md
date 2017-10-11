# Union Types as Light Enums

If you define an `enum` in TypeScript, it becomes a lot of JavaScript code. If you need to use it like a classical `enum`, this may be necessary. But for most use cases, simple strings will do. They can be typed using [Union Types](https://www.typescriptlang.org/docs/handbook/advanced-types.html).

## Classical Enums

```
enum Direction {
    Up,
    Down,
    Left,
    Right
}

const myValue = Direction.Up
```

TypeScript's JavaScript output:

```
var Direction;
(function (Direction) {
    Direction[Direction["Up"] = 0] = "Up";
    Direction[Direction["Down"] = 1] = "Down";
    Direction[Direction["Left"] = 2] = "Left";
    Direction[Direction["Right"] = 3] = "Right";
})(Direction || (Direction = {}));
var myValue = Direction.Up;
```

## Make use of Union Types instead

```
type Direction =
    "Up" |
    "Down" |
    "Left" |
    "Right"

const myValue: Direction = "Up"
```

JavaScript output (one line):

```
var myValue = "Up";
```




