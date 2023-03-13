### The way that rust handle memory

## Description

- ### Each value in Rust has an _owner_.
- ### There can only be one owner at a time.
- ### When the owner goes out of scope, the value will be dropped.


## Example
```Rust
fn return_something () { 
	let output = String::from("b"); 
	return output; // output ownership is given
}

fn do_something (var : String) { // var Ownership is given to this scope
	// code...
} // var is drop (free()) here 

fn main(){
	let var = String::from("a");

	do_something(var); // after this var is not accessible

	let var2 = return_something(); // The ownership is given to var2

	let var3 = var2; // after this var2 is not accessible, only var3
}
```

---

# Reference

## Description 

### How to pass argument without giving the ownership

### In functions with more than one reference, use Lifetime. ![[Generics, Traits and Lifetimes in Rust#Lifetimes]]


## Rules 

-   You can have _either_ one mutable reference _or_ any number of immutable references.
-   References must always be valid.

## Example
```Rust
fn do_something (var : &mut String) { // must be mut to be write on
	// code that alter var...
}

fn read_this (var : &String) { // var Ownership is NOT given to this scope
	// code that read var...
}

fn main(){
	let var = String::from("a");

	read_this(&var); // after this var is still accessible

	let mut var2 = String::from("b");
	
	do_something(&mut var2);
}
```

---

# Slice

## Example
```Rust
let s = String::from("hello world"); 
let hello = &s[0..5]; 
let world = &s[6..11];

// Still the same memory
```