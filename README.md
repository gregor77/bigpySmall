# bigpySmall
bigpy small project, the note class

## 빅데이터를 위한 파이썬
- 강사님 : 이성주 seongjoo@codebasic.co
- [강의교재 "Python for Data Analysis"](http://it-ebooks.info/book/1041)
  * 강의 교재
- http://continuum.io/ 
  * product > anaconda
  * python 버전 2.7로 진행
   (why 3.4 버전을 사용하지 않는 것인가? 빅데이터 분석에 사용하는 라이브러리들이 3지원 작업중...)
  * window에서 설치할때는 "All Users"권한으로 설치를 진행
  * 터미널 $python 입력. python 버전뒤에 anaconda 붙어서 나오는지 확인
  * 터미널 $ipython 입력해도 무방, ctrl + d 종료	
- [참조 사이트]
  * [교재자료 pydata-book](https://github.com/pydata/pydata-book)
  * [이성주 강사님 github](https://github.com/lseongjoo/bigpy)
  * [IPython 설명](http://ipython.org/)
  * [Pandas library](http://pandas.pydata.org/)
  * [Python 기초문법](https://github.com/lseongjoo/learn-python)
 
### ipython notebook
```
$ipython notebook

# 로컬의 파일시스템을 보여주는 web page수행된다.
# data 분석을 할때 notebook을 자주 사용한다.
```
- Document에  "bigpy" 폴더를 만들어서 강의 진행
- notebook 단축키 
 * enter : new line
 * shift + enter : execute + new cell
 * 수행한 명령에 대한 설명을 추가할때, Code를 Markdown으로 변경해서 설명 추가 가능
 * #하면 heading1 처럼 표현됨
 * 위아래 화살표를 사용하면 cell의 위치 변경이 가능함
- ipython notebook으로 작성한 파이썬 소스를 활용할 수가 있냐?
 * File > Download as > 원하는 파일 형식을 입력

### Pandas
1. 사용 방법
 - 편집창을 누른 상태로 문자 'o'를 누르면  output 부분이 토글된다.
 - 편집모드 나가서, 셀을 선택한 상태에서
   * 'y' : 코드
   * 'm' : Markdown
 - ipython 노트북에는 디버그가 실행되지 않는다. -> ipython을 실행해야 한다.
   * ipython이 있는 경로로 가서, $ipython 입력
   * $run pydata-book/ch03/ipython_bug.py
   * $%debug 실행  --> shell이  ipdb 로 변경된 것을 확인가능
   * $up --> 이 함수를 실행한 상위 스택으로 올라갈 수 있다.
   * $down --> stack을 내려올 수 있다.
   * $quit --> debug 종료
   * $run -d pydata/ch03/ipython_bug.py --> debug 모드로 실행
   * $continue or $c -->  다음 중단점까지 실행
   * $next --> 한 줄씩 실행
   * $step --> 함수 into 실행
   * $print(a)  -->  특정한 객체의 상태를 확인하고 싶을 때, 파이썬 명령어로 바로 확인할 수 있다.
   * $list --> 앞, 뒤로 다섯개 줄을 볼 수 있다.
   * -> break point는 어떻게 설정하는가?
   * $b 9 --> 줄번호 9에 중단점을 설정해라
   * $b --> 중단점 정보를 확인하고 싶을때
 - ipython notebook 자체는 디버그를 지원하지 않는다.
   * save as. 를 python 으로 다운받는다.
   * markup은 주석으로, code cell 부분만 export 된다.
   * 브레이크포인트 찍고, ipython 디버그 실행해서 확인한다.

3. [참고]
  - anaconda 말고, enthought 라는 패키지도 있다. (www.enthought.com)
  - numpy, scipy를 만든 곳 --> 데이터 분석에 자주 사용
  - "데이터/수치 분석을 위한 파이썬 라이브러리 SciPy와 NumPy" (http://www.hanbit.co.kr/ebook/look.html?isbn=9788968486135)

4. anaconda vs enthought
  - ipython을 설치해서 둘다 사용하는데, enthought는 ipython기반에 자기 독자적인 개발체계를 사용하는데 비즈니스 모델을 가지므로, 사용하기가 번거로운 면이 있다.
 
 ```
 $pip search ipython  # ipython 패키지를 찾는 명령어
 $pip install pandas  # 원하는 패키지를 설치할 수 있다. unix 계열에 apt-get과 유사한 명령어	
 ```

5. [사용 예]
  - 분석 서버와 표현해주는 웹서버를 분리하여, http or tcp 통신을 통해서 분석결과를 받아오서 보여준다.
  - 분석 서버에 비용이 많이 드는 경우, 병렬적으로 늘리면서 효율적으로 관리가 가능하다.
  - 실제 강사님도 이렇게 사용하고 있다고 함.

6. [질문]
  - 센서로 수집한 종류를 파일로 떨궈서 분석을 해야하는가? --> NoSQL, 관계형 DB로 부터 DataFrame생성이 가능
  - d3.js로 데이터 시각화를 하고 싶은데, 분석을 파이썬기반이면 해당 웹앱도 파이썬 기반이 되어야 하는가?
