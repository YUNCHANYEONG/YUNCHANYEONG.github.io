---
layout: single
title : java day6 test
categories : coding
tag : java
toc : true
---

#### 임의의 숫자 5개를 입력하여 출력결과가 오름차순으로 출력되는 프로그램을 작성하라.

```
Scanner sc = new Scanner(System.in);
        int num = 5;
        int[] arr = new int[num];

        for (int i = 0; i < arr.length; i++) {
            System.out.print((i + 1) + "번째 숫자를 입력하세요 >>> ");
            arr[i] = sc.nextInt();
        }
        // 70 90 100 60 80
        int temp = 0;

        for (int i = 0; i < arr.length-1; i++) {
            for (int j = i + 1; j < arr.length; j++) {
                if (arr[i] > arr[j]) {       // 70 > 60
                    temp = arr[i];           // temp = 70 , arr[0] = 70
                    arr[i] = arr[j];         // arr[0] = 60, arr[3] = 60
                    arr[j] = temp;           // arr[3] = 70, temp = 70
                }                       // 결론 arr[i] > arr[j]일 경우 두 값이 바뀌어 저장
            }
        }

        for (int i = 0; i < arr.length; i++) {
            System.out.print(arr[i] + " ");     // 60 70 80 90 100
        }
```

```
실행결과
1번째 숫자를 입력하세요 >>> 70
2번째 숫자를 입력하세요 >>> 90
3번째 숫자를 입력하세요 >>> 100
4번째 숫자를 입력하세요 >>> 60
5번째 숫자를 입력하세요 >>> 80
60 70 80 90 100 
```



#### 문자열로 숫자를 입력받아 각 자리수를 곱하는 프로그램을 작성하자.

```
		Scanner sc = new Scanner(System.in);
        System.out.print("숫자를 입력하세요 >>> ");
        String num = sc.next(); // 234

        int result = 1;

        for (int i = 0; i < num.length(); i++) {
            result *= Integer.parseInt(num.substring(i,i+1));
            // 각 자리수들의 숫자의 곱을 result에 대입
        }

        System.out.println("결과 : " + result); // 결과 : 24
```

```
실행결과
숫자를 입력하세요 >>> 234
결과 : 24
```
