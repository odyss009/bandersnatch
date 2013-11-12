# 사용법

Node.js와 Pandoc의 설치가 필요합니다. 각각의 설치 내용은 공식 웹 사이트를 참조하십시오.

* [Node.js](http://nodejs.org/)
* [Pandoc](http://johnmacfarlane.net/pandoc/)

또한 작업을 수행하는 Grunt를 이용하고 있기 때문에, Grunt이 들어 있지 않은 경우 설치하십시오

    npm install -g grunt-cli

## 프로젝트 만들기

임의의 디렉토리에 bandersnatch을 적당한 디렉토리 이름 clone합니다.

    git clone https://github.com/sansyo/bandersnatch.git sample

파일 세트를 취득 할 수 있으면, Grunt 작업을 수행하는 node_modules를 설치합니다.

    cd sample && npm install

이것으로 준비 완료입니다.

## 원고 작성

source 디렉토리 slides.md이 원본 파일입니다.

## Pandoc 의한 변환

Pandoc의 변환은 Grunt 통해 실행합니다.

    cd sample
    grunt

※ sample 디렉토리에있는 경우 cd 실행하지 않아도됩니다.

## 공개용 파일 생성

불필요한 파일을 제외한 공개 디렉토리 (기본 이름 : presentation )을 만들고 동시에 아카이브를 만듭니다.

    grunt dist
