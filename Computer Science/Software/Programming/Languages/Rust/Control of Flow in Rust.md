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

^f8afa7

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

# Match

```Rust
match coin {
	Coin::Penny => {
		println!("Lucky penny!");
		1
	} 
	Coin::Nickel => 5,
	Coin::Dime => 10, 
	Coin::Quarter(state) => state, //Quarter is a Enum
	None => None,
	_ => (), // None of the Cases and do Nothing
}
```

# If Let

```Rust
let config_max = Some(3u8);
if let Some(max) = config_max {
	println!("The maximum is configured to be {}", max); 
} else {
	count += 1;
}
```