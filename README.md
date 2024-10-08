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
`There is no need to manually cast string literals when assigning them to a string array in Solidity. The Solidity compiler correctly infers that all elements in the array are of type string, regardless of their length.
I appreciate your patience, and I'm glad you brought this to my attention so I could clarify the correct behavior.``

```solidity
//SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.1 <0.9.0;
contract myArray{
string[][]ipadAirPrice=[[("pro")],[("air")]];
}
```

Array Members
- Push
   Adds an element to the end of the array. For dynamic arrays only.
  You can’t push to a fixed size array because it has been fixed already, and memory has already been allocated to it. If you want to push, you need to use dynamic arrays. Dynamic arrays have no fixed 
  size, can contain numbers, and keep growing.


```solidity
  // SPDX-License-Identifier: GPL-3.0
pragma solidity ^0.8.1;
contract myArray{
uint[] public ipadProPrice=[1000,1100,1200,1300,1400,1500];
string [] public appleProduct=["ipad","macbook","iphone"];

function addToPrice(uint addIpadPrice) public{
ipadProPrice.push(addIpadPrice);
}
function addToAplle(string memory newAplleProduct) public{
appleProduct.push(newAplleProduct);
}
function addToPrice() public{
ipadProPrice.push()=5;
}
function addToAplle() public{
appleProduct.push()="ipadAir";
}
}
```
Length
Length Arrays have length member that contains that elements

```solidity
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.1 <0.9.0;
contract myArray{
uint[] public ipadProPrice=[1000,1100,1200,1300,1400,1500];
string [] public appleProduct=["ipad","macbook","iphone"];
function getLength() public view returns(uint){
    return ipadProPrice.length;
}
function getLengthS() public view returns(uint){
    return appleProduct.length;
}
}
```
- Pop
  pop() items can be removed from the array using pop method which remove the last index and adjust the length pop method in dynamic array only
```solidity
  // SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.1 <0.9.0;
contract myArray{
uint[] public ipadProPrice=[1000,1100,1200,1300,1400,1500];
string [] public appleProduct=["ipad","macbook","iphone"];
function getLength() public view returns(uint){
return ipadProPrice.length;
}
function getLengthS() public view returns(uint){
return appleProduct.length;
}
function popMethod() public{
ipadProPrice.pop();
appleProduct.pop();
}
}
```
-Delete
Delete member not delete the index (index to zero)
```solidity
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.1 <0.9.0;
contract myArray{
uint[] public ipadProPrice=[1000,1100,1200,1300,1400,1500];
string [] public appleProduct=["ipad","macbook","iphone"];
function deleteMethod() public {
delete ipadProPrice[1];
}
}
```
Access elements in array
```solidity
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.1 <0.9.0;
contract myArray{
uint[]  ipadProPrice=[1000,1100,1200,1300,1400,1500];
string []  appleProduct=["ipad","macbook","iphone"];
uint public accessElement=ipadProPrice[5];
string public accessElementS=appleProduct[1];
}
```
```solidity
/ SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.1 <0.9.0;
contract myArray{
uint[]  ipadProPrice=[1000,1100,1200,1300,1400,1500];
string []  appleProduct=["ipad","macbook","iphone"];
function getIpadPrice() public view returns(uint){
return ipadProPrice[2];
}
function getAppleProduct() public view returns( string memory){
return appleProduct[1];
}
}
```
Access elements in multi dimensional array
```solidity
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.1 <0.9.0;
contract myArray{
uint [][] ipadPriceRam =[[uint(1000),1200,1300],[uint(8),16,32]];
string [][] appleProduct=[["ipad","macbook","iphone"],["airpod","typec","headphone"]];
function getIpadPriceRam() public view returns(uint){
return ipadPriceRam[1][2];
}
function appleProductAccess() public view returns(string memory){
return appleProduct[1][0];
}
function accessTwoArray() public view returns(uint,uint){
return(ipadPriceRam[0][0],ipadPriceRam[1][0]);
}
}
```
Special array bytes
Variables of type bytes and string are special arrays. The bytes type is similar to bytes1[], but it is packed tightly in calldata and memory. string is equal to bytes but does not allow length or index access
```solidity
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.1 <0.9.0;
contract specialArray{
    //any nunmber of bytes
bytes public appleProduct= "ipad";
    // four bytes only
bytes4 public newApple="ipad"; 
//upto 32 bytes
bytes32 public name="mahmoud ibrahim elsayed"; 
    // index in array
function access() public view returns(bytes1){ 
return appleProduct[1];
}
    // get length
function getLength() public view returns(uint){ 
return appleProduct.length;
}

function popArray()public{
return appleProduct.pop();
}
}
```
String dont have length property ,it should be converted in to bytes
String to bytes
```solidity
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.1 <0.9.0;
contract stringArray {
string apple="ipadPro";
/*function getLength() public view returns(uint){ 
return apple.length;}*/
bytes stringToBytes=bytes(apple);
function getLength() public view returns(uint){ //error
return stringToBytes.length;
}
}
```
Compare two string
```solidity
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.1 <0.9.0;
contract stringCompare {
function compareString(string memory _firstName) public pure returns(bool) {
if(keccak256(abi.encodePacked(_firstName))==keccak256(abi.encodePacked("mourad"))){
return true;
}else{
return false;
}
}
}
```
Function output array
```solidity
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.1 <0.9.0;
contract arrayOutput {
uint [] ipadPrice=[1000,2000,3000];
function outputArray()public view returns(uint[] memory){
return ipadPrice;
}
}
```
How to get the largest element in an array — Solidity?
```solidity
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.1 <0.9.0;
contract arrayOutput {
uint [] ipadPrice=[1100,1200,1300,1400,1500];
function getMaxPric() public view returns(uint){
uint i;
uint maxPrice=0;
for(i=0;i<5;i++){
if(maxPrice<ipadPrice[i]){
maxPrice=ipadPrice[i];
}
}
return maxPrice;
}
}
```
Multidimensional arrays in solidity and mapping
```solidity
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.0 <0.9.0;
contract arrayMapping{
mapping(address => string[][])  getInfo;
function addNameJop(string memory name, string memory jop) public{
getInfo[msg.sender].push([name, jop]);
}
function getNameJop() public view returns(string [][] memory){
return getInfo[msg.sender];
}
}
```
Array example contract to check the price in array
```solidity
//SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.0 <0.9.0;
contract ipadPrice{
uint256 [] ipadPriceInShop=[1000,2000,5000,4000,6000,10001,3000,250000];
function checkIpadPrice(uint thePrice) public view returns(bool){
bool trueprice = false;
for(uint i=0;i<7;i++){
if(ipadPriceInShop[i]== thePrice){
trueprice=true;
}
}
return trueprice;
}
}
```
Array example check true name -Compare two string
```solidity
//SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.0 <0.9.0;
contract forLoopTest{
string[] className=["ahmed","mourad","mahmoud","hamza"];
function findclassName(string memory checkName) public view returns (bool){
bool isCheckNamecorrect=false;
for(uint i=0;i<4;i++){
if(keccak256(abi.encodePacked(className[i]))==keccak256(abi.encodePacked(checkName))){
isCheckNamecorrect=true;  
        }
}
return isCheckNamecorrect;
}
}
```
In Solidity, array elements can be of any type, including complex types like mappings or structs. However, there are some restrictions you need to be aware of when working with these types, especially in relation to storage locations and publicly-visible functions
```solidity
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.1 <0.9.0;
contract stringArray {
struct Person {
    string name;
    uint age;
}

Person[] public people;  // Dynamic array of structs
}
```
It is possible to mark state variable arrays public and have Solidity create a getter. The numeric index becomes a required parameter for the getter.
When you declare an array as public, Solidity generates a getter function for that array. The getter will not return the entire array but rather allow you to access individual elements by providing an index.
```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract ArrayGetterExample {
    // Declare a public dynamic array of uint
    uint[] public numbers;

    // Constructor to initialize the array with some values
    constructor() {
        numbers.push(10);  // numbers[0] = 10
        numbers.push(20);  // numbers[1] = 20
        numbers.push(30);  // numbers[2] = 30
    }

    // Solidity automatically creates this getter:
    // function numbers(uint index) public view returns (uint) {
    //     return numbers[index];
    // }
}
```
In Solidity, accessing an array element past its end (i.e., using an index that is out of bounds) causes a failing assertion and reverts the transaction. Solidity checks array bounds at runtime, and trying to access an invalid index will lead to an exception.

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract Array {
    uint[] public numbers ;
function getElement(uint index) public view returns (uint) {
    return numbers[index];  // Fails if index >= numbers.length
}
}
```
Note
Dynamically-sized arrays can only be resized in storage. In memory, such arrays can be of arbitrary size but the size cannot be changed once an array is allocated.
```solidity


//SPDX-License-Identifier:MIT
pragma solidity ^0.8.25;
contract dynamicArrayResized{
    uint[]numbers;

    function addNumber(uint _numbers) public {        
        numbers.push(_numbers);
    }


    function getLength() public view returns(uint){
        return numbers.length;
    }
}
```
```solidity
pragma solidity ^0.8.0;

contract DynamicArrayExample {
    function processArray() public pure {
        // Dynamically-sized array in memory
        uint[] memory dynamicArray = new uint[](3); // Allocate memory for 3 elements
        dynamicArray[0] = 10;
        dynamicArray[1] = 20;
        dynamicArray[2] = 30;

        // You can work with the dynamically-sized array in memory
        // But you cannot resize it once allocated
    }
}
```
-Concatenate
In Solidity, you can concatenate multiple string values using the string.concat function. This function returns a single string that contains the combined content of all the arguments provided, without adding any extra padding.

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;
contract Concatenate {
    string  public result =string.concat("hello", " mourad");
}
```
```solidity
// SPDX-License-Identifier: GPL-3.0
pragma solidity ^0.8.12;

contract C {
    function concatString(string memory firstName, string memory lastName) public pure returns(string memory){
        return string.concat(firstName,"",lastName);
    }
}
```
```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;
contract Concatenate {
    bytes  public result =bytes.concat("hello", " mourad");
}

```
```solidity
// SPDX-License-Identifier: GPL-3.0
pragma solidity ^0.8.12;

contract C {
    string s = "Storage";  // A storage string initialized with "Storage"

    // Public function f takes three arguments:
    // - bytes calldata bc: a byte array passed as calldata
    // - string memory sm: a string passed as memory
    // - bytes16 b: a fixed-size byte array (16 bytes)
    function f(bytes calldata bc, string memory sm, bytes16 b) public view {
        // Concatenating the storage string `s`, the byte array `bc` converted to a string, 
        // the string literal "Literal", and the memory string `sm`.
        string memory concatString = string.concat(s, string(bc), "Literal", sm);
        
        // Asserting that the length of the concatenated string is equal to the sum of:
        // - length of the storage string `s`
        // - length of the byte array `bc`
        // - length of the string literal "Literal" (which is 7)
        // - length of the memory string `sm`
        assert((bytes(s).length + bc.length + 7 + bytes(sm).length) == bytes(concatString).length);

        // Concatenating different bytes arrays:
        // - bytes(s): the storage string converted to bytes
        // - bc: the entire byte array passed as calldata
        // - bc[:2]: slicing the first two bytes of the byte array `bc`
        // - the string literal "Literal" converted to bytes
        // - the memory string `sm` converted to bytes
        // - the fixed-size byte array `b`
        bytes memory concatBytes = bytes.concat(bytes(s), bc, bc[:2], "Literal", bytes(sm), b);
        
        // Asserting that the length of the concatenated bytes array is equal to the sum of:
        // - length of the storage string `s`
        // - length of the byte array `bc`
        // - length of the first two bytes of `bc` (2 bytes)
        // - length of the string literal "Literal" (7 bytes)
        // - length of the memory string `sm`
        // - length of the fixed-size byte array `b` (which is always 16 bytes, since it's bytes16)
        assert((bytes(s).length + bc.length + 2 + 7 + bytes(sm).length + b.length) == concatBytes.length);
    }
}
```
Allocating Memory Arrays
In Solidity, memory arrays are temporary data structures that only exist during the execution of a function. When a memory array is allocated, it is initialized with a specific size, and its size cannot be changed after allocation.
to allocate a memory array, use the new keyword and specify the size of the array in square brackets [].
Size is Fixed: Memory arrays have a fixed size once allocated and cannot be resized during execution.
Temporary: Memory arrays are only available during the execution of a function and are deallocated afterward.
Default Values: When a memory array is allocated, each element is initialized to the default value for its type (0 for uint, false for bool, etc.).
```solidity

/ SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.4.16 <0.9.0;

contract C {
    function f(uint len) public pure {
        uint[] memory a = new uint[](7);
        bytes memory b = new bytes(len);
        assert(a.length == 7);
        assert(b.length == len);
        a[6] = 8;
// a[10] = 8 ; error when deploy
    }
}
```
In Solidity, errors like out-of-bounds array access only occur at runtime, not at compile time. This means that when the code is executed, Solidity checks whether the index used to access the array is within the bounds of the array.

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract MemoryArrayExample {
    
    // Function that allocates and initializes a memory array
    function createMemoryArray(uint size) public pure returns (uint[] memory) {
        // Allocate a memory array of uint with the specified size
        uint[] memory memoryArray = new uint[](size);
        
        // Initialize the array elements
        for (uint i = 0; i < size; i++) {
            memoryArray[i] = i + 1;  // Initialize each element with i+1
        }
        
        // Return the memory array
        return memoryArray;
    }
}
```

The array literal [1, -1] is invalid because the type of the first expression is uint8 while the type of the second is int8 and they cannot be implicitly converted to each other. To make it work, you can use [int8(1), -1]
```solidity
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.4.16 <0.9.0;
contract C {
    int[] a = [int(1),2];
    int[] b = [int8(1),-2];
    uint[] c = [1,2];  
}
```
n Solidity, fixed-size memory arrays cannot be directly assigned to dynamically-sized memory arrays due to their differing nature. Fixed-size arrays have a predetermined length, while dynamically-sized arrays can change in size during execution. Therefore, Solidity doesn't allow direct assignment between these types.

```solidity
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.4.16 <0.9.0;

contract C {
    function invalidAssignment() public pure {
        uint[3] memory fixedArray = [uint(1), uint(2), uint(3)];
        uint[] memory dynamicArray = fixedArray;  // This is not allowed
    }
}
```
You can use a loop to copy the elements from a fixed-size array to a dynamically-sized array like this:
```solidity
 //SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.4.16 <0.9.0;

contract C {
    function copyArray() public pure returns (uint[] memory) {
        uint[3] memory fixedArray = [uint(1), uint(2), uint(3)];
        uint[] memory dynamicArray = new uint[](fixedArray.length);  // Create a dynamic array

        // Manually copy the elements
        for (uint i = 0; i < fixedArray.length; i++) {
            dynamicArray[i] = fixedArray[i];
        }

        return dynamicArray;
    }
}
```
If you want to initialize dynamically-sized arrays, you have to assign the individual elements:
```solidity

// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.4.16 <0.9.0;

contract C {
    function f() public pure {
        uint[] memory x = new uint[](3);
        x[0] = 1;
        x[1] = 3;
        x[2] = 4;
    }
}
```















