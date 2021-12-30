![post-thumbnail](https://media.vlpt.us/images/new_wisdom/post/4a0259ee-b980-484b-8bf4-25eb4705459f/flask.png)

Soundee 프로젝트에서는 5초마다 들어오는 소리에 대한 추론 정보를 DB에 저장해야 한다. 딥러닝 서버로 flask를 사용하니 알아볼 겸사겸사해서 정리!!

## 🚩 기본 세팅 설정 (몇 가지 설치들)

최근에 나는 ✨MAC✨으로 바꿨기 때문에😎 MAC 기준으로 작성하겠다.
MAC에서는 Homebrew라는 패키지 매니저가 있으면 각종 개발에 필요한 패키지들을 쉽게 설치할 수 있으니 Homebrew를 먼저 깔자!
(나는 이미 Homebrew가 설치돼 있는 상태이다.)

**Homebrew 설치**

```null
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

그리고 Python3 이상이 필요하니 brew를 사용해 설치하자.

**Python3 설치**

```null
$ brew install python3
$ python3 --version
```

Python3를 설치하게 되면 파이썬 패키지 관리 툴인 pip가 함께 설치된다.
파이썬 관련 패키지들은 pip로 모두 설치 가능하다.
이제 파이썬 가상환경을 만들어주자!

**가상환경 설치 & 생성**

```null
$ sudo pip3 install virtualenv
```

virtualenv를 설치했다면 프로젝트 폴더에서 가상환경을 생성하고 켜주자!

```null
$ virtualenv myenv
$ source myenv/bin/activate
```

![img](https://media.vlpt.us/images/new_wisdom/post/f7b7b977-bc39-4d17-a663-514bf81beaff/image.png)
그럼 이렇게 가상환경이 켜진 걸 볼 수 있다.
만약 가상환경을 끄고 싶으면 deactivate 를 입력하면 된다.

그럼 이제 flask를 설치해보자!

```null
$ pip3 install flask
```

참고로 가상환경이 활성화 된 상태에서 pip를 통한 설치는 그 가상환경에만 적용이 된다.

이제 폴더 안에 파이썬 파일을 작성하면 된다!

flask를 이용한 간단한 페이지 띄우기!
**📃 main.py**

```null
from flask import Flask
app = Flask(__name__)


@app.route('/')
def hello():
    return "Hello World!"
```

이를 실행하기 위해서는 간단한 명령어 하나면 된다!

```null
$ FLASK_APP=main.py flask run
```