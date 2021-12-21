---
layout: single
title : java day7 test
categories : coding
tag : java
toc : true
---

#### 과일 구입 프로그램을 만들어보자.

 (단, 과일 클래스 상속 받아 각 과일 이름별 클래스를 생성하고 과일 저장을 10개까지)

```
메뉴을 선택하세요(1.사과구입 2.바나나구입 3.오렌지구입 4.구입목록 5.과일검색 6.종료)
1
사과를 구입했습니다.
2
바나나를 구입했습니다.
4
***** 구입한 과일 *****
사과 : 100원, 빨강, 서울,
바나나 : 1500원, 노랑, 제주
...
5
검색할 과일을 선택하세요(1.사과 2.바나나 3.오렌지)
1
사과 : 100원, 빨강, 서울
6
프로그램을 종료합니다.
```

```
import java.util.Scanner;

public class Shop_me {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int ap = 0;
        int ba = 0;
        int or = 0;

        Fruit_me[] fruits = new Fruit_me[3];
        for (int i = 0; i < 3; i++) {
            fruits[i] = new Fruit_me("0", "0", "0", "0");
        }

        int t = 0;
        do {
            int count = ap + ba + or;
            System.out.print("메뉴을 선택하세요(1.사과구입 2.바나나구입 3.오렌지구입 4.구입목록 5.과일검색 6.종료) >>> ");
            int a = sc.nextInt();
            if (a == 1) {
                System.out.print("사과를 구입했습니다.");
                fruits[0] = new Fruit_me("사과", "1200원", "빨강", "서울");
                if (count == 10) {
                    System.out.println("더 이상 구입하실수 없습니다.");
                    continue;
                }
                ap++;
                System.out.print("(" + ap + ") ");
                System.out.println("");

            } else if (a == 2) {
                System.out.print("바나나를 구입했습니다.");
                fruits[1] = new Fruit_me("바나나", "1300원", "노랑", "필리핀");
                if (count == 10) {
                    System.out.println("더 이상 구입하실수 없습니다.");
                    continue;
                }
                ba++;
                System.out.print("(" + ba + ") ");
                System.out.println("");

            } else if (a == 3) {
                System.out.print("오렌지를 구입했습니다.");
                fruits[2] = new Fruit_me("오렌지", "1500원", "주황", "제주시");
                if (count == 10) {
                    System.out.println("더 이상 구입하실수 없습니다.");
                    continue;
                }
                or++;
                System.out.print("(" + or + ") ");
                System.out.println("");

            } else if (a == 4) {
                System.out.println("***** 구입한 과일 *****");
                /*
                사과 : 100원, 빨강, 서울,
                바나나 : 1500원, 노랑, 제주
                */

                System.out.println("총 구매 과일의 수 : " + count);
                if (ap >= 1) {
                    System.out.print("구매한 사과(" + ap + ") ");
                    fruits[0].info();
                }
                if (ba >= 1) {
                    System.out.print("구매한 바나나(" + ba + ") ");
                    fruits[1].info();
                }
                if (or >= 1) {
                    System.out.print("구매한 오렌지(" + or + ") ");
                    fruits[2].info();
                }
                System.out.println("");

            } else if (a == 5) {
                int z = 0;
                do {
                    System.out.print("검색할 과일을 선택하세요(1.사과 2.바나나 3.오렌지 4.이전으로) >>> ");
                    int q = sc.nextInt();
                    if (q == 1) {
                        fruits[0].info();
                    } else if (q == 2) {
                        fruits[1].info();
                    } else if (q == 3) {
                        fruits[2].info();
                    } else if (q == 4) {
                        z++;
                    } else {
                        System.out.println("입력값을 확인하세요.");
                    }
                } while (z == 0);
                System.out.println("");
            } else if (a == 6) {
                System.out.println("프로그램을 종료합니다.");
                t++;
            }

        } while (t == 0);

    }
}
```

```
public class Fruit_me {
    /* name : 과일이름
    price : 가격
   color : 색상
   from : 원산지
     */

    private String name;
    private String price;
    private String color;
    private String from;

    public Fruit_me(){}

    public Fruit_me(String name, String price, String color, String from) {
        this.name = name;
        this.price = price;
        this.color = color;
        this.from = from;
    }

    public void info(){
        System.out.println(name + " : " + price + ", " + color + ", " + from);
    }
}
```

```
메뉴을 선택하세요(1.사과구입 2.바나나구입 3.오렌지구입 4.구입목록 5.과일검색 6.종료) >>> 1
사과를 구입했습니다.(1) 
메뉴을 선택하세요(1.사과구입 2.바나나구입 3.오렌지구입 4.구입목록 5.과일검색 6.종료) >>> 2
바나나를 구입했습니다.(1) 
메뉴을 선택하세요(1.사과구입 2.바나나구입 3.오렌지구입 4.구입목록 5.과일검색 6.종료) >>> 3
오렌지를 구입했습니다.(1) 
메뉴을 선택하세요(1.사과구입 2.바나나구입 3.오렌지구입 4.구입목록 5.과일검색 6.종료) >>> 4
***** 구입한 과일 *****
총 구매 과일의 수 : 3
구매한 사과(1) 사과 : 1200원, 빨강, 서울
구매한 바나나(1) 바나나 : 1300원, 노랑, 필리핀
구매한 오렌지(1) 오렌지 : 1500원, 주황, 제주시

메뉴을 선택하세요(1.사과구입 2.바나나구입 3.오렌지구입 4.구입목록 5.과일검색 6.종료) >>> 5
검색할 과일을 선택하세요(1.사과 2.바나나 3.오렌지 4.이전으로) >>> 1
사과 : 1200원, 빨강, 서울
검색할 과일을 선택하세요(1.사과 2.바나나 3.오렌지 4.이전으로) >>> 2
바나나 : 1300원, 노랑, 필리핀
검색할 과일을 선택하세요(1.사과 2.바나나 3.오렌지 4.이전으로) >>> 3
오렌지 : 1500원, 주황, 제주시
검색할 과일을 선택하세요(1.사과 2.바나나 3.오렌지 4.이전으로) >>> 4

메뉴을 선택하세요(1.사과구입 2.바나나구입 3.오렌지구입 4.구입목록 5.과일검색 6.종료) >>> 6
프로그램을 종료합니다.
```

