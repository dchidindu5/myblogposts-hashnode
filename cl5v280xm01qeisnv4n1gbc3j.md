## Implementing a time function to generate better random numbers in C++

Random numbers are numbers that occur in a sequence such that two conditions are met: 
1. The values are uniformly distributed over a definite interval or set, and 
2. It is impossible to predict future values based on past or present ones. Random numbers are important in statistical analysis and probability theory.


Random numbers are useful particularly in games and simulations. For example, many board games such as chess and die (one of a pair of dice) are used to determine how many
places a player is to advance.

A die is a cube containing spots on each of its six faces. The number of spots range from one to six. A player tosses a die or sometimes a pair of dice, and the side(s) that face up have meaning in the game being played.
A die or pair of dice are used in other games of chance.
The dots on each face after rolling is determined at random by the complex tossing of the die. A software
adaptation of a game that involves dice would need a way to simulate the random roll of a die.


A conventional C++ program uses two standard C functions for generating pseudorandom numbers,: ```srand``` and ```rand```. To use the standard C random functions in your C++ program, you must include the  ```<cstdlib>``` header file.<br> <br>

**Syntax**
- ```void srand(unsigned)```

- ```int rand()```
<br><br>


```srand ()```

The ```srand()``` function sets the starting point for producing a series of pseudo-random integers. If srand() is not called, the ```rand()``` seed is set as if ```srand(1)``` were called at program start. Any other value for seed sets the generator to a different starting point.

```rand ()```

The ```rand()``` function is used in C/C++ to generate random numbers in the range (0, RAND_MAX). 
Each call to rand returns the next value in the sequence of pseudorandom values.

```
//Simple Random number
#include <iostream>
#include <cstdlib>
#include <windows.h>

int main(){
	system("color 0B");
	srand(20);
	for(int i=0; i<15; i++){
		int r = rand();
		std::cout<< r << " ";
		
	}
	std::cout << '\n';
}
```


![simpleRandom.JPG](https://cdn.hashnode.com/res/hashnode/image/upload/v1658162452007/CCjxpDTlt.JPG align="left")
**Figure 1**<br>
The code snippet shows how a sequence of 15 pseudorandom numbers that will be printed as described in the for loop.

```srand(20)``` - Sets the random seed value to 20.

```for (int i = 0; i < 15; i++)```- Random number in the range of 1 to 15.

```int r = rand();```- Generate the sequence of pseudorandom values.


The numbers printed by the program appear to be random. The algorithm is given a seed value to begin,
and a formula is used to produce the next value. The seed value determines the sequence of numbers generated;

![randomImage.JPG](https://cdn.hashnode.com/res/hashnode/image/upload/v1658163587772/x0yA5zWfV.JPG align="left")
**Figure 2**<br>

> N/B: Identical seed values generate identical sequences. If you run the program again, the same sequence is
> displayed because the same seed value, 20 is used. In order to allow each program run to display different sequences, the seed value must be different for each run.

### Using time function for generating better numbers.
How can we implement a different seed value for each run? The best way to make up a “random” seed at run time is to use the time function which is found in the ```ctime``` library.
The call time(0) returns the number of seconds since midnight January 1, 1970.
To achieve that the program employs the use of ```#include <ctime>``` in its header.

The program below incorporates the time function to improve its randomness over multiple executions.

### Code Snippet 
```
#include <iostream>
#include <ctime>// Library that contains the time function
#include <cstdlib> // library that contains the random value.
#include <windows.h>

int main(){
	system("color 0D");
	srand(static_cast<unsigned>(time(0)) );
	int i = 0;
	while(i < 15){
		int r = rand();
		std::cout<< r << " ";
		i++;
	}
	std::cout<<'\n';
}
```
Notice that the function ```srand(static_cast<unsigned>(time(0)))``` produces a different pseudorandom number sequence for each execution. That means it uses a different seed value, and the
generated pseudorandom number sequences will be different.

The following results shows three different execution done that produces different random sequences.

![1ex.JPG](https://cdn.hashnode.com/res/hashnode/image/upload/v1658405491836/HQhQJwaie.JPG align="left")
first execution

![2ex.JPG](https://cdn.hashnode.com/res/hashnode/image/upload/v1658405501753/ynGjSTnEg.JPG align="left")
second execution
![3ex.JPG](https://cdn.hashnode.com/res/hashnode/image/upload/v1658405515474/p0oxyh_5J.JPG align="left")
Third execution


The actual type of value that ```time``` returns is ```time_t```, so the result from a call to time must
be cast to unsigned int before being used with srand.
Notice that the numbers returned by rand can be rather large. The pseudorandom values range from 0
to a maximum value that is implementation dependent and the maximum value for Visual C++´s rand function is 32,767, which corresponds to the largest 16-bit signed int value. 
The ```cstdlib``` header defines the constant RAND_MAX that represents the largest value in the range. 

The following statement
```
std::cout << RAND_MAX << '\n';``` would print the value of RAND_MAX for a particular system.

### Sources

1. https://cplusplus.com/reference/cstdlib/rand/
2. https://www.geeksforgeeks.org/rand-and-srand-in-ccpp/
3. https://www.techtarget.com/whatis/definition/random-numbers
