Go's for-range loop has two form of syntax and two different semantics 
value semantics and pointer semantics. before sharing details let's first 2 small code snippets 
one form of for-range loop 

```
package main

import "fmt"

func main() {
	fruits := [5]string{"Apple", "Banana", "Orange", "Dates", "Cherry"}

	fmt.Printf("Bfr[%s] : ", fruits[1])

	for i, v := range fruits {
		fruits[1] = "fig"

		if i == 1 {
			fmt.Printf("v[%s]\n", v)
		}
	}
}
```

output
`Bfr[Banana] : v[Banana]`

let's explain what this code does,
first we create an array fruits with array litarel.which is 5 length array with string type. we initialize the array when we create it.

in the next line we just print the 2nd element of the array "Banana"
`fmt.Printf("Bfr[%s] : ", fruits[1])`

after that we loop over the array.
in go there is only one loop for, we range over the frutes array that return 2 thigns `i` which is index then second return value is element of that index. for here it's `v` 

when for loop run for first time, we reassign the first elemetn's value to fig 
`fruits[1] = "fig`  and in the sececon iteration when it meet the if statement we print the value of 1st element of the array 
we see in both cases the value is  `Banana`


let's see another example of for range loop 

```
package main

import "fmt"

func main() {
	fruits := [5]string{"Apple", "Banana", "Orange", "Dates", "Cherry"}

	fmt.Printf("Bfr[%s] : ", fruits[1])

	for i := range fruits {
		fruits[1] = "fig"

		if i == 1 {
			fmt.Printf("v[%s]\n", v)
		}
	}
}
```

output
`Bfr[Banana] : v[fig]`

here in for range loop we only return i the index and the result is change now it's actually change the array 1 index value from Banana to Fig 

big question why 

Go provides two different semantics for iterating over a collection. I can iterate using value semantics or pointer semantics.

value semantics mean every piece of code is working with it's own copy data 

and pointer semantics is we have one copy of data and we share the data 


When using value semantic iteration, two things happen. First, the collection I’m iterating over is copied and I iterate over the copy. In the case of an array, the copy could be expensive since the entire array is copied. 

so in first example 
`for i, v := range fruits {`
this "fruits array are copy of orginal array that's why changes doesn't happen but 
In secend example in pointer semantics  when we don't have copy and get the syntax is only index i , we are iterating over the When using pointer semantic iteration, I iterate over the original collection and I access each element associated with the collection directly.

that's why arra's 1 index is now fig 





