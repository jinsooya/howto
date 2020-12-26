- - -

# 가상 환경 만들기

## Virtual Environments

* * *

**박 진 수** 교수  
Intelligent Data Semantics Lab  
Seoul National University

- - -

<h1>Table of Contents<span class="tocSkip"></span></h1>
<div class="toc"><ul class="toc-item"><li><span><a href="#가상-환경-구성" data-toc-modified-id="가상-환경-구성-1">가상 환경 구성</a></span><ul class="toc-item"><li><span><a href="#파이썬-환경" data-toc-modified-id="파이썬-환경-1.1">파이썬 환경</a></span></li><li><span><a href="#아나콘다-환경" data-toc-modified-id="아나콘다-환경-1.2">아나콘다 환경</a></span></li></ul></li><li><span><a href="#가상-환경-활성화" data-toc-modified-id="가상-환경-활성화-2">가상 환경 활성화</a></span><ul class="toc-item"><li><span><a href="#파이썬-환경" data-toc-modified-id="파이썬-환경-2.1">파이썬 환경</a></span></li><li><span><a href="#아나콘다-환경" data-toc-modified-id="아나콘다-환경-2.2">아나콘다 환경</a></span></li></ul></li><li><span><a href="#가상-환경-비활성화" data-toc-modified-id="가상-환경-비활성화-3">가상 환경 비활성화</a></span><ul class="toc-item"><li><span><a href="#파이썬-환경" data-toc-modified-id="파이썬-환경-3.1">파이썬 환경</a></span></li><li><span><a href="#아나콘다-환경" data-toc-modified-id="아나콘다-환경-3.2">아나콘다 환경</a></span></li></ul></li></ul></div>

#  가상 환경 구성 

가상 환경은 각 프로젝트마다 파이썬 실행 환경을 독립적으로 활용할 수 있게 해주는 편리한 기능이다. 예를 들어 프로젝트의 특징에 따라 다른 종류의 파이썬 라이브러리가 필요할 수도 있고 동일한 라이브러리라고 하더라고 호환성이나 버전 종속성 때문에 다른 버전을 사용해야 할 수도 있다. 이런 경우에 가상 환경을 구성하여 사용하면 편리하다.

## 파이썬 환경

**방법 1(상대 경로)**

가상 환경을 만들기 위해서 먼저 가상 환경 파일들을 저장할 상위 폴드로 이동한다. 예를 들어 /projects/python/venv 아래에 'myenv'를 만들고자 한다면 다음과 같이 `venv` 모듈을 실행하면 된다.


```code
python -m venv [폴더-이름]
```

- Linux / macOS
  + /projects/python/venv 폴더(디렉토리)에서

```sh
$ python -m venv myenv
```

- Windows
  + C:₩projects₩python₩venv 폴더(디렉토리)에서


```sh
C:₩projects₩python₩venv> python -m venv myenv
```

**방법 2(절대 경로)**

절대 경로를 사용하여 가상 환경을 구성하려면 현재 폴더나 아무 폴더에서 다음 명령어를 실행한다.

```code
python -m venv [절대경로]
```

- Linux / macOS
  + 어디서든 다음 명령을 실행하면 된다.


```sh
$ python -m venv /projects/python/venv/myenv
```

- Windows
  + 어디서든 다음 명령을 실행하면 된다.

```sh
C:₩Users₩me> python -m venv C:₩projects₩python₩venv₩myenv
```

실행 결과 'myenv' 폴더가 생성되며, 파이썬 인터프리터를 포함해서 표준 라이브러리와 관련 파일들이 복사된다.

상세한 설명은 아래 링크를 참조하면 된다.
- https://docs.python.org/3/library/venv.html

## 아나콘다 환경

아나콘다(anaconda)에서 가상 환경을 구성할 때는 운영제제와 상관없이 공통적으로 명령어 셸에서 다음 명령어를 실행하면 된다. 이때 가상 환경의 이름이 'myenv'라 가정한다. 그리고 'x.x'를 설치하고자 하는 파이썬 버전으로 설정한다. `python=x.x`를 생략하면 기본 파이썬  버전이 설치된다.

```code
conda create --name myenv python=x.x
```

상세한 설명은 아래 링크를 참조하면 된다.
- https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-with-commands

# 가상 환경 활성화

## 파이썬 환경

가상 환경을 할성화하는 명령어는 운영체제마다 다르다. 여기서는 실행하고자 하는 가상 환경의 이름은 'myenv'이고 'projects/python/venv' 아래 하위 폴더로 설치되어 있다고 가정한다.

**방법 1(상대 경로)**

- Linux / macOS
  + /projects/python/venv 폴더(디렉토리)에서

```sh
$ source myenv/bin/activate
```

- Windows
  + C:₩projects₩python₩venv 폴더(디렉토리)에서
  
```sh
C:₩projects₩python₩venv> myenv₩Scripts₩activate.bat
```

**방법 2(절대 경로)**

절대 경로를 사용하여 가상 환경을 구성하려면 현재 폴더나 아무 폴더에서 다음 명령어를 실행한다.

- Linux / macOS

```sh
$ source /projects/python/venv/myenv/bin/activate
```

- Windows

```sh
C:₩Users₩me> C:₩projects₩python₩venv₩myenv₩Scripts₩activate (또는 ativate.bat)
```

가상 환경을 성공적으로 할성화했다면 명령어 셸은 다음과 같은 프롬프트(prompt)가 나타난다. Windows의 경우는 `$` 대신 `>`가 표시될 것이다.

```sh
(myenv) $
```


상세한 설명은 아래 링크를 참조하면 된다.
- https://docs.python.org/3/library/venv.html

## 아나콘다 환경

다음 명령어를 실행하면 가상 환경이 활성화 된다. 이때 가상 환경의 이름은 'myenv'라 가정한다. 

프롬프트 `%`는 운영 체제에 따라(`>`, `$` 등) 다를 수 있다.

```sh
(base) % conda activate myenv
```

가상 환경을 성공적으로 활성화해다면 명령어 셸은 다음과 같은 프롬프트(prompt)가 나타난다.

```sh
(myenv) %
```

만약 가상 환경 이름이 기억나지 않으면 다음 명령어를 싱행하여 구성한 가상 환경의 이름을 확인할 수 있다.

```sh
(base) % conda env list
```

상세한 설명은 아래 링크를 참조하면 된다.
- https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#activating-an-environment

# 가상 환경 비활성화

## 파이썬 환경

- Linux / macOS

```sh
(myenv) $ deactivate
```

- Windows

```sh
(myenv) C:₩...> deactivate (또는 deactivate.bat)
```

## 아나콘다 환경

프롬프트 `%`는 운영 체제에 따라(`>`, `$` 등) 다를 수 있다.

```sh
(myenv) % conda deactivate
```

- - -

# THE END
