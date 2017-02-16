## 3장 숫자 삼각형

이번 장에서는 다음과 같은 출력을 하는 프로그램을 만들어 보자.

```
1
2 3
4 5 6
7 8 9 10
11 12 13 14 15
16 17 18 19 20 21
1
1 1
1 2 1
1 3 3 1
1 4 6 4 1
1 5 10 10 5 1
```

초보에게 저것을 짜라는 것은 굉장한 요구사항이므로 코드에 대한 설명은 **6장 숫자 삼각형 2부**에서 다룰 것이다.

이 장의 목표는 머리를 비우고 그냥 코드를 따라 입력해 저렇게 나오나 결과를 확인하는 것이다.

프로그램 전체 코드는 다음과 같다.

```
for x in 1:6
    for y in 1:x
        print(y + binomial(x,2), " ")
    end
    println()
end

for x in 1:6
    for y in 1:x
        print(binomial(x-1,y-1), " ")
    end
    println()
end
```

이번 장에서 추가로 해 볼 것은 물음표 키\(**?**\)를 눌러 키워드와 함수에 대한 도움말을 보는 것이다.

영어가 불편하면 구글 번역기\([https://translate.google.com/](https://translate.google.com/)\)에 텍스트를 복사해 붙여 넣어 번역해 보자.

help?&gt; **for**

help?&gt; **end**

help?&gt; **print**

help?&gt; **println**

help?&gt; **binomial**

