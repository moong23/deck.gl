<p align="right">
  <a href="https://npmjs.org/package/deck.gl">
    <img src="https://img.shields.io/npm/v/deck.gl.svg?style=flat-square" alt="version" />
  </a>
  <a href="https://github.com/visgl/deck.gl/actions?query=workflow%3Atest+branch%3Amaster">
    <img src="https://github.com/visgl/deck.gl/workflows/test/badge.svg?branch=master" alt="build" />
  </a>
  <a href="https://npmjs.org/package/deck.gl">
    <img src="https://img.shields.io/npm/dm/@deck.gl/core.svg?style=flat-square" alt="downloads" />
  </a>
  <a href='https://coveralls.io/github/visgl/deck.gl?branch=master'>
    <img src='https://img.shields.io/coveralls/visgl/deck.gl.svg?style=flat-square' alt='Coverage Status' />
  </a>
</p>

<h1 align="center">deck.gl | <a href="https://deck.gl">홈페이지</a></h1>

<h5 align="center"> GPU기반의 고성능 대규모 데이터 시각화 </h5>

[![docs](http://i.imgur.com/mvfvgf0.jpg)](https://visgl.github.io/deck.gl)


deck.gl은 대규모 데이터셋의 고성능 WebGL2/WebGPU 기반 시각화 작업을 단순화하도록 설계되었습니다. 사용자는 기존 레이어를 활용하거나 deck.gl의 확장 가능한 아키텍처를 활용하여 사용자 맞춤형 요구사항을 충족하는 강렬한 시각적 결과물을 최소한의 작업을 통해 빠르게 얻어낼 수 있습니다.

deck.gl은 **데이터** (일반적으로 JSON 객체 배열) 를 시각적 아이콘, 다각형, 텍스트와 같은 **레이어**의 스택으로 매핑하고 지도, 1인칭, 정사영과 같은 **보기방식**을 통해 이를 확인합니다.

deck.gl은 여러 가지 문제를 추가 설치 없이 처리할 수 있습니다:

* 대용량 데이터셋의 고성능 렌더링 및 업데이트
* 선택, 강조, 필터링하기와 같은 상호작용 이벤트 처리
* 지도 투영 및 주요 베이스 지도 제공업체와의 통합
* 충분한 테스트를 거친 검증된 레이어 카탈로그

Deck.gl은 사용자가 자유롭게 커스터마이징할 수 있게 설계되었습니다. 모든 레이어는 렌더링 각 측면을 프로그래밍 방식으로 제어할 수 있는 유연한 API들과 함께 제공됩니다. 모든 핵심 클래스들은 사용자가 사용자 정의 유즈케이스들을 해결하기 위해 쉽게 확장할 수 있습니다.

## 구성

### Script 태그

```html
<script src="https://unpkg.com/deck.gl@latest/dist.min.js"></script>
```

- [시작하기](/docs/get-started/using-standalone.md#using-the-scripting-api)
- [전체 예시](https://github.com/visgl/deck.gl/tree/master/examples/get-started/scripting)

### NPM 모듈

```bash
npm install deck.gl
```

#### 순수 JS

- [시작하기](/docs/get-started/using-standalone.md)
- [전체 예시](/examples/get-started/pure-js)

#### React

- [시작하기](/docs/get-started/using-with-react.md)
- [전체 예시](/examples/get-started/react)

### Python

```bash
pip install pydeck
```

- [시작하기](https://deckgl.readthedocs.io/en/latest/installation.html)
- [예시](https://deckgl.readthedocs.io/en/latest/layer.html)

### 타사 상품

- [deckgl-typings](https://github.com/danmarshall/deckgl-typings) (Typescript)
- [mapdeck](https://symbolixau.github.io/mapdeck/articles/mapdeck.html) (R)
- [vega-deck.gl](https://github.com/microsoft/SandDance/tree/master/packages/vega-deck.gl) ([Vega](https://vega.github.io/))
- [earthengine-layers](https://earthengine-layers.com/) ([구글어스 엔진](https://earthengine.google.com/))
- [deck.gl-native](https://github.com/UnfoldedInc/deck.gl-native) (C++)
- [deck.gl-raster](https://github.com/kylebarron/deck.gl-raster/) (raster에서의 연산)

## 학습 자료

* [API 문서](https://deck.gl/#/documentation) 에서 최신 배포버전을 확인하세요
* [웹사이트 시연](https://deck.gl/#/examples) 소스 링크 포함
* [상호작용 플레이그라운드](https://deck.gl/playground)
* [deck.gl Codepen 시연](https://codepen.io/vis-gl/)
* [deck.gl Observable 시연](https://beta.observablehq.com/@pessimistress)
* [vis.gl Medium 블로그](https://medium.com/vis-gl)
* [deck.gl Slack 작업공간](https://slack-invite.openjsf.org/)

## 기여하기

deck.gl은 [OpenJS 재단](https://openjsf.org/) 프로젝트인 vls.gl의 일부입니다. 기여에 관심이 있으시면 [기여 가이드라인](/CONTRIBUTING.md) 을 읽어보세요.


## 어트리뷰션

#### 데이터 원본

각 예제에는 데이터 원본들이 나열되어 있습니다.

#### deck.gl 프로젝트는 다음과 같은 곳에서 지원받고 있습니다.

<a href="https://www.unfolded.ai"><img src="https://raw.githubusercontent.com/visgl/deck.gl-data/master/images/branding/unfolded.png" height="32" /></a>
<a href="https://www.foursquare.com"><img src="https://raw.githubusercontent.com/visgl/deck.gl-data/master/images/branding/fsq.svg" height="40" /></a>

<a href="https://www.carto.com"><img src="https://raw.githubusercontent.com/visgl/deck.gl-data/master/images/branding/carto.svg" height="48" /></a>

<a href="https://www.mapbox.com"><img src="https://raw.githubusercontent.com/visgl/deck.gl-data/master/images/branding/mapbox.svg" height="44" /></a>
<a href="https://www.uber.com"><img src="https://raw.githubusercontent.com/visgl/deck.gl-data/master/images/branding/uber.png" height="40" /></a>

<a href="https://www.browserstack.com/"><img src="https://d98b8t1nnulk5.cloudfront.net/production/images/static/logo.svg" alt="BrowserStack" width="200" /></a>
