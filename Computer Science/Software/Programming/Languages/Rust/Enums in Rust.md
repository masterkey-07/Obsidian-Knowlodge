```Rust
enum IpAddr { 
	V4(u8, u8, u8, u8), 
	V6(String), 
} 

struct Ipv4Addr { /* --snip-- */ } 
struct Ipv6Addr { /* --snip-- */ }

enum IpAddr { 
	V4(Ipv4Addr), 
	V6(Ipv6Addr), 
}

impl IpAddr { 
	fn connect(&self) {
		// method body would be defined here 
	} 
}

let home = IpAddr::V4(127, 0, 0, 1); 
let loopback = IpAddr::V6(String::from("::1"));

home.connect();
```