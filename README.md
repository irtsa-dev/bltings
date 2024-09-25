# builtin-greyscript (bltings)
Adds more functions into [greyscript](https://codedocs.ghtools.xyz/) from [Grey Hack](https://store.steampowered.com/app/605230/Grey_Hack/) to utilize in scripts.
<br />
<br />
​<br />
## Installation
1. Copy the code from the **bltings.src** file found [here](https://github.com/irtsa-dev/builtin-greyscript/tree/main/builtint-greyscript).
2. Open **CodeEditor.exe** in the game **Grey Hack** and paste the contents of the `bltings.src` file you copied.
3. Build the code and save binary file naming it whatever you wish (or do `bltings`). Make sure to check **Allow import**.
4. Save to a path you will remember (or save it to `/bin`).
<br />
<br />
<br />
<br />
<br />
<br />

## Usage
To import:
```lua
import_code("/bin/bltings")
```
Or if you didnt save as recommended:
```lua
import_code("<path-to-file>")
```
<br />

Then, later on you may utilize the functions:
<br />
<br />

New Map Functions
```js
max()
// Will return the key that has the longest value.
// Example: {"a" : 123, "b": 1}.max   [returns "a"]

min()
// Will return the key that has the shortest value.
// Example: {"a" : 123, "b": 1}.max   [returns "b"]
```
<br />

New List Functions
```js
max()
// Will return the largest value in the list.
// Example: [1, 3, 8, 5, 1, 5, 0].max   [returns 5]

min()
// Will return the smallest value in the list.
// Example: [1, 3, 8, 5, 1, 5, 0].max   [returns 0]

maxIndex()
// Will return the index of the largest value in the list.
// Example: [1, 3, 8, 5, 1, 5, 0].maxIndex   [returns 2]

minIndex()
// Will return the index of the largest value in the list.
// Example: [1, 3, 8, 5, 1, 5, 0].maxIndex   [returns 6]

delete(item)
// Will delete the first instance of the given 'item' from list and will also return said list.
// Example: [1, 3, 8, 5, 1, 5, 0].delete(3)   [returns [1, 8, 5, 1, 5, 0]]
// Note: Will modify the given list.

deleteAll(item)
// Will delete the all instances of the given 'item' from list and will also return said list.
// Example: [1, 3, 8, 5, 1, 5, 0].delete(1)   [returns [3, 8, 5, 5, 0]]
// Note: Will modify the given list.

set()
// Will delete the all duplicates from list and will also return said list.
// Example: [1, 3, 8, 5, 1, 5, 0].set   [returns [1, 3, 8, 5, 0]]
// Note: Will modify the given list.

count(item)
// Will return how many times the given 'item' appears in said list.
// Example: [1, 3, 8, 5, 1, 5, 0].count(1)   [returns 2]

mean()
// Will return the mean (average) of the said list.
// Example [1, 3, 8, 5, 1, 5, 0].mean   [returns 3.28571...]

median()
// Will return the median (middle of organized list) of the said list.
// Example [1, 3, 8, 5, 1, 5, 0].median   [returns 3]

mode()
// Will return the mode (most occuring) item of the said list.
// Example [1, 3, 8, 5, 1, 5, 0].mode   [returns 1]

applyFunction(func)
// Will apply the given function 'func' onto all items in the given list.
// Example [1.32, 124.234, 423.3, 32.24545].applyFunction(@floor)   [returns [1, 124, 423, 32]]

all()
// Will return true if all values in said list are true.
// Example [true, true, false].all   [returns 0(false)]

any()
// Will return true if at least one values in said list are true.
// Example [true, true, false].any   [returns 1(true)]
```
<br />

New String Functions
```js
capitalize()
// Will capitalize the first letter of said string.
// Exaple "hello!"   [returns "Hello!"]

lfill(amount, filler)
// Will fill space on the left side of the said string using 'filler' until the length of the string is equal to 'amount'.
// Example "hello".lfill(10, " ")   [returns "     hello"]
// Note: 'filler' variable defaults to "0"

rfill(amount, filler)
// Will fill space on the right side of the said string using 'filler' until the length of the string is equal to 'amount'.
// Example "hello".rfill(10, " ")   [returns "hello     "]
// Note: 'filler' variable defaults to "0"

format(Variables)
// Will replace instances of "{}" in said string with items given in 'Variables' in the order of the given 'Variables'.
// Example "Hello {}! Today is {}.".format(["User","Friday"])   [returns "Hello User! Today is Friday."]
// Note: The amount of "{}" in said string and amount of items in 'Variables' should be equal in length.

group(groupsize)
// Will split the string into a list comprising of substrings of sizes equal to 'groupsize'.
// Example "Hello! How are you?".group(3)   [returns ["Hel", "lo!", " Ho", "w a", "re ", "you", "?"]]
```
<br />

New Number Functions
```js
factors()
// Will return a list of the factors of the given 'value'.
// Example: x = 20; x.factors   [returns [1, 2, 4, 5, 10, 20]]

factorsPrime()
// Will return a list of the prime factors of the given 'value'.
// Example: x = 20; x.factorsPrime   [returns [2, 2, 5]]

isPrime()
// Will return true if the given 'value' is prime, false if otherwise (1 or 0).
// Example: x = 7; x.isPrime   [returns 0(false)]

decimalpercent()
// Will convert the decimal 'value' into percentage form assuming 'value' is a decimal.
// Example x = 10; x.decimalpercent   [returns 1000]

percentdecimal()
// Will convert the percentage 'value' into decimal form assuming 'value' is a percentage.
// Example x = 10; x.percentdecimal   [returns 0.1]

percentmultiplier()
// Will convert the percentage 'value' into multiplier form assuming 'value' is a percentage.
// Example x = 10; x.percentmultiplier   [returns 1.1]

multiplierpercent()
// Will convert the multiplier 'value' into percentage form assuming 'value' is a multiplier.
// Example x = 10; x.multiplierpercent   [returns 900]

decimalfraction()
// Will convert the decimal 'value' into fraction form assuming 'value' is a decimal.
// Example x = 0.305; x.decimalfraction   [returns 61/200]
```
<br />

New General Functions
```js
factors(value)
// Will return a list of the factors of the given 'value'.
// Example: factors(20)   [returns [1, 2, 4, 5, 10, 20]]

factorsPrime(value)
// Will return a list of the prime factors of the given 'value'.
// Example: factorsPrime(20)   [returns [2, 2, 5]]

isPrime(value)
// Will return true if the given 'value' is prime, false if otherwise (1 or 0).
// Example: isPrime(7)   [returns 0(false)]

greatestCommonFactor(Values)
// Will return the greatest common factor of the given 'Values'
// Example: greatestCommonFactor([10, 20, 55])   [returns 5]

decimalpercent(value)
// Will convert the decimal 'value' into percentage form assuming 'value' is a decimal.
// Example decimalpercent(10)   [returns 1000]

percentdecimal(value)
// Will convert the percentage 'value' into decimal form assuming 'value' is a percentage.
// Example percentdecimal(10)   [returns 0.1]

percentmultiplier(value)
// Will convert the percentage 'value' into multiplier form assuming 'value' is a percentage.
// Example percentmultiplier(10)   [returns 1.1]

multiplierpercent(value)
// Will convert the multiplier 'value' into percentage form assuming 'value' is a multiplier.
// Example multiplierpercent(10)   [returns 900]

decimalfraction(value)
// Will convert the decimal 'value' into fraction form assuming 'value' is a decimal.
// Example decimalfraction(0.305)   [returns 61/200]

baseConvert(value, base)
// Will convert the 'value' variable assuming base 10 into given 'base' base and will return as list.
// Example baseConvert(100, 7)   [returns [2, 0, 2]]

hex(value)
// Will return the 'value' variable assuming base 10 as hexidecimal, will be a string.
// Example hex(100)   [returns "64"]

bin(value)
// Will return the 'value' variable assuming base 10 as binary, will be a string.
// Example bin(100)   [returns "1100100"]

oct(value)
// Will return the 'value' variable assuming base 10 as octal, will be a string.
// Example oct(100)   [returns "144"]

all(Values)
// Will return true if all values in given list 'Values' are true.
// Example all([true, true, false])   [returns 0(false)]

any(Values)
// Will return true if at least one values in given list 'Values' are true.
// Example any([true, true, false])   [returns 1(true)]

foldercount(folder)
// Will return how many folders are in the given folder 'folder', will return null if folder is not of type 'file'(folder).
// Example folder=get_shell.host_computer.File("/home"); foldercount(folder)   [returns 3]

filecount(folder)
// Will return how many files are in the given folder 'folder', will return null if folder is not of type 'file'(folder).
// Example folder=get_shell.host_computer.File("/etc"); filecount(folder)   [returns 3]

open_ports(router)
// Will return a list of open used ports on the given router 'router'.
// Example open_ports(get_router)   [returns [port, port, port, port]]

closed_ports(router)
// Will return a list of closed used ports on the given router 'router'.
// Example closed_ports(get_router)   [returns [port, port]]

filehash(file)
// Will return the md5 hash of the file contents of the given file 'file'.
// Example filehash(get_shell.host_computer.File("/etc/passwd"))   [returns "e2d0144aa03278f03fb1d50c1c46b7ca"]

folderhash(folder)
// Will return the md5 hash of all child folder and file paths concatenated of the given folder 'folder'.
// Example folderhash(get_shell.host_computer.File("/home"))   [returns "9c746492c2295b799aa637d641b3998a"]
```
​
<br />
<br />
### Additional Notes
- Additional functions may be added later on.
- Functions may be changed if changing the functionality of function is requested.
