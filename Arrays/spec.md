# Get
```
[V] — a 1D vector

/get
[V]: a vector, [I]: index
[1] — [V]@[I]
```
# Obverse
```
/obverse
[V]: a vector
[1] — [L]: length of [V]
[^] Establishes upper-bound
[2] — [I]: index = 0
[^] A position index; Allowing us to obversely scan [V]
[3] While [I] < [L]
[^] — As long as [I] is less than [L] do the following 
	[!] — Element `[V]@[I]`
	[^] Log the element at index [I] in [V]
	[1] — [I] += 1
	[^] Advance index for the next iteration
```
<!-- TODO: Generalize obverse to scan forward from any start and any end greater than start -->
# Reverse
<!-- ```
/reverse
[V]: a vector
[1] — [L]: an end point = 0
[^] Establishes lower-bound
[2] — [I]: index = length of [V] - 1
[^] A position index; Allowing us to obversely scan [V]
[3] — While [I] < [L]
[^] — As long as [I] is less than [L] do the following 
	[!] — Element `[V]@[I]`
	[^] Log the element at index [I] in [V]
	[1] — [P] += 1
	[^] Advance [P] for the next iteration
``` -->

# Traverse