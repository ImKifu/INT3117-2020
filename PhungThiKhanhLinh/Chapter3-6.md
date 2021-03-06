#### Exercise 6:
__a.    Một bài kiểm thử không đạt lỗi:__
```java
@Test
 void testComputePrimesA() {
     PrimeNumbers primeNumbers = new PrimeNumbers();
     primeNumbers.computePrimes(0);
 
     assertEquals("[]", primeNumbers.toString());
     // it never enters the while loop
 }
 ```
__b.    Một bài kiểm thử đạt lỗi nhưng không lây nhiễm:__
```java
@Test
 void testComputePrimesB() {
     PrimeNumbers primeNumbers = new PrimeNumbers();
     primeNumbers.computePrimes(7);
 
     assertEquals("[2, 3, 5, 7, 11, 13, 17]",
          primeNumbers.toString());
 } 
 ```
__c.    Một kiểm thử lây nhiễm trạng thái, nhưng không lan truyền:__
```java
@Test
 void testComputePrimesC() {
     PrimeNumbers primeNumbers = new PrimeNumbers();
     primeNumbers.computePrimes(8);
 
     assertEquals("[2, 3, 5, 7, 11, 13, 17, 19]", 
         primeNumbers.toString());
     // it is affected because it doesn't include 19
}
````
__d.    Một kiểm thử được lan truyền, nhưng k tiết lộ:__
- Kiểm tra này không thể thực hiện được vì các lỗi bắt đầu ở số 19 (chúng ta không xem xét số 9 vì nó không phải là số nguyên tố), tất cả các số nguyên tố tiếp theo kết thúc bằng '9' sẽ không nằm trong giá trị kết quả.

__e.    Một bài kiểm thử cho thấy lỗi:__
```java
@Test
 void testComputePrimesE() {
     PrimeNumbers primeNumbers = new PrimeNumbers();
     primeNumbers.computePrimes(8);
 
     assertEquals("[2, 3, 5, 7, 11, 13, 17, 19]",
         primeNumbers.toString());
 } 
 ```
