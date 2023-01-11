```Rust
#[derive(Debug)] // => Define an Implementation of Debug to Rectangle
struct Rectangle { // Define the Struct 
	width: u32,
	height: u32,
}

impl Rectangle { // Implement Methods for the Struct
	fn square(size: u32) -> Self {
		Self {
			width: size,
			height: size,
		}
	}
	
	fn area(&self) -> u32 {
		self.width * self.height
	}
	
	fn can_hold(&self, other: &Rectangle) -> bool {
		self.width > other.width && self.height > other.height
	}
}

fn main() {
	let rect = Rectangle::square(10); // :: -> Associated Function 

	let rect2 = dbg!(rect); // Prints Rect because of Debug Implementation 

	println!("area : {}", rect2.area());
}
```