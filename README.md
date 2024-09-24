# builtin-greyscript (bltings)
Adds more functions into [greyscript](https://codedocs.ghtools.xyz/) from [Grey Hack](https://store.steampowered.com/app/605230/Grey_Hack/) to utilize in scripts.
<br />
<br />
​<br />
## Installation
1. Choose whether or not you wish to have **logs** with said functions or just the functions barebones in [scripts](https://github.com/irtsa-dev/builtin-greyscript/tree/main/builtint-greyscript).
2. Open **CodeEditor.exe** in the game **Grey Hack** and copy+paste the contents of the `.src` file you have chosen in the previous step.
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

Then, later on you may utilize:
```js
max(Values)
maximum(Values)
// Expectes type(s) 'list', 'map' for 'Values'
// If list is passed, will return the biggest value found in list.
// If map is passed, will print out the key associated with the biggest value found in map.


min(Values)
minimum(Values)
// Expectes type(s) 'list', 'map' for 'Values'
// If list is passed, will return the smallest value found in list.
// If map is passed, will print out the key associated with the smallest value found in map.


removeItem(Values, item)
remi(Values, item)
remItem(Values, item)
// Expects type(s) 'list' for Values | any for item
// Will remove the first instance of the specified item from the provided list.
// Will return a list with the first instance of said item removed.


removeAllItems(Values, item)
remItems(Values, item)
remAllItem(Values, item)
// Expects type(s) 'list' for Values | any for item
// Will remove all instances of the specified item from the provided list.
// Will return a list with all instances said item removed.


count(Values, item)
// Expects type(s) 'list', 'map' for Values | any for item
// If list is passed, will return how many times the item appears in given list.
// If map is passed, will return the length of the value associated with the item as the key for map.


removeDuplicates(Values)
remDups(Values)
remDuplicates(Values)
// Expects type(s) 'list' for Values
// Will return a list with all duplicate values removed.


mean(Values)
average(Values)
// Expects type(s) 'list' for Values
// Will return the mean/average of the provided list (may not behave as expected for lists containing non-numbers).


median(Values)
middle(Values)
// Expects type(s) 'list' for Values
// Will return the median/middle of the provided list when sorted (may not behave as expected for lists containing non-numbers).


mode(Values)
most(Values)
// Expects type(s) 'list' for Values
// Will return the mode/most (most common item) of the provided list.


factors(number)
// Expects type(s) 'number', 'string(number)' for number
// Will return a list of factors of the given number.


greatestCommonFactor(Values)
GCF(Values)
// Expects type(s) 'list' for Values
// Will return the greatest common factor of the Values in given list (may not behave as expected for lists containing non-numbers).


decimalToPercent(number)
DTP(number)
// Expects type(s) 'number', 'string(number)' for number
// Will return the percentage form of given number (assuming decimal).


percentToDecimal(number)
PTD(number)
// Expects type(s) 'number', 'string(number)' for number
// Will return the decimal form of the given number (assuming percentage).


percentToMultiplier(number)
PTM(number)
// Expects type(s) 'number', 'string(number)' for number
// Will return the multiplier form of the given number (assuming percentage).



multiplierToPercent(number)
MTP(number)
// Expects type(s) 'number', 'string(number)' for number
// Will return the percentage form of the given number (assuming multiplier).


decimalToFraction(number)
DTF(number)
// Expects type(s) 'number', 'string(number)' for number
// Will return the fraction form of the given number (assuming decimal).


baseConvert(number, base)
// Expects type(s) 'number', 'string(number)' for number
// Expects type(s) 'number', 'string(number)' for base
// Will return (in list for) the number converted to given base.


hex(number)
// Expects type(s) 'number', 'string(number)' for number
// Will return the hexidecimal form of the given number.


bin(number)
// Expects type(s) 'number', 'string(number)' for number
// Will return the binary form of the given number.

oct(number)
// Expects type(s) 'number', 'string(number)' for number
// Will return the octal form of the given number.


capitalize(string)
// Expects type(s) 'string' for string
// Will return given string with first item in the provided string uppercase.


applyFunction(func, Values)
// Expects type(s) 'function' for func | 'list' for Values
// Will apply the given function to all items in the given Values (note one must pass the function with @ infront (applyFunction(@sqrt, lust)).
// This edits the provided list, so reassignment is not needed.


rfill(string, amount, filler)
// Expects type(s) 'string' for string | 'number', 'string(number)' for amount | 'string' for filler
// Will use the filler variable and will pad on the right the string with said filler until the length of said string is equal to the amount variable.


lfill(string, amount, filler)
// Expects type(s) 'string' for string | 'number', 'string(number)' for amount | 'string' for filler
// Will use the filler variable and will pad on the left the string with said filler until the length of said string is equal to the amount variable.


isPrime(number)
// Expects type(s) 'number', 'string(number)' for number
// Will return true or false depending on if the number is a prime number or not.


factorsPrime(number)
factorsp(number)
// Expects type(s) 'number', 'string(number)' for number
// Will return a list of prime factors of the given number.


format(string, Values)
f(string, Values)
// Expects type(s) 'string' for string | 'list' for Values
// Takes a string with '{}' and returns the same string with each instance with a the correspond item in Values, expects equal number of items in Values list and '{}' in the given string.


stringGroup(string, groupsize)
// Expects type(s) 'string' for string | 'number' for groupsize
// Will return a list of the given string "chopped" up into groups with lengths equal to groupsize (the last item may not be said length if the length of the string is not a multiple of the groupsize).
```
​
<br />
<br />
### Additional Notes
- Additional functions may be added later on.
- Functions may be changed if changing the functionality of function is requested.
