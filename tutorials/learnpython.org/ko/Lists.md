리스트는 배열과 매우 유사합니다. 리스트는 변수의 어떤 유형이든 포함할 수 있으며, 원하는 만큼 많은 변수를 포함할 수 있습니다. 리스트는 또한 매우 간단한 방식으로 반복할 수 있습니다. 여기에 리스트를 만드는 방법의 예가 있습니다.

    mylist = []
    mylist.append(1)
    mylist.append(2)
    mylist.append(3)
    print(mylist[0]) # 1 출력
    print(mylist[1]) # 2 출력
    print(mylist[2]) # 3 출력

    # 1,2,3 출력
    for x in mylist:
        print(x)

존재하지 않는 인덱스에 접근하면 예외(오류)가 발생합니다.

    mylist = [1,2,3]
    print(mylist[10])

Exercise
--------

이 연습 문제에서는 "append" 리스트 메소드를 사용하여 숫자와 문자열을 올바른 리스트에 추가해야 합니다. "numbers" 리스트에 숫자 1, 2, 3을 추가하고 문자열 변수에 'hello'와 'world'를 추가해야 합니다.

또한 대괄호 연산자 `[]`를 사용하여 names 리스트에서 두 번째 이름을 second_name 변수에 채워 넣어야 합니다. 인덱스는 0부터 시작하므로 리스트에서 두 번째 항목에 접근하려면 인덱스가 1이어야 함을 유의하세요.