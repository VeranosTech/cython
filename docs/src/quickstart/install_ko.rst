싸이선(Cython) 설치
===========================

아나콘다([Anaconda]_), Enthought Canopy([Canopy]_),
Python(x,y)([Pythonxy]_), and Sage([Sage]_)와 같은
과학기술용 파이썬 배포판은 사이썬을 포함하므로 추가 설치가 필요없다.
만약 사용하고 있는 배포판의 싸이판의 버전이 너무 낮으면
다음에 설명하는 방식으로 업그레이드할 수 있다.
이 튜토리얼은 (다른 설명이 없다면) 싸이선 버전 0.11.2 이상을 대상으로 한다.

파이썬과 달리 싸이선은 C 컴파일러가 시스템에 있어야 한다.
C 컴파일러를 설치하는 법은 사용하는 시스템마다 다르다.:

 - **리눅스(Linux)**에는 GNU C 컴파일러(gcc)가 있거나 쉽게 설치할 수 있다.
   예를 들어 우분투나 데이안에서는``sudo apt-get install build-essential`` 명령으로
   필요한 것을 모두 설치할 수 있다.

 - **맥(Mac) OS X**에서는 애플 XCode를 설치한다.
   XCode는 맥 OS X's 설치 DVD나 http://developer.apple.com\ 에서 구할 수 있다.

 - **윈도우(Windows)** 가장 인기있는 방식은 오픈소스 MinGW(a
   Windows distribution of gcc)를 사용하는 것이다.
   MinGW을 수동으로 설치하는 방법에 대해서는 부록을 참조한다.
   Enthought Canopy, Python(x,y)에는 MinGW이 포함되어 있지만
   부록에서 설명하는 몇가지 설정 단계가 필요하다.
   다른 방법은 마이크로소프트 Visual C를 사용하는 것이다.
   단 파이썬을 빌드한 것과 같은 버전의 컴파일러가 있어야 한다.

.. dagss tried other forms of ReST lists and they didn't look nice
.. with rst2latex.

가장 최신의 싸이선 버전은 http://cython.org\ 에서 내려받는다.
tarball 또는 zip 파일 압축을 풀고, 디렉토리 안으로 들어가서 다음을 실행한다.::

  python setup.py install

만약 ``pip``\ 가 시스템에 있으면 다음처럼 PyPI에서 받아서 설치할 수 있다.

::

  pip install Cython

PyPI에 있는 wheel 패키지가 지원하지 않는 플랫폼에서 CI/테스팅 용의 빌드를 할 때는
전체 소스코드를 빌드하는 것보다 컴파일되지 않는 사이썬 버전을 설치하는 게 훨씬 빠르다.

::

    pip install Cython --install-option="--no-cython-compile"


.. [Anaconda] http://docs.continuum.io/anaconda/
.. [Canopy] https://enthought.com/products/canopy/
.. [Pythonxy] http://www.pythonxy.com/
.. [Sage] W. Stein et al., Sage Mathematics Software, http://sagemath.org
