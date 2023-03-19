# Debug Annotations

```Rust
#[derive(Debug)] // -> Make the struct printable
struct MyStruct {
// code...
}
```

# Test Annotations

```Rust
#[cfg(test)]
mod tests {
	#[test] // define this functions as a test
	#[ignore] // ignore this function 
	fn test_this() {
		// code...
	}
}
```