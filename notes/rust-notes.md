
## Result && Option

[Option](https://doc.rust-lang.org/std/option/enum.Option.html)

| Method                                              | For `None`| For `Some(value)`      | Typical Use Case              |
|-----------------------------------------------------|-----------|------------------------|-------------------------------|
| `map        <U, F>   (self, f: F) -> Option<U>`     | `None`    | Applies `F(T)`         | Transform contained value     |
| `and_then   <U, F>   (self, f: F) -> Option<U>`     | `None`    | Returns new Option     | Chaining operations (flatMap) |
| `map_or     <U, F>   (self, default: U, f: F) -> U` | `U`       | Applies `F(T)`         | Provide default for `None`    |
| `map_or_else<U, D, F>(self, default: D, f: F) -> U` | `D(T)`    | Applies `F(T)`         | Lazy default computation      |
| `unwrap_or        (self, default: T) -> T`          | `T`       | Returns `Some(value)`  | Provide default for `None`    |
| `unwrap_or_else<F>(self, f: F) -> T`                | `F(T)`    | Returns `Some(value)`  | Lazy default computation      |

[Result](https://doc.rust-lang.org/std/result/enum.Result.html)

| Method                                              | For `Err(e)`                    | For `Ok(value)`                     | Typical Use Case                        |
|-----------------------------------------------------|---------------------------------|-------------------------------------|-----------------------------------------|
| `map           <U, F>(self, op: F) -> Result<U, E>` | original `Err(e)`               | Applies `F`, returns `Ok(f(value))` | Transform the success value             |
| `and_then      <U, F>(self, op: F) -> Result<U, E>` | original `Err(e)`               | Applies `F`, returns `Result<U, E>` | Chain computations returning Result     |
| `map_err       <F, O>(self, op: O) -> Result<T, F>` | Applies op, returns `Err(op(e))`| `Ok(value)` unchanged               | Transform the error value               |
| `map_or        <U, F>(self, default: U, f: F) -> U` | Returns default `U`             | Applies `F(value)`                  | Map Ok or fallback default on Err       |
| `map_or_else<U, D, F>(self, default: D, f: F) -> U` | Calls `D(e)`                    | Applies `F(value)`                  | Map Ok or compute fallback based on Err |


Transforming contained values. These methods transform `Option` to `Result`:
- `ok_or` transforms `Some(v)` to `Ok(v)`, and `None` to `Err(err)` using the provided default `err` value
- `ok_or_else` transforms `Some(v)` to `Ok(v)`, and `None` to a value of `Err` using the provided function
- `transpose` transposes an `Option` of a `Result` into a `Result` of an `Option`


`Option`: `fn as_mut(&mut self) -> Option<&mut T>`: converts from `&mut Option<T>` to `Option<&mut T>`.

## Bool

    pub fn then<T, F>(self, f: F) -> Option<T>
    
## Slice

https://doc.rust-lang.org/std/primitive.slice.html

## Vec

https://doc.rust-lang.org/std/vec/struct.Vec.html

## Regular expression

    let re = Regex::new(r"^(\d+)-(\d+)$").unwrap();
    re.captures(val).ok_or(e).and_then(|captures) {
        // handle captures[1]
    });
    
## General

Swaps values

- `std::mem::swap`, If you want to replace the values of two variables

        // pub const fn swap<T>(x: &mut T, y: &mut T)
        // Swap the values at two mutable locations, without deinitializing either one
        std::mem::swap(&mut self.line_buf, self.lookahead_line.as_mut().unwrap());

- `std::mem::take`, If you want to swap with a default or dummy value

        // pub fn take<T>(dest: &mut T) -> T
        // Replaces dest with the default value of T, returning the previous dest value        

- `std::mem::replace`, If you want to swap with a passed value, returning the old value, see replace

        // pub const fn replace<T>(dest: &mut T, src: T) -> T
        // Moves src into the referenced dest, returning the previous dest value. Neither value is dropped.
        let old_v = mem::replace(&mut v, vec![3, 4, 5]);
