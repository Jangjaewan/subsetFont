# Subset font

서브셋 글리프를 활용해 경량화된 웹폰트 파일 생성 (ttf, woff, woff2)   
포함된 스크립트를 사용하기 위해선  <code>Python</code>과 FontTools의 <code>pyftsubset</code>라이브러리 설치 필요

## 사용방법 및 참고 링크
	
1. 시스템에 파이썬 설치

아래 리스트를 참고하여 폰트 파일의 이름에 추가 및 수정
Black = 900
ExtraBold = 800
Bold = 700
SemiBold = 600
Medium = 500
Regular = 400
Light = 300
ExtraLight = 200
Thin = 100


bash 파일 실행 시 매개변수
EX) bash build_subset [kr/google] [폰트이름(폴더명)] [ttf/otf] [옵션 nonKr / onlyKr / onlyEn / onlyNum ] [옵션 full / kr ]
$1 : kr || google
$2 : 폰트이름
$3 : 폰트 확장자 [otf / ttf]
$4 : default : glyphs
       옵션 [nonKr / onlyKr / onlyEn / onlyNum]
       폰트파일에서 선택된 문자열만 추출하여 폰트로 생성한다.
$5 : unicode type  full - (나눔고딕 기준 119개) || kr - (노토 KR 기준 92개) 옵션. 아무것도 쓰지 않으면 텍스트파일 기준으로 만듬


Make CSS파일
kr 타입만 생성 됩니다.
argument [font-weight1 font-weight2.... font-name]
ex) bash make_css GmarketSans
폰트명에 포함된 특정 문자에 따라 폰트 굵기 설정
Black = 900
ExtraBold = 800
Bold = 700
SemiBold = 600
Medium = 500
Regular = 400
Light = 300
ExtraLight = 200
Thin = 100



## 참고 링크

- [웹폰트, 가볍게 최적화 하기 - 스포카 한산스](https://brunch.co.kr/@kimdal/4)
- [스포카 한 산스 웹폰트로 사용하기](https://spoqa.github.io/2017/02/15/using-shs-as-webfonts.html)
- [스포카한산스 영숫자 서브셋](https://github.com/isangho/SpoqaHanSans-EN)
- [폰트툴즈의 pyftsubset을 사용한 폰트 서브셋 만들기](https://www.44bits.io/ko/post/optimization_webfont_with_pyftsubnet)
- [Webfont Generator Online](https://transfonter.org/)