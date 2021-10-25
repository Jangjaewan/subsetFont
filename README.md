# Subset font

서브셋 글리프를 활용해 경량화된 웹폰트 파일 생성 (ttf, woff, woff2)   
포함된 스크립트를 사용하기 위해선  <code>Python</code>과 FontTools의 <code>pyftsubset</code>라이브러리 설치 필요

## 사용방법 및 참고 링크
	
1. 시스템에 파이썬 설치
	- [Python 다운로드](https://www.python.org/downloads/)
	- [설치 가이드](https://wikidocs.net/8)
	- 터미널에 <code>python --version</code> 명령어 실행했을 때 버전이 출력되면 정상적으로 설치된 것

![파이썬 버전확인 명령어](/images/thumb_1.jpg)

2.  pyftsubset 라이브러리 설치([폰트툴즈의 pyftsubset을 사용한 폰트 서브셋 만들기](https://www.44bits.io/ko/post/optimization_webfont_with_pyftsubnet)) 
```
$ pip install fonttools

// Successfully installed fonttools-3.xx.x 메세지와 함께 설치가 완료되면 pyftsubset 명령어 실행 후 정상적으로 설치 되었는지 확인

$ pyftsubset
usage: pyftsubset font-file [glyph...] [--option=value]...
Try pyftsubset --help for more information.

//usage... 메세지 출력되면 정상
```
3. 다운로드 받은 <code>fonts</code> 디렉토리에 웹폰트 폴더 생성(폴더명은 웹폰트로 사용할 이름)

![폴더생성](/images/thumb_2.jpg)

4. 생성된 폴더 안에 다운로드 받은 폰트 파일(ttf, otf) 추가
5. 아래 리스트를 참고하여 굵기별 폰트 파일의 이름에 추가 및 수정
	- Black = 900
	- ExtraBold = 800
	- Bold = 700
	- SemiBold = 600
	- Medium = 500
	- Regular = 400
	- Light = 300
	- ExtraLight = 200
	- Thin = 100

![](/images/thumb_3.jpg)

6. 스크립트 파일 실행
	- 스크립트 파일 매개변수 : [kr || google] [폰트이름(폴더명)] [ttf || otf] [옵션 nonKr || onlyKr || onlyEn || onlyNum ] [옵션 full || kr ]
	- <code> EX) bash build_subset kr GmarketSans ttf</code>
	- 매개변수 상세안내
		- **glyphs** : 서브셋에 활용할 글리프 설정
			- kr : 특수문자, 한글 자모, 알파벳, 숫자, 구두점, 완성형 한글 등을 포함한 글리프
			- google : 구글폰트에서 사용한 빅데이터 기반 분석을 통해 그룹화된 전체 문자 글리프
			- 웹폰트용 CSS 파일은 kr만 생성됨
		- **폰트이름** : 3번에서 생성된 폴더 이름. <code>font-family</code>에 사용될 이름
		- **type** : 다운로드 받은 폰트 파일의 확장자
		- **subset**(옵션) : 폰트파일에서 선택된 문자열만 추출하여 폰트로 생성. 기본은 glyphs 
			- nonKr : 한글 제외
			- onlyKr : 한글만 포함
			- onlyEn : 영문만 포함
			- onlyNum : 숫자만 포함
		- **unicode subset**(옵션) : 텍스트 형식의 글리프가 아닌 유니코드 형식의 글리프 사용으로 unicode-range 활용
			- kr : 노토 KR 기준 92개의 unicode-range
			- full : 나눔고딕 기준 119개의  unicode-range

![](/images/thumb_4.jpg)

7. 실행이 완료되면 output > kr 디렉토리에 fonts 폴더에서 만들었던 폴더가 생성되어 있고 Subset 폴더와 웹폰트용 CSS 파일이 추가되어 있음

![](/images/thumb_5.jpg)

## 참고 링크

- [웹폰트, 가볍게 최적화 하기 - 스포카 한산스](https://brunch.co.kr/@kimdal/4)
- [스포카 한 산스 웹폰트로 사용하기](https://spoqa.github.io/2017/02/15/using-shs-as-webfonts.html)
- [스포카한산스 영숫자 서브셋](https://github.com/isangho/SpoqaHanSans-EN)
- [폰트툴즈의 pyftsubset을 사용한 폰트 서브셋 만들기](https://www.44bits.io/ko/post/optimization_webfont_with_pyftsubnet)
- [Webfont Generator Online](https://transfonter.org/)