## Visibility Modifiers

```
private
protected
internal
public // default
```


#### Packages
1. `public`은 모든곳에서 접근가능
2. `private`은 선언된 파일 내부에서만 접근가능
3. `internal`은 같은 `module`내에서만 접근가능
4. `protected` Top-Level엔 선언불가능


#### Classes ans Interfaces
1. `public`은 모든곳에서 접근가능
2. `private`은 클래스 내부에서만 접근가능
3. `internal`은 같은 `module`내에서만 접근가능
4. `protected`는 `private`의 속성에 추가로 subclass의 접근도 허용한다.


#### Constructors
```kotlin
class C private constructor(a: Int) {}
```


#### Modules
- `internal`에서 말하는 모듈의 정의
- 함께 컴파일되는 Kotlin의 파일집합

1. IntelliJ IDEA 모듈
2. Maven 혹은 Gradle Project
3. Ant 태스크를 한 번 호출하여 컴파일 된 파일 집합