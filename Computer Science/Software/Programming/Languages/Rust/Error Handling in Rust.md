# Rust Errors Categories  
## Recoverable 

Errors that can be handled

```Rust
fn function() -> Result<T, Err> {
	let file = File::open("file.txt"); // exist
	let file = match file {
		Ok(file) => file,
		Err(err) => return err, 
	}

	let file = File::open("file2.txt"); // don't exist
	let file = file?; // if is an Error, return it, if not, continue the code
}
```

## Unrecoverable 

Symptoms of bugs (out of index or not handling error)

```Rust
let file = File::open("file.txt").unwrap(); // file.txt don't exist

let array = [1,2,3];
array.get(3); // out of index

panic!("error!"); // panic macro
```
