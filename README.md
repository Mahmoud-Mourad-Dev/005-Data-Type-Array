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



















