
## Result && Option

Option

| Method        | Closure Type                                 | Behavior on `None`           | Behavior on `Some(value)`        | Return Type | Typical Use Case              |
|---------------|----------------------------------------------|------------------------------|----------------------------------|-------------|-------------------------------|
| map           | FnOnce(T) -> U                               | Returns `None`               | Applies the mapping closure      | Option<U>   | Transform contained value     |
| map_or        | FnOnce(T) -> U + default value               | Returns the default value    | Applies the mapping closure      | U           | Provide default for `None`    |
| map_or_else   | default: FnOnce() -> U + map: FnOnce(T) -> U | Calls default closure (lazy) | Calls the mapping closure        | U           | Lazy default computation      |
| and_then      | FnOnce(T) -> Option<U>                       | Returns `None`               | Returns the new Option           | Option<U>   | Chaining operations (flatMap) |


Result

| Method        | Args / Closure                               | Behavior on Err(e)            | Behavior on Ok(value)           | Return Type | Notes / Typical Use Case                |
|---------------|----------------------------------------------|-------------------------------|---------------------------------|-------------|-----------------------------------------|
| map           | f: T -> U                                    | Returns original Err(e)       | Applies f, returns Ok(f(value)) | Result<U, E>| Transform the success value             |
| map_err       | op: E -> F                                   | Applies op, returns Err(op(e))| Ok(value) unchanged             | Result<T, F>| Transform the error value               |
| map_or        | default: U, f: T -> U                        | Returns default               | Applies f, returns result       | U           | Map Ok or fallback default on Err       |
| map_or_else   | default: E -> U, f: T -> U                   | Calls default(e)              | Calls f(value)                  | U           | Map Ok or compute fallback based on Err |
| and_then      | f: T -> Result<U, E>                         | Returns original Err(e)       | Applies f, returns Result<U, E> | Result<U, E>| Chain computations returning Result     |


Transforming contained values. These methods transform Option to Result:
- ok_or transforms Some(v) to Ok(v), and None to Err(err) using the provided default err value
- ok_or_else transforms Some(v) to Ok(v), and None to a value of Err using the provided function
- transpose transposes an Option of a Result into a Result of an Option

## Bool

    pub fn then<T, F>(self, f: F) -> Option<T>

## Regular expression

    let re = Regex::new(r"^(\d+)-(\d+)$").unwrap();
    re.captures(val).ok_or(e).and_then(|captures) {
        // handle captures[1]
    });
    
