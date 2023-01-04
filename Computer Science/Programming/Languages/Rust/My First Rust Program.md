# Cargo File

```toml
[package]
name = "learning_rust"
version = "0.1.0"
edition = "2021"

[dependencies]
rand = "0.8.5"

[[bin]]
name = "learning_rust"
path = "main.rs"
```

# Code
```Rust
use rand::Rng; //library
use std::cmp::Ordering; //library
use std::io; //library

fn main() {
	println!("Guess the number!"); // "functions" with ! is a macro

	let mut generator = rand::thread_rng();
	let secret_number = generator.gen_range(1..=100);

	println!("The secret number is: {secret_number}");
	
	loop {
		println!("Please input your guess.");
	
		let mut guess = String::new();
	
		io::stdin()
			.read_line(&mut guess)
			.expect("Failed to read line");
	
		let guess: u32 = match guess.trim().parse() {
			Ok(num) => num,
			Err(_) => continue,
		};
	
		println!("You guessed: {guess}");
	
		match guess.cmp(&secret_number) {
			Ordering::Less => println!("Too small!"),
			Ordering::Greater => println!("Too big!"),
			Ordering::Equal => {
				println!("You win!");
				break;
			}
		}
	}
}
```