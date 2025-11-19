2025-11-18 13:09

Status:


Tags:
[[cs]] 
[[cs145]] 
[[uni]] 


_______
# cs145 - Interactive Programs and More Streams

**Interactive:** input + output (simultaneously)

[[cs145 - Data Structures|Char datatype]] → `#\X` 
- *Note* → string is not char (no matter the length)
	- Made by combining char (finite sequence of characters)
- Can convert chars to integers
	- ASCII values (128 characters)
		- Subset of Unicode (300K) characters (written in hexadecimal) 
	- Means you can also compare string sizes `string<?` 
- `read-char` → reads sequence of characters and displays one at a time
- `#<eof>` marks end of input stream (not a character)
	- “End of File“ 
	- `eof-object?` → predicate of eof
- `write-char` → displays given character in a prettier format (inverse of read-char)
	- I.e. displays without `#\` 

`void` → produces nothing 

*Continuation-passing* → style where you embed the recursive call as part of the calculation of the next value (passing on recursive call by nesting it)
- Consumes input, state, output and stores output and then calls next Gen Call
- Output can be multiple values (in a list) or nothing (empty)




# References

