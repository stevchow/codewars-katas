Description:

Mr. Scrooge has a sum of money 'P' that wants to invest, and he wants to know how many years 'Y' this sum has to be kept in the bank in order for this sum of money to amount to 'D'.

The sum is kept for 'Y' years in the bank where interest 'I' is paid yearly, and the new sum is re-invested yearly after paying tax 'T'

Note that the principal is not taxed but only the year's accrued interest

Example:

  Let P be the Principal = 1000.00      
  Let I be the Interest Rate = 0.05      
  Let T be the Tax Rate = 0.18      
  Let D be the Desired Sum = 1100.00


After 1st Year -->
  P = 1041.00
After 2nd Year -->
  P = 1083.86
After 3rd Year -->
  P = 1128.30
Thus Mr. Scrooge has to wait for 3 years for the initial pricipal to ammount to the desired sum.

Your task is to complete the method provided and return the number of years 'Y' as a whole in order for Mr. Scrooge to get the desired sum.

Assumptions : Assume that Desired Principal 'D' is always greater than the initial principal, however it is best to take into consideration that if the Desired Principal 'D' is equal to Principal 'P' this should return 0 Years.


```js
function calculateYears(principal, interest, tax, desired) {
   
   // create an endless loop y=0;true;y++ 
   // that will increment the number of years
   for ( var year = 0;; year++ ) {
   
     // check if the principal has reached the desired amount
     if ( principal >= desired ) {
       return year;
     }
   
     // calculate the interest for this year
     var currentYearInterest = interest * principal;
     
     // calculate the tax on the interest for this year
     var currentYearTax = currentYearInterest * tax;
     
     // adjust the principal to add the interest and minus the tax
     principal = principal + currentYearInterest - currentYearTax;
   
   }
   
}
```