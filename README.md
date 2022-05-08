# NextJs Introduction

# Library vs. Framework

Library : what I use as developer (내가 사용하는 것)

- 아무때나 원하는 대로 작성 가능  
  Framework : Call my code (내 코드를 불러옴)
- 특정한 규칙을 따라서 작성해야 작동함
- component의 이름은 중요하지 않음, **function을 export default 하는 것이 중요!!**
- 파일명이 url의 주소로 입력 - 앱의 home은 index.js에서 나옴 (따라서 url/index 페이지 없음)

# hydration

: react.js를 프론트엔드 안에서 실행하는 것  
 (next.js는 react.js를 백엔드에서 동작시켜서 페이지를 미리 생성 -> component를 render -> rendering이 끝나면 HTML로 됨 -> next.js는 그 HTML을 페이지의 소스코드에 넣음 => 유저는 자바스크립트와 react.js가 로딩되지 않았더라도 콘텐츠 볼 수 있음) => 나중에 react.js 로딩 되면 기존의 페이지와 연결되어서 일반적인 react.js처럼 작동함

# Route

이전의 바닐라js? 에서 사용하던 것처럼 <a href="/">Home<a>를 하게 되면 페이지를 이동할 때마다 전체 script가 재 로딩됨  
 따라서 Link사용

    <Link href="/">  // Link는 href를 위한 것, 다른 속성 넣을 수 없음
        <a className="hello", stylecolor="red">Home<a> // <a></a>가 꼭 필요한 것은 아니지만 속성을 넣기 위해 사용
    </Link>

# Styled JSX

component 새로 지정할 필요 없이 한 파일 내에서 css 가능  
한 파일에서 지정한 css style은 다른 파일에서 가져다 쓸 수 없음
      <style jsx>{`
          nav {
            background-color: green;
          }
          a {
            text-decoration: none;
          }
        `}</style>

=> 다른 컴포넌트에서 <style jsx global>{` ... `}하면 이미 지정된 style있어도 적용가능 (해당 페이지에서만)


# appComponent (_app.js)
페이지의 청사진 만들기
    export default function 파일 이름({ Component, pageProps}) {
        return <Component {...pageProps} />;
    }

컴포넌트에 css를 import하고 싶다면 module이어야 함
cf) 커스텀 app 컴포넌트에서는 css import 가능