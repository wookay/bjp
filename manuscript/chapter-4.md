# 4장 과일 알아 맞추기

이번 장에서는 다음과 같은 조건이 주어질 때

```
🍎  + 🍎  + 🍎  == 30
🍎  + 🍌  + 🍌  == 18
🍌  - 🌰  == 2
```

아래의 식이 뭔지 맞추는 프로그램을 만들어 보자.

```
🌰  + 🍎  + 🍌
```

이거 수학 아닌가요? 네.

이번 장에서는 준비물이 필요하다. 다음과 같은 두 패키지를 설치하자.

```
julia> Pkg.add("JuMP") 
...
julia> Pkg.add("Clp") 
...
```

이번 장도 설명은 **7장 과일 알아 맞추기 2부**에서 상세히 다루기로 하고 전체 코드를 입력해 보자.

```
using JuMP
using Clp

m = Model(solver = ClpSolver())

@variable(m, 🍎 )
@variable(m, 🍌 )
@variable(m, 🌰 )

@constraint(m, 🍎  + 🍎  + 🍎  == 30)
@constraint(m, 🍎  + 🍌  + 🍌  == 18)
@constraint(m, 🍌  - 🌰  == 2)

solve(m)

println("🌰  + 🍎  + 🍌  : ", getvalue(🌰  + 🍎  + 🍌 ))
```

이번 장에서도 새로 등장한 함수와 매크로\(**@**로 시작하는\)에 대해 물음표 키를 눌러 도움말로 읽어 보자.

그리고 다음과 같이 **typeof 함수**를 이용해 대상이 어떤 타입인지 보도록 하자.

```
julia> typeof(JuMP)
Module

julia> typeof(m)
JuMP.Model

julia> typeof(🍎)
JuMP.Variable

julia> typeof(solve)
JuMP.#solve

julia> typeof(println)
Base.#println
```

**@show 매크로**는 식의 중간 과정을 보여준다.

```
julia> @show 🍎 + 🍎
🍎 + 🍎 = 2 🍎
2 🍎
```

**typeof**와 **@show**도 물음표 키를 눌러 도움말로 찾아보자.

help?&gt; **typeof**

help?&gt; **@show**

