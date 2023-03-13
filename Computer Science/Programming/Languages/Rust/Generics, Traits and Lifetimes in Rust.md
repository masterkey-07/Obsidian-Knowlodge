# Generics 
### Rust define the specific types in compile time. 

```Rust
struct Point<T, U> {
	x: T,
	y: U, 
}

fn function<T>(list: &[T]) -> &T { /* code... */ }
``` 

# Traits

``` Rust
pub trait Trait { 
	fn to_implement_function(&self) -> String; 
	
	fn default_function(&self) -> String { 
		// code...
	}
}
```

# Lifetimes