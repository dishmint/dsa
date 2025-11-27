# Access
```
/access
[V]: a 1D vector, [I]: index
[1] — [V]@[I]
[^] Access the element in [V] that [I] points to
```
> Accessing an element from a `1D vector` is like having a garage door opener that can target any garage on your street. `[V]`  is the street of houses, `[I]` is the address. Click the opener tuned to address `[I]`, and its contents will be revealed.
> 
> Technically,`[V]` takes up a string of addresses in memory/disk. `[I]` points to one of those addresses. So you're requesting a piece of `[V]`, which one? The piece at `[I]`.

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
	[!] — Element `access[ [V], [I] ]`
	[^] Log the element at index [I] in [V]
	[1] — [I] += 1
	[^] Advance index for the next iteration
```
> An obverse scan is like going down a one-way street. Opening and Closing each house's garage to see what's inside.
>
> Techincally, we're advancing the pointer `[I]` to access the piece at the next address. The `While` loop helps us manage that iteration. Terminating the advancement when `[I]` is equal to `[L]`, the length of the array. 
> 
> An array can start at index 0 or 1, in this case 0. So the first element is at 0, and the last element is at `[L]` - 1. On a street of 5 houses: the first home would be house #0, and the last home would be house #4.
> 
> Since `[I]` is a pointer, and `[L]` establishes the boundary of the pointer, why start at the beginning of the street? Good question, `obverse` can be generalized to start and end anywhere (so long as the `[I]`: *the start*, is less than `[L]`: *the end*).
<!-- TODO: Generalize obverse to scan forward from any start and any end greater than start -->
# Reverse
```
/reverse
[V]: a vector
[1] — [L]: an end point = 0
[^] Establishes lower-bound
[2] — [I]: index = length of [V] - 1
[^] A position index; Allowing us to reversely scan [V]
[3] — While [I] > [L]
[^] — As long as [I] is greater than [L] do the following 
	[!] — Element `access[ [V], [I] ]`
	[^] Log the element at index [I] in [V]
	[1] — [I] -= 1
	[^] Revance [I] for the next iteration
```
> A reverse scan is like going back through the houses just to be sure. This time revancing `[I]`.

# Traverse
```
/traverse
	[V]: a vector
	[F]: Forward end = Length[ [V] ] - 1
	[^] the upper bound
	[B]: Backward end = 0
	[^] the lower bound
	[S]: starting position
	[^] where to start from
	[M]: number of moves (- ~ +)
[1] — move[ [V], [S], [M] ]

/move
	[V]: a vector
	[S]: starting position
	[M]: number of moves
[1] — PositiveQ[ [M] ]
	[T] — obverse[ [V], [S], [M] ]
	[F] — reverse[ [V], [S], [M] ]

/obverse
	[V]: a vector
	[S]: 0 < a starting position < Length[ [V] ]
	[M]: 0 < number of steps to take < +∞
[1] — [L]: an end point = End[ [V] ]
[2] — [S] += [M]
[3] — [S] > [L]
	[T] — [>]: access[ [V], [L] ]
	[F] — [>]: access[ [V], [S] ]

/reverse
	[V]: a vector
	[S]: 0 < a starting position < Length[ [V] ]
	[M]: -∞ < number of steps to take < 0
[1] — [L]: an end point = Start[ [V] ]
[2] — [S] -= [M]
[3] — [S] > [L]
	[T] — [>]: access[ [V], [S] ]
	[F] — [>]: access[ [V], [L] ]
```

> A traverse scan is like moving toward a house on the street, then realizing you need to change direction to a different house.