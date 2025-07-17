# Get
```
/get
[V]: a 1D vector, [I]: index
[1] — [V]@[I]
```
> Getting an element from a `1D vector` is like having a garage door opener that can target any garage on your street. `[V]`  is the street of houses, `[I]` is the address. Click the opener tuned to address `[I]`, and its contents will be revealed.
# Obverse
```
/obverse
[V]: a 1D vector
[1] — [L]: length of [V]
[^] Establishes a forward-bound
[2] — [I]: index = 0
[^] A position index; Allowing us to obversely scan [V]
[3] While [I] < [L]
[^] — As long as [I] is less than [L] do the following 
	[!] — Element `[V]@[I]`
	[^] Log the element at index [I] in [V]
	[1] — [I] += 1
	[^] Advance index for the next iteration
```
> An obverse scan is like going down a one-way street. Opening and Closing each house's garage to see what's inside. You might be asking, why start at the beginning of the street? Good question, because obverse can be generalized to start and end anywhere (so long as the start is less than the end)
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