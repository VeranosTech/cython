싸이선(Cython) 개요
================================

싸이선([Cython])은 파이썬 언어용 C 확장 모듈을 만들기 위한 프로그래밍 언어이다.
객체지향, 함수형, 동적 타입 프로그래밍을 지원하는 고수준 언어인
파이썬([Python]_)의 상위집합이 되는 것을 목표로 한다.
주 기능은 언어의 일부로 정적 타입 선언을 추가할 수 있도록
지원하는 것이다.
소스코드는 최적화된 C/C++ 코드로 자동 변환된 후 다시 파이썬 확장 모듈로 컴파일된다.
이런 방식으로 파이썬 언어가 가지는 높은 프로그래밍 생선성을 유지한 채로
빠른 프로그램 실행과 외부 C 라이브러리 통합을 동시에 가능하게 한다.

파이썬의 주된 실행 환경은 C로 만들어진 CPython이다. 이외에 자바(Jython [Jython]_),
C# (IronPython [IronPython]_), 파이썬(PyPy [PyPy]_)의 다른 구현도 있다.
C로 만들어진 CPython은 C 언어 인터페이스를 통해 많은 외부 라이브러리를 래핑(wrapping)할 수 있다.
그러나 C로 통합용 코드를 만드는 작업이 쉽지 않다.
특히 C같은 기계어에 가까운 언어가 아닌 파이썬같은 고수준 언어에만 익숙한 프로그래머들에게는
더 어렵다.

싸이선은 Pyrex([Pyrex]_)에 기반을 두고 있드며 파이썬 코드를 C 코드로
자동 변환하는 소스코드 변환기를 사용하여 이 문제를 해결한다.
이 코드는 CPython 실행 환경에서 실행되지만 컴파일된 C의 속도로 실행되며
C 라이브러리들 직접 호출할 수도 있다.
동시에 파이썬 소스코드의 원래 인터페이스도 유지하므로 다른 파이썬 코드에서도
직접 사용할 수 있다.
이런 두 특성으로 인해 싸이선은 두가지 경우에 많이 사용된다.:
첫번째는 빠른 바이너리 모듈로 CPython 인터프리터 자체를 확장하는 것이고
두번째는 외부 C 라이브러리와 파이썬 코드를 연결하는 인터페이스 역할이다.

싸이선은 대부분의 정규 파이썬 코드를 컴파일할 수 있지만
추가적으로 파이썬과 C 자료형을 정적 타입 선언하면 엄청난 속도 향상을 얻을 수도 있다.
싸이선은 C 문법을 원래의 파이썬 코드 일부에 적용하여 효율적인 C 코드를 생성할 수 있다.

자료형 선언의 목적은 두가지인데 하나는 파이썬의 동적 타입 문법을 정적이고 빠른 C 문법으로 바꾸는 것이고
다른 하나는 외부 라이브러리에서 선언된 타입을 직접 다루기 위한 것이다.
따라서 싸이선은 두 개의 프로그래밍 세계를 결합한, 폭넓게 적용 가능한 프로그래밍 언어가 된다.

.. [Cython] G. Ewing, R. W. Bradshaw, S. Behnel, D. S. Seljebotn et al.,
   The Cython compiler, http://cython.org.
.. [IronPython] Jim Hugunin et al., http://www.codeplex.com/IronPython.
.. [Jython] J. Huginin, B. Warsaw, F. Bock, et al.,
   Jython: Python for the Java platform, http://www.jython.org.
.. [PyPy] The PyPy Group, PyPy: a Python implementation written in Python,
   http://pypy.org.
.. [Pyrex] G. Ewing, Pyrex: C-Extensions for Python,
   http://www.cosc.canterbury.ac.nz/greg.ewing/python/Pyrex/
.. [Python] G. van Rossum et al., The Python programming language,
   http://python.org.
