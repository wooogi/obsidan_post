CSS를 작성하다보면 "~이 없을 경우"와같이 특정 선택자가 없을 때에 대한 스타일 처리를 하고 싶은 경우가 생깁니다. 이번 포스팅에서는 특정 선택자가 포함되어 있지 않는 요소에 대하여 스타일을 적용하기 위한 방법에 대해 소개하도록 하겠습니다.

### :not() 선택자

CSS :not() 선택자는 부정(negation) CSS 가상클래스로CSS의 :not() 선택자를 사용하면 특정 선택자가 제외된 경우에 대한 스타일 적용을 할 수 있습니다. 일반적으로 선택자(selector)를 해당 요소를 선택하기 위해 사용되지만 not 선택자는 해당 선택자를 제외한 나머지 요소를 선택하기 위해 사용합니다. not 선택자를 활용하면 실무에서 꽤 유용하게 사용되는 경우가 많기 때문에 알아두면 작업하는데 많이 도움이 될 것입니다.

### 사용방법

:not() 선택자를 사용하는 방법은 굉장히 간단합니다. 선택자에 **:not({selector})** 형태로 사용하면 됩니다. 글보다는 코드로 보는게 훨씬 이해가 쉬울 것입니다! 아래는 :not() 선택자를 활용한 코드 예시입니다. 아래 예시는 html li 태그에서 active 클래스 선택자를 포함하지 않는 요소에 스타일을 적용하는 예시입니다.

```html
// html 예시
<ul>
  <li>not 선택자 예시 1</li>
  <li class="active">not 선택자 예시 2</li>
  <li>not 선택자 예시 3</li>  
</ul>
```

```css
/*CSS*/
ul li:not(.active) {
  color: red;
}
```

### 결과

active 클래스 선택자가 없는 1번째, 3번째 요소에만 빨간색 색상이 적용된 것을 확인할 수 있습니다.

[https://codepen.io/dsonesof-the-vuer/pen/WNzJNaE](https://codepen.io/dsonesof-the-vuer/pen/WNzJNaE)

### :not 선택자 응용 예시

위 예시에서 클래스 선택자를 활용해서 스타일을 적용해 봤는데, 클래스 선택자 말고도 다른 선택자를 활용해서 응용할 수 있습니다. 클래스가 아닌 다른 속성 등에도 사용할 수 있는데요. 예를 들어 img 태그의 src 속성이 존재하지 않을 경우에 대한 스타일 처리가 가능합니다. img 태그의 src 속성이 존재하지 않을 경우 img 기본 백그라운드 색상이 f7f7f7 컬러코드로 적용되는 것을 확인할 수 있습니다.

```html
<img src="<https://blog.kakaocdn.net/dn/EkMuZ/btqTKMVy1Hd/mdDQDZGdcKAd5MtgTO2OWk/img.png>">
<img>
```

```css
img {width: 240px;height: 240px;}
img:not(src) {background-color: #f7f7f7;}
```

<iframe src="https://codepen.io/dsonesof-the-vuer/pen/ExELxOG" style="width:100%; height:400px;"></iframe>

<iframe height="300" style="width: 100%;" scrolling="no" title="Untitled" src="https://codepen.io/dsonesof-the-vuer/embed/ExELxOG?default-tab=html%2Cresult" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/dsonesof-the-vuer/pen/ExELxOG">
  Untitled</a> by 김동욱 (<a href="https://codepen.io/dsonesof-the-vuer">@dsonesof-the-vuer</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>

![](https://codepen.io/dsonesof-the-vuer/pen/ExELxOG)
![[https://codepen.io/dsonesof-the-vuer/pen/ExELxOG]]
[https://codepen.io/dsonesof-the-vuer/pen/ExELxOG](https://codepen.io/dsonesof-the-vuer/pen/ExELxOG)

### 정리

몇 가지 예시를 통해 :not() 선택자의 기본 동작 원리에 대해서 살펴봤는데, 실무에서도 굉장히 유용하게 쓰이는 선택자인 만큼 사용 방법에 대해서 숙지하고 있으면 작업할 때 굉장히 유용하게 쓰일 것입니다.
