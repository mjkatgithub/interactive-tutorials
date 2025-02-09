Python은 C 스타일의 문자열 포맷팅을 사용하여 새롭게 포맷된 문자열을 만듭니다. "%" 연산자는 "튜플" (고정 크기 리스트)로 둘러싸인 변수 집합과 포맷 문자열을 함께 사용하여 포맷합니다. 포맷 문자열은 일반 텍스트와 함께 "%s", "%d"와 같은 "인자 지정자"를 포함합니다.

변수 "name"에 사용자 이름이 있다고 가정하고, 해당 사용자를 위한 인사말을 출력하고 싶습니다.

    # 이는 "Hello, John!"을 출력합니다.
    name = "John"
    print("Hello, %s!" % name)

두 개 이상의 인자 지정자를 사용할 경우, 튜플 (괄호)을 사용합니다:

    # 이는 "John is 23 years old."을 출력합니다.
    name = "John"
    age = 23
    print("%s is %d years old." % (name, age))

문자열이 아닌 모든 객체도 %s 연산자를 사용하여 포맷될 수 있습니다. 객체의 "repr" 메서드에서 반환되는 문자열이 문자열로 포맷됩니다. 예를 들어:

    # 이는 "A list: [1, 2, 3]"을 출력합니다.
    mylist = [1,2,3]
    print("A list: %s" % mylist)

알아두어야 할 기본적인 인자 지정자는 다음과 같습니다:


`%s - 문자열 (숫자와 같은 문자열 표현이 있는 모든 객체)`

`%d - 정수`

`%f - 부동소수점 숫자`

`%.<숫자>f - 소수점 오른쪽의 고정 자릿수를 가진 부동소수점 숫자`

`%x/%X - 16진수 표현(소문자/대문자) 정수`


Exercise
--------

다음과 같은 구문을 사용하여 데이터를 출력하는 포맷 문자열을 작성해야 합니다:
    `Hello John Doe. Your current balance is $53.44.`