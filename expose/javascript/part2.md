1. At line 12 it will encounter the line of code `console.log(i);` and will print out `3`. This is because `var i` inside the `for` loop is function-scoped, and after looping through the three items in `prices` array, `i` ends up as `3` which is the length of array `prices`.
2. At line 13 it will run through the code `console.log(discountedPrice)` and prints `150`. This is because `discountedPrice` was declared with variable `var` inside the `for` loop, it scoped to the whole function rather than just the loop. The final value is the last item in the prices array being calculated after the processing of the three prices, which is `300 x 0.5 = 150`. Hence the result out printed `150`.
3. At line 14, it will run through `console.log(finalPrice)` and also prints out `150`. Since `finalPrice` was declared with variable `var` at the top of the function, even after the `for` loop is over, `finalPrice` remains in scope. `console.log(finalPrice)` will then outputs `150` as the value it contains is after the last item in the list `300 x 0.5 = 150`. And the function will replace it with the most recent rounded discounted price each time we go through the loop.
4. This function will return the array `[50, 100, 150]` after the iteration through the loop. We start with the prices array `[100, 200, 300]` and the discount `0.5` before the loop. Within the loop, each of the price is multipled by `1 - 0.5 = 0.5` thus giving the array `[50, 100, 150]` after we rounded them and push into the `discounted` array and return it at the end. However such returned value is not being printed out as we never have a call for `console.log()` function that will print the output array. Thus nothing ever gets printed, but the return array should be `[50, 100, 150]`.
5. At line 12 it will encounter `console.log(i)` and out prints the error `ReferenceError: i is not defined`. This is because `i` was declared with `let` inside the `for` loop. Block-scoped `let` variables will not exist once exit out of the loop, hence there is no `i` value to log outside the loop.
6.  At line 13 it will encounter `console.log(discountedPrice)` where we will get the error `ReferenceError: discountedPrice is not defined`. This will be the same reason as question 5, it is because `discountedPrice` was declared with `let` variable inside the `for` loop statement. The `let` variable are block-scoped meaning it only exists within each loop interation. Therefore outside of the loop, there will be no `discountedPrice` to reference.
7.  At line 14 it runs through `console.log(finalPrice)` and prints `150`. This is because `finalPrice` was being declared with `let` variable that are outside the loop, so it will still exist after the loop iterations. By the end of the loop, the value was being set to the last discounted price and rounded to `150`.
8.  The function will return the array `[50, 100, 150]`. As we start with the prices array that contains `[100, 200, 300]` and the discount of `0.5`. In the `for` loop we calculate each discounted price with `price x (1 - discount)` and round the value so it stay as whole numbers, then push it into the `discounted` array. After the process of all item in the array, it will return array `[50, 100, 150]`. But it would not be shown as we never print the return value out with the call `console.log()` and therefore nothing is sent to the console but function should return `[50, 100, 150]`.
9.  At line 11 it will run through `console.log(i)` and throws an error `ReferenceError: i is not defined`. This is because `i` value was declared with `let` variable inside the `for` loop. The block-scoped `let` variables only exist within the loop statement, so when the function reach the `console.log()`, there's no `i` for reference.
10. At line 12 the function run through `console.log(length)` and prints out `3`. Because `length` was declared with `const` variable at the top of the function and outside of the `for` loop, making it accessiable throughout the entire function. Since `prices.length` is 3 based on the number of items in the prices array, logging `length` would output `3`.
11. The function will return the discounted array `[50, 100, 150]`. We firstly created an empty `discounted` array and store the number of items in prices array in `length`. Then the `for` loop, using block-scoped `let i` would run from `0` to `length - 1`. Once through each iteration we calculate with `prices[i] * (1 - discount)`, we store the value into `discounted`. And after the iteration through all items in the array, `discounted` will hold `[50, 100, 150]` and being returned. But such array was not being shown since we never call `console.log()` for `discounted`, thus not being display in terminal. But it would return the discounted array as `[50, 100, 150]`.
12. Notations
- A. student.name // 'Sarah'
- B. student['Grad Year'] // '2022'
- C. student.greeting() // calls the function logs 'Hello!'
- D. student['Favorite Teacher'].name // 'Thomas Powell'
- E. student.courseLoad[0] // 'CSE110'
13. Arithmetic
- A. '3' + 2 = `'32'` 
    The '+' operator with the string '3' performs string concatenation, so 2 in this operation is treated as string '2' and join with '3' to get the result string of '32'.
- B. '3' - 2 = `1`
    The '-' operator would forces numeric conversion as it only works on numbers, so the string '3' is being treated as the number 3 and being subtracted with 2 to get the result of 1.
- C. 3 + null = `3`
    Null in this case is being treated as 0 in numeric contexts, thus 3 plus 0 will result in the number 3.
- D. '3' + null = `'3null'`
    The '+' operator treats null as a string 'null', thus with the operator it concatenated to the string '3' and result in '3null'.
- E. true + 3 = `4`
    True in here is being treated as 1 in numeric contexts, thus 1 plus 3 would result in the number 4.
- F. false + null = `0`
    False in here is being treated as 0 in numeric contexts while null is also being treated as 0 in numeric contexts. Thus 0 plus 0 will result in 0.
- G. '3' + undefined = `'3undefined'`
    The '+' operator treats undefined as another string, thus it concatenated the string '3' with 'undefined' to get the result of '3undefined'.
- H. '3' - undefined = `NaN`
    The '-' operator only works with numbers, thus string '3' is being treated as the number 3, undefined would become NaN since it is not a number. Therefore 3 subtracts NaN would just result in NaN.
14. Comparison
- A. '2' > 1 outputs `true`
    The '>' operstor triggers numeric conversion for comparison. The string '2' is being treated as the number 2, thus 2 it is greater than 1, hence the comparsion will be true.
- B. '2' < '12' outputs `false`
    Since both are strings, the comparsion would be lexicographical, '2' is being compare to string '1' and since the value of '2' is greater than '1', so '2' < '12' would be false.
- C. 2 == '2' outputs `true`
    The loose equality operator treats '2' as the number 2, therefore 2 == 2 would be true as the number 2 is indeed equal to the number 2.
- D. 2 === '2' outputs `false`
    The strict equality operator checks both value and type that is being compared, and in this case one is a number with the other being a string. So it would return false as the number 2 and the string '2' are not the same type.
- E. true == 2 outputs `false`
    True in this case is treated as the number 1 with the '==' loose equality operator, and 1 does not equal to 2, so it returns false.
- F. true === Boolean(2) outputs `true`
    The Boolean(2) converts the number 2 to be true as any non-zero number is true. Thus the strict equality between the two booleans would be true as both sides are the same type.
15. The '==' loose equality compared two values for equality after applying type convertion when they are different types. Such as the comparsion 2 == '2' is true because the string '2' is converted to the number 2 before comparison. While the '===' strict equality checks both the value and type independently without convertion. Therefore, even though they would compare equally under '==' operator, 2 === '2' is false since one is a number and the other is a string.
16. In JS file `part2-question16.js`
17. When the function is called with the parameters `modifyArray([1,2,3], doSomething)` we will get the result array to be `[2,4,6]`. Inside the `modifyArray` function, it created an empty array `newArr`. Once we call `modifyArray` with the array `[1,2,3]` and the callback function `doSomething`, it will loop over each element of the input array `[1,2,3]` starting with the first iteration when `i = 0`. During `i = 0`, `array[0]` is `1`, thus it would be `callback(1)` that calls on function `doSomething(1)` that runs and returns `1 * 2 = 2`, then it push the result `2` into the `newArr`, which it now become `[2]`. Then move on to second iteration when `i = 1`, where `array[1]` is `2`, the callback function would then calls on function `doSomething(2)` that returns value `4` as `2 * 2 = 4`. `4` would then be push to the `newArr`, which now it contains elements `[2, 4]`. The third iteration when `i = 2`, `array[2]` is `3` and callback function calls on function `doSomething(3)` that returns `6` since `3 * 2 = 6`. Pushes `6` into the `newArr`, now the `newArr` contains `[2, 4, 6]`. And this concludes the loop as all the item in the array has been iterated through. After such loop, the function `modifyArray` would return the result `newArr` to be `[2, 4, 6]`.
18. In the JS file, `part2-question18.js`
19. The output of the code is `1 4 3 2`.
