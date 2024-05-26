**Framing or Frame** : Divide Bits into blocks of information, but it is not packages

**Difference between Frame and Package** : Frame is nothing more than little packages

**Framing Methods**
- **Counting** : Counting the bits
	- Can have **Errors**, making confusions an then lose informations.
- **Flags** : Flag the start and end of the frame
	- Has **Headers**, that "maps" the structure of the frame
	- Has **Trailers**, that verify errors and other functions
- **Bit Stuffed** : Make framing at level of bits, filling bits with specific bits for division.


### Finding Errors : is more Cheap

- **Duplicate Deliver**
- **Pairing Bits** : there is a inversion list of bits of the real content for comparing
- **Checksum** : 
	- **Used in** TCP, UPD and IP
	- **Reference** : [Internet Protocol](https://datatracker.ietf.org/doc/html/rfc791)
- Payload + hash(Payload)
- Cyclic Redundancy Checks (CRCs)
	- Used by Ethernet, 802.11

### Fixing Errors : is more Robust

- **Hamming Codes** (Originator)
- **Binary Convolutional Codes**
- **Reed-Solomon Codes**
- **Low-Density Parity Check Codes**

### Internet Protocol Example

![[Pasted image 20230830193828.png|center]]
Low-Density Parity Check Codes
# Drawing

![[Data Link Layer 2023-08-30 19.10.49.excalidraw|center]]