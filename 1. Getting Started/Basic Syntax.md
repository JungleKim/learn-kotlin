# Basic Syntax

## Defining Packages
```kotlin
package my.demo

import java.util.*

/// ... more
```
* 패키지 키워드는 코드의 최상단에 위치해야합니다.
* 코드파일은 파일시스템에 임의로 배치 할 수 있습니다.
	* XCode의 구조같은 이야기인것같다.

## Defining Functions
```kotlin
fun sum(a: Int, b: Int): Int {
	return a + b
}

fun sum(a: Int, b: Int) = a + b

fun printSum(a: Int, b: Int): Unit {
	println("sum of $a and $b is ${a + b}")
}

fun printSum(a: Int, b: Int) {
	println("sum of $a and $b is ${a + b}")
}
```	
1. `Int`파라미터 2개를 받고, `Int`를 리턴하는 경우
2. 반환유형을 유추 할 수있는 경우.
3. 의미있는 반환값이 없는경우 (Void)
4. Unit은 생략가능

## Defining Local Variables
```kotlin
// 상수
val a: Int = 1  // 타입명시와 함께 초기화
val b = 2   // `Int` 타입 유추
val c: Int  // 바로 초기화 하지않을땐 타입명시 필요
c = 3
```
```kotlin
// 변수
var xx: String = 5 // Error
var x = 5 // `Int` 타입 유추
x += 1 // 재 할당 가능
```

## Comments
```kotlin
// 한줄

/*
여
러
줄
*/
```

## Using String Templates
```kotlin
var a = 1
val s1 = "a is $a"  // 변수사용

a = 2
val s2 = "${s1.replace("is", "was")}, but now is $a" // 함수, 연산등 임의의 표현식
```

## Using Conditional Expressions
```kotlin
fun maxOf(a: Int, b: Int): Int {
    if (a > b) {
        return a
    } else {
        return b
    }
}

fun maxOf(a: Int, b: Int) = if (a > b) a else b
```
1. 평범한 if문
2. 3항연산자 응용

## Using nullable values and checking for null
```kotlin
// nullable 명시
fun parseInt(str: String): Int? {
    // ...
}
```

## Using type checks and automatic casts
```kotlin
fun getStringLength(obj: Any): Int? {
    if (obj is String) {
        // obj is String Type
        return obj.length
    }

	 // obj is Any Type
    return null
}

fun getStringLength(obj: Any): Int? {
    if (obj !is String) return null

	 // obj is String Type
    return obj.length
}

fun getStringLength(obj: Any): Int? {
    // `obj is String` 이후 오른쪽 연산자에서 obj는 String이다.
    if (obj is String && obj.length > 0) {
        return obj.length
    }

    return null
}
```
* `is`키워드로 타입을 체크한 이후에 별도로 캐스팅할 필요없다.

## Using a for loop
```kotlin
val items = listOf("apple", "banana", "kiwi")
for (item in items) {
    println(item)
}

val items = listOf("apple", "banana", "kiwi")
for (index in items.indices) {
    println("item at $index is ${items[index]}")
}
```

## Using