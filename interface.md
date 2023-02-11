interface is collection of method that some type must have those method 

for say 
```
type student interface {
	study()
	attendInExam()
}
```

i declare a interface `student` that hast must method `study()` 

now let's declare a struct type 

```
type Studentds struct {
	stu string
}
```

now we can implement interface to this struc's method 

```
	func (s Studentds) study string {
		return "stuyding"
	}
```





