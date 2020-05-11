## Big-o표기법이란?

> 알고리즘의 성능을 수학적으로 표현해주는 표기법 / 시간과 공간복잡도를 표현할 수 있음 / 실제 러닝타임을 표시하기보다는 데이터나 사용자의 증가률에 따른 알고리즘의 성능을 예측하는게 목표 

### O(1)

-----

언제나 일정한 시간이 걸리는 알고리즘

### O(n)

----

입력 데이터의 크기에 비례해서 철회시간이 걸리는 알고리즘을 표현할때 사용, 데이터와 시간이 같이 증가함

### O(n^2)

-----

![image-20200511153059941](/Users/hongbeen/Library/Application Support/typora-user-images/image-20200511153059941.png)

### O(nm)

----

![image-20200511153227320](/Users/hongbeen/Library/Application Support/typora-user-images/image-20200511153227320.png)

### O(n^3)

---

![image-20200511153332622](/Users/hongbeen/Library/Application Support/typora-user-images/image-20200511153332622.png)

### O(2^n)

-----

![image-20200511153452671](/Users/hongbeen/Library/Application Support/typora-user-images/image-20200511153452671.png)

피보나치수열 사용 / 처음엔1로 시작하여 늘어난 면이 2 > 3 > 5 > 8

이미지출처: https://www.youtube.com/watch?v=6Iq5iMCVsXA

### O(log n) / binary search

----

한번씩 찾을 때마다 검색해야하는 데이터의 양이 절반씩 떨어지는 알고리즘

### O(Sqr+(n))

------

![image-20200511153924778](/Users/hongbeen/Library/Application Support/typora-user-images/image-20200511153924778.png)



Big-O표기법은 상수는 버리고 표현함

![image-20200511154030743](/Users/hongbeen/Library/Application Support/typora-user-images/image-20200511154030743.png)