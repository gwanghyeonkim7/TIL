# 파이썬

- 파이썬은 버전의 영향을 많이 받기 때문에 확실히 버전에 대한 관리가 필요하다.
- '아나콘다' 프로그램을 이용해 버전을 마음대로 설정

~~~python
ㅇ visual c++ 2005 설치


ㅇ Lib/asyncio/__init__.py
import asyncio
if sys.platform == 'win32':  # pragma: no cover
    from .windows_events import *
    asyncio.set_event_loop_policy(asyncio.WindowsSelectorEventLoopPolicy())
    __all__ += windows_events.__all__
else:
    from .unix_events import *  # pragma: no cover
    __all__ += unix_events.__all__
~~~

--- 최신 버전일 경우 위의 코드를 이용해서 수정



### 개발환경

- 주피터 노트북
- VS Code



conda create --name myenv (가상 환경을 만든다)

activate myenv

conda list

activate 를 이용해 활성화

deactivate 를 이용해 비활성화 앞의 괄호를 지우는 것.

**jupyter notebook 주피터 노트북 실행방법



**구문이 시작될 때에는 무조건 콜론!

