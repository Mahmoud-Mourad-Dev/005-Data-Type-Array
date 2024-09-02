# Array
In Solidity, arrays are used to store collections of elements of the same type. There are two types of arrays in Solidity:
Fixed-size arrays: Arrays with a predefined length.
Dynamic arrays: Arrays that can change in size (grow or shrink).
```solidity
//SPDX-License-Identifier:MIT
pragma solidity ^0.8.0;
contract FixedArray {
    // Fixed-size array of 5 unsigned integers
    uint[5] public numbers = [1, 2, 3, 4, 5];
    //one dimensional fixed size array
    uint[2] ipadProPrice=[1500,2000]; 

}
```
Dynamic Array
```solidity

//SPDX-License-Identifier:MIT
pragma solidity ^0.8.0;
contract DynamicArray {
    // Dynamic array of unsigned integers
    uint[] public numbers;
    //one dimensional dynamic array
    uint[] macProPrice=[2000,2500,3000]; 

}
```
Multi dimensional fixed-size array

```solidity
//SPDX-License-Identifier:MIT
pragma solidity ^0.8.0;
contract MultiDimensionalFixedArray {
    // Define a 2x3 fixed-size array
    uint[2][3] public fixedArray;
    uint[2][2] ipadAirPrice; 
}
```
Multi dimensional dynamic array

```solidity
//SPDX-License-Identifier:MIT
pragma solidity ^0.8.0;
contract MultiDimensionalDynamicArray {
    // Define a 2x3 fixed-size array
    uint[][] public fixedArray;
    uint[][] ipadAirPrice; 
}
```
Multi dimensional mixed siza array

```solidity
//SPDX-License-Identifier:MIT
pragma solidity ^0.8.0;
contract MultiDimensionalMixedArray {
    // Define a 2x3 fixed-size array
    uint[][5] public fixedArray;
    uint[1][] ipadAirPrice; 
}
```
Four multi dimensional dynamic array upto15

```solidity
//SPDX-License-Identifier:MIT
pragma solidity ^0.8.0;
contract MultiDimensionalArray {
   // four multi dimensional dynamic array upto15
    uint[][][][] public fixedArray;
}
```
Summery
```solidity

//SPDX-License-Identifier:MIT
pragma solidity >=0.7.1 <0.9.0;
contract myarray{
uint[6] ipadPrice=[1000,2000,3000,4000,5000,1000];
  // fixed size integer array with 6 elements
uint[]  macPrice=[1100,2100,3100]; 
// dynamic array
uint[2] ipadProPrice=[1500,2000]; 
//one dimensional fixed size array
uint[] macProPrice=[2000,2500,3000]; 
//one dimensional dynamic array
uint[2][2] ipadAirPrice; 
// multi dimensional fixed-size array
uint[][] ipad8Price; 
//multi dimensional dynamic array
uint[2][] iphone8Price; 
// multi dimensional mixed siza array
uint[][2] iphone11Price;
 // multi dimensional mixed siza array
uint[][][][] macBook; 
// four multi dimensional dynamic array upto15
string[] macbook2; 
// array of string
bool[] macbook3; 
// array of bool
}
```
Array have to same type
```solidity
//SPDX-License-Identifier:MIT
pragma solidity >=0.7.1 <0.9.0;
contract myArray{
uint[] error1=[1,true,"ahmed"];
//Unable to deduce common type for array elements
}
```
Add value to dimensional array
you need to manually cast the elements of the array to a common type, ensuring that all elements share the same data type. This is required because Solidity, at least as of now, is not smart enough to automatically infer a common type for all elements of a mixed array.
For instance, if you attempt to create a multi-dimensional array with both small and large numbers, Solidity will automatically infer types like uint8 for smaller numbers (e.g., 8, 4) and uint16 for larger numbers (e.g., 1200, 1400). Since uint8 and uint16 are not directly compatible, the Solidity compiler will throw a type mismatch error.
```solidity
/SPDX-License-Identifier:MIT
pragma solidity >=0.7.1 <0.9.0;
contract myArray{
uint[][]ipadAirPrice=[[uint(1200),1400,1600,1800],[uint(8),6,8,4]];
}
```
```solidity
//SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.1 <0.9.0;
contract myArray{
uint[][]ipadAirPrice=[[3001],[300]];
}
```
```solidity
//SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.1 <0.9.0;
contract myArray{
string[][]ipadAirPrice=[[string("pro")],[string("air")]];
}
```
```solidity
//SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.1 <0.9.0;
contract myArray{
string[][]ipadAirPrice=[[("pro")],[("air")]];
}
```






