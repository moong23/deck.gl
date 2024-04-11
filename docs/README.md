# 소개

<p align="center">
  이 문서는 
  <a href="https://github.com/visgl/deck.gl/blob/9.0-release/docs/README.md">
    <img src="https://img.shields.io/badge/deck.gl-v9.0-brightgreen.svg?style=flat-square" />
  </a>
  를 위해 작성되었습니다.
  더 오래된 버전을 찾으시나요?
  <a href="https://github.com/visgl/deck.gl/blob/8.9-release/docs/README.md">
    <img src="https://img.shields.io/badge/deck.gl-v8.x-brightgreen.svg?style=flat-square" />
  </a>
  <a href="https://github.com/visgl/deck.gl/blob/7.3-release/docs/README.md">
    <img src="https://img.shields.io/badge/deck.gl-v7.x-green.svg?style=flat-square" />
  </a>
  <a href="https://github.com/visgl/deck.gl/blob/6.4-release/docs/README.md">
    <img src="https://img.shields.io/badge/deck.gl-v6.x-green.svg?style=flat-square" />
  </a>
</p>


deck.gl은 대규모 데이터셋의 고성능 WebGL2/WebGPU 기반 시각화 작업을 단순화하도록 설계되었습니다. 사용자는 기존 레이어를 활용하거나 deck.gl의 확장 가능한 아키텍처를 활용하여 사용자 맞춤형 요구사항을 충족하는 강렬한 시각적 결과물을 최소한의 작업을 통해 빠르게 얻어낼 수 있습니다.

deck.gl은 **데이터** (일반적으로 JSON 객체 배열)를 시각적 아이콘, 다각형, 텍스트와 같은 **레이어**의 스택으로 매핑하고 지도, 1인칭, 정사영과 같은 **보기방식**을 통해 이를 확인합니다.

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

- [시작하기](./get-started/using-standalone.md#using-the-scripting-api)
- [전체 예시](https://github.com/visgl/deck.gl/tree/master/examples/get-started/scripting)

### NPM 모듈

```bash
npm install deck.gl
```

#### Pure JS

- [시작하기](./get-started/using-standalone.md)
- [전체 예시](https://github.com/visgl/deck.gl/tree/master/examples/get-started/pure-js)

#### React

- [시작하기](./get-started/using-with-react.md)
- [전체 예시](https://github.com/visgl/deck.gl/tree/master/examples/get-started/react)

### Python

```bash
pip install pydeck
```

- [시작하기](https://pydeck.gl/installation.html)
- [예시](https://pydeck.gl/)

### 타사 상품

- [deckgl-typings](https://github.com/danmarshall/deckgl-typings) (Typescript)
- [mapdeck](https://symbolixau.github.io/mapdeck/articles/mapdeck.html) (R)
- [vega-deck.gl](https://github.com/microsoft/SandDance/tree/master/packages/vega-deck.gl) ([Vega](https://vega.github.io/))
- [earthengine-layers](https://earthengine-layers.com/) ([구글 어스 엔진](https://earthengine.google.com/))
- [deck.gl-native](https://github.com/UnfoldedInc/deck.gl-native) (C++)

## 생태계

deck.gl은 [vis.gl](http://vis.gl) 프레임워크 제품모음의 주요 프레임워크중 하나입니다.

deck.gl은 다음과 같은 여러 동료 모듈들과 함께 개발되었습니다:

* [luma.gl](https://luma.gl/) - 범용 WebGL2/WebGPU 라이브러리로, (가능한 한) 원시 브라우저 API는 물론 다른 WebGL2/WebGPU 라이브러리와도 상호 정보 교환이 가능하도록 설계되었습니다. 특히 luma.gl은 WebGL2/WebGPU 문맥의 소유권을 주장하지 않으며, 애플리케이션이나 다른 라이브러리에서 만든 문맥을 포함하여 제공된 모든 문맥과 함께 작동할 수 있습니다.
* [loaders.gl](https://loaders.gl) - 포인트 클라우드, 3D 지오메트리, 이미지, 지리공간 형식 및 표 형식 데이터를 포함한 빅데이터 시각화에 중점을 둔 파일 형식용 프레임워크-독립적 로더 모음입니다.
* [react-map-gl](https://visgl.github.io/react-map-gl) - deck.gl과 원활하게 작동하는 Mapbox GL을 감싸는 React wrapper입니다. 필요한 기능에 따라 두가지 통합 모드를 선택할 수 있으며, 자세한 내용은 [Mapbox와 함께 사용하기](./developer-guide/base-maps/using-with-mapbox.md#react-map-gl)를 참조하세요.
* [nebula.gl](https://nebula.gl/) - deck.gl용 고성능 기능 편집 프레임워크입니다.

## deck.gl에 대해 알아보기

deck.gl에 대한 학습 방법은 사전 지식과 사용 목적에 따라 달라집니다.

다양한 레이어들과 그들의 속성에 익숙해지고 deck.gl 개발자 가이드의 기본 문서를 읽는 것이 첫 번째 단계 중 하나입니다.

deck.gl 예제들을 살펴보는 것도 좋은 출발점입니다.

deck.gl 애플리케이션을 개발하는 방법에 대한 심층적인 튜토리얼은 [Vis Academy](http://vis.academy/) 웹사이트에서 확인할 수 있습니다.

또한 [블로그](https://medium.com/vis-gl)에는 도움이 될 만한 추가 정보가 많이 있습니다.

그 다음에는 어디로 가야 할까요?

### 반응형 UI 프로그래밍 배우기

deck.gl은 React와 같은 프레임워크에 의해 대중화된 함수형 UI 프로그래밍 원칙에 의해 설계되었습니다. 고성능의 deck.gl 애플리케이션과 레이어를 작성하기 위한 핵심은 업데이트와 중복 계산을 최소화하는 방법을 알고 "얕은 동등성(shallow equality)"과 같은 개념을 이해하는 데 있습니다. 이는 React와 함께 deck.gl를 사용할 때 중요하지만, React가 아닌 환경에서 deck.gl를 사용할 때도 이해하면 도움이 될 수 있습니다.

반응형 프로그래밍 패러다임에 관한 정보(문서, 블로그 게시물, 교육용 비디오 등)는 React, Flux, Redux와 같은 최신 웹 프레임워크와 관련하여 상당히 많이 있습니다. 어디서부터 시작해야 할지는 주로 애플리케이션 아키텍처 선택에 따라 달라집니다. 이러한 정보를 탐색하면 기본 deck.gl 개발자 가이드 문서인 업데이트(Update)에서 다룰 수 있는 내용을 초월하는 정보를 얻을 수 있습니다.

### WebGL2/WebGPU에 대해 이해하기

WebGL2 또는 WebGPU에 대한 지식은 deck.gl에서 사용자 정의 레이어를 만들려는 경우에만 필요합니다. 새 레이어에 대한 새롭고 야심찬 렌더링 접근 방식을 시도하려면 더 깊은 지식이 필요할 수 있지만, 놀랍게도 적은 양의 WebGL2/WebGPU 지식으로도 기존 deck.gl 레이어를 수정하거나 확장(셰이더 코드 수정 포함)할 수 있는 경우가 많습니다.

WebGL2/WebGPU에 대해 학습할 수 있는 웹 자료가 많이 있습니다. [luma.gl](https://luma.gl/)이 좋은 시작점이 될 수 있습니다.