
This Note Include Some Modern Or Special Features In C++

Overview of the content :

- Initialize
- Function
- Object
- Template
- Modern Feature

Reference TextBook:

Effective Modern C++
![](../../_IMG/PL/Snipaste_2024-05-08_19-46-39.png)


The C++ Programming Language (4th Edition)
![](../../_IMG/PL/Snipaste_2024-05-08_19-49-06.png)

# Initialize

## Uniform Initialization

Using C++ Uniform Initialization, we can avoid error or narrow type casting !

Examples For C++ 11 Uniform Initialization
```c++
int data1(10.5);  // Direct Initialization (C++ will don't care about this)

int data2{10};   // Uniform Initialization (There will be a error occured)
```

Uniform Initialization For Class
```c++
class test{
private:
	int INT;
	bool BOOL;
public:
	test(int _int, bool _bool) : INT(_int), BOOL(_bool){
		std::cout<<"test(int _int, bool _bool)"<<std::endl;
	}
}; 
int main(){
	test test1{10, true};
	
	return 0;
}
```
## Structured Binding

In C++ 17 Structured Binding, we can set multiple variables simultaneously !

Example:
```c++
std::tuple<std::string, std::string, std::string> getInfo(){
	std::string name {"Stanford CS 106L"};
	std::string date {"2024-05-08"};
	std::string language{"C++"};
	return {name, date, language};
}
// We can get the result using this way
auto [name, date, language] = getInfo();
```
# Function

This Part of Note Mainly Include Some Function Utility and Advanced Feature

## Function Overload
To overload a function, declare multiple functions with the same name but _differently typed parameters_ or a _different number of parameters_

The Traits which will determine whether a function can be overloaded
- different number of parameters
- different parameters type

> Note : Whether a function can be overloaded is Unrelated with _return type_

Examples :
```c++
double divide(double x, double y){
return x / y;
}
int divide(int x, int y){
return x / y;
}
```

# Object


# Template


# Modern Feature