- variable is the heart of the language.

- most important thing as a software developer is the idea of type.

Slices
স্লাইস হলো ডাইনামিক এরে। স্লাইছ আসলে কোন ডাটা নিজে contain করে না । 

as we know slice is dynamic array. we can grow the capacity of a slice. 
when we try to add a new value in a slice, greather then it's original length and capacity 
the golang create a new array under the hood, copying existing element and and it's length 

- slice doesn't copy the array 
- slice refference the array 

so the array will be remian in memory. that will create a probl


- The zero value of a slice is nil.
A nil slice has a length and capacity of 0 and has no underlying array.


- blank identifier `_`


method 
when a function retun a function this is method 
`func (v Vertex) Abs() float64 {`
	`return math.Sqrt(v.X*v.X + v.Y*v.Y)`
`}`
here Abs() is method 

? method ki only dyped datar hoy ?
like struc or type 
