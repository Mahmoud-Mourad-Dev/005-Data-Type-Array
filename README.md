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
contract MultiDimensionalFixedArray {
    // Define a 2x3 fixed-size array
    uint[][] public fixedArray;
    uint[][] ipadAirPrice; 
}
```
Multi dimensional mixed siza array

```solidity
//SPDX-License-Identifier:MIT
pragma solidity ^0.8.0;
contract MultiDimensionalFixedArray {
    // Define a 2x3 fixed-size array
    uint[][5] public fixedArray;
    uint[1][] ipadAirPrice; 
}
```





