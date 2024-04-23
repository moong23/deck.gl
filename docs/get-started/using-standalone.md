# deck.gl 단독으로 사용하기

deck.gl 코어 라이브러리와 레이어는 React, Mapbox GL, MapLibre GL에 대한 종속성이 없으며, 모든 자바스크립트 어플리케이션에서 사용할 수 있습니다.

[시작하기 예제](https://github.com/visgl/deck.gl/tree/master/examples/get-started)는 어플리케이션의 시작점으로 사용할 수 있는 바닐라 자바스크립트 템플릿들이 포함하고 있습니다.


## @deck.gl/core 사용하기

` @deck.gl/core`는 React에 의존성이 없는 deck.gl의 하위모듈입니다.

[Deck](../api-reference/core/deck.md) 클래스는 deck.gl 레이어 인스턴스와 뷰포트 매개변수를 가져와서 해당 레이어를 투명한 오버레이로 렌더링합니다.

```bash
npm install @deck.gl/core @deck.gl/layers
```

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs groupId="language">
  <TabItem value="js" label="JavaScript">

```js
import {Deck} from '@deck.gl/core';
import {ScatterplotLayer} from '@deck.gl/layers';

const INITIAL_VIEW_STATE = {
  latitude: 37.8,
  longitude: -122.45,
  zoom: 15
};

const deckInstance = new Deck({
  initialViewState: INITIAL_VIEW_STATE,
  controller: true,
  layers: [
    new ScatterplotLayer({
      data: [
        {position: [-122.45, 37.8], color: [255, 0, 0], radius: 100}
      ],
      getPosition: d => d.position,
      getFillColor: d => d.color,
      getRadius: d => d.radius
    })
  ]
});
```

  </TabItem>
  <TabItem value="ts" label="TypeScript">

```ts
import {Deck, MapViewState} from '@deck.gl/core';
import {ScatterplotLayer} from '@deck.gl/layers';

const INITIAL_VIEW_STATE: MapViewState = {
  latitude: 37.8,
  longitude: -122.45,
  zoom: 15
};

type DataType = {
  position: [longitude: number, latitude: number];
  color: [r: number, g: number, b: number];
  radius: number;
};

const deckInstance = new Deck({
  initialViewState: INITIAL_VIEW_STATE,
  controller: true,
  layers: [
    new ScatterplotLayer<DataType>({
      data: [
        {position: [-122.45, 37.8], color: [255, 0, 0], radius: 100}
      ],
      getPosition: (d: DataType) => d.position,
      getFillColor: (d: DataType) => d.color,
      getRadius: (d: DataType) => d.radius
    })
  ]
});
```

  </TabItem>
</Tabs>


## 스크립팅 API 사용하기

deck.gl은 d3.js와 같은 네이티브 자바스크립트 스크립팅 인터페이스인 독립 실행형 버전의 라이브러리도 제공합니다. [Codepen](https://codepen.io), [JSFiddle](https://jsfiddle.net) 그리고 [Observable](https://observablehq.com)와 같은 프로토타입 환경에서 deck.gl을 사용할 수 있습니다. 이러한 노력은 디자이너, 창의적인 개발자, 데이터 과학자 등 모든 사람이 상호작용형 시각화를 위해 GPU를 더 쉽게 사용할 수 있도록 하는 것을 목표로 합니다. 스크립팅 API는 [Mapbox GL JS](https://mapbox.com) 이나 [MapLibre GL JS](https://maplibre.org)과 즉시 통합할 수 있습니다. 시각화를 기본 지도에 추가하려면 기본 지도 라이브러리와 스타일시트를 포함해야 합니다:

deck.gl을 스크립팅 환경에서 사용하려면 `script`태그에 독립실행형 버전을 포함하세요.

<Tabs groupId="map-library">
  <TabItem value="mapbox" label="Mapbox">

```html
<script src="https://unpkg.com/deck.gl@latest/dist.min.js"></script>
<!-- optional if mapbox base map is needed -->
<script src="https://api.mapbox.com/mapbox-gl-js/v3.2.0/mapbox-gl.js"></script>
<link href="https://api.mapbox.com/mapbox-gl-js/v3.2.0/mapbox-gl.css" rel="stylesheet" />
<!-- Allow the map to render in full screen  -->
<style>
  body {
    width: 100vw;
    height: 100vh;
    margin: 0;
  }
</style>
```

  </TabItem>
  <TabItem value="maplibre" label="MapLibre">

```html
<script src="https://unpkg.com/deck.gl@latest/dist.min.js"></script>
<!-- optional if maplibre base map is needed -->
<script src="https://unpkg.com/maplibre-gl@3.0.0/dist/maplibre-gl.js"></script>
<link href="https://unpkg.com/maplibre-gl@3.0.0/dist/maplibre-gl.css" rel="stylesheet" />
<!-- Allow the map to render in full screen  -->
<style>
  body {
    width: 100vw;
    height: 100vh;
    margin: 0;
  }
</style>
```

  </TabItem>
</Tabs>

이는 두개의 전역 객체인 `deck`과 `luma`를 노출시킵니다. deck.gl 코어에서 내보내진 모든 것들은 `deck.<Class>`으로 접근할 수 있습니다.

스크립팅 API의 [DeckGL](../api-reference/core/deckgl.md) 클래스는 Mapbox나 MapLibre 통합과 같은 몇가지 추가적인 기능과 함께 코어 `Deck` 클래스를 확장합니다.

<Tabs groupId="map-library">
  <TabItem value="mapbox" label="Mapbox">

```js
//This example renders a scatterplot with DeckGL, on top of a basemap rendered with mapbox-gl, using a map style JSON from Carto.
const {DeckGL, ScatterplotLayer} = deck;

new DeckGL({
  mapboxApiAccessToken: '<mapbox-access-token>',
  mapStyle: 'mapbox://styles/mapbox/light-v9',
  initialViewState: {
    longitude: -122.45,
    latitude: 37.8,
    zoom: 15
  },
  controller: true,
  layers: [
    new ScatterplotLayer({
      data: [
        {position: [-122.45, 37.8], color: [255, 0, 0], radius: 100}
      ],
      getPosition: d => d.position,
      getFillColor: d => d.color,
      getRadius: d => d.radius
    })
  ]
});
```

  </TabItem>
  <TabItem value="maplibre" label="MapLibre">

```js
//This example renders a scatterplot with DeckGL, on top of a basemap rendered with maplibre-gl, using a map style JSON from Carto.
const {DeckGL, ScatterplotLayer} = deck;

new DeckGL({
  mapStyle: 'https://basemaps.cartocdn.com/gl/positron-nolabels-gl-style/style.json',
  initialViewState: {
    longitude: -122.45,
    latitude: 37.8,
    zoom: 15
  },
  controller: true,
  layers: [
    new ScatterplotLayer({
      data: [
        {position: [-122.45, 37.8], color: [255, 0, 0], radius: 100}
      ],
      getPosition: d => d.position,
      getFillColor: d => d.color,
      getRadius: d => d.radius
    })
  ]
});
```

  </TabItem>
</Tabs>

codepen [시연](https://codepen.io/vis-gl)과 [observable 프로필](https://beta.observablehq.com/@pessimistress)에서 예시를 확인하세요.
