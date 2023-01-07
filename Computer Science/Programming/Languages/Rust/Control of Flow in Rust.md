# If/Else 

^2d7d9f

```Rust
const condition = true;

if condition {
	// code...
} else {
	// code...
}

let another_condition = if condition { true } else { false };
```

# Loop 

```Rust
'counting_up: loop {
	loop {
		break 'counting_up; // this loop breaks the labeled loop
	}

	break 1; // loop returns 1
}
```

# While

```Rust
while condition {
	//code...
}
```

# For

```Rust
let elements = [10, 20, 30, 40, 50];
for element in elements {
	//code...
}
```
