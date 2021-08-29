클래스란 인스턴스를 만들어내는 공장과도 같다.

클래스 상속 
class 상속받을 클래스명(상속할 클래스명)

```python

#클래스 선언 
class HousePark:
    lastname = "박"
    def __init__(self, name):
        self.fullname = self.lastname + name
    def travel(self, where):
        print("%s, %s여행을 가다." %(self.fullname, where))

pey = HousePark("응용")
pey.travel("부산")

#상속 
class HouseKim(HousePark):
    lastname = "김"
juliet = HouseKim("줄리엣")
juliet.travel("독도")

```


연산자 오버로딩 

```python
#연산자 오버로딩 

class HousePark :
    lastname = "박"
    
    def __init__(self, name):
        self.fullname = self.lastname + name 
    def travel(self, where):
        print("%s, %s여행을 가다." %(self.fullname, where))
    def love(self, other):
        print("%s, %s 사랑에 빠졌네" % (self.fullname, other.fullname))
    def __add__(self, other):
        print("%s, %s 결혼했네" %(self.fullname, other.fullname))
        
class HouseKim(HousePark):
    lastname = "김"
    def travel(self, where, day):
        print("%s, %s여행 %d일 가네." %(self.fullname, where, day))
        
pey = HousePark("응용")
juliet = HouseKim("줄리엣")
pey.love(juliet)
pey + juliet

# pey + juliet 더하기 연산자로 __add__ 호출 
```



모듈 : 

```python
def sum(a,b):
    if type(a) != type(b):
        print("서로 다른 타입이라 더할 수 없습니다.")
        return
    else:
        result = a+b
    return result
```

``` python
import mod1 
print(mod1.sum(1,'a'))

#주의! mod1.py라고 확장자를 입력하지 말 것. 

결과

#서로 다른 타입이라 더할 수 없습니다.
#None


```

return 이 단독으로 사용될 경우 None 값을 돌려준다. 

모듈파일의 if __name__ == "__name__": 
- mod1.py처럼 모듈파일을 직접 실행시켰을 경우 해당 문장의 아래 문장이 수행된다. 
- import로 파일을 불러 사용할 경우 수행되지 않는다.


내장함수
```python 
#enumerate
#순서가 있는 자료형(리스트, 튜플, 문자열)을 입력으로 받아 인덱스 값을 포함하는 enumerate 객체로 리턴한다.

for i, name in enumerate(['body','foo','bar']):
    print(i,name)
```
