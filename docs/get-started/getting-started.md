# 설치 및 예제 실행

## 설치하기

deck.gl 프레임워크 설치하기:

```bash
npm install deck.gl --save
```

혹은

```bash
yarn add deck.gl
```

[deck.gl](https://www.npmjs.com/package/deck.gl) 모듈은 모든 deck.gl의 기능과 종속성이 포함하고 있습니다. 기능의 하위 항목을 선택 설치하려면 [의존성](#selectively-install-dependencies) 항목을 참조하세요.

## 예제 실행하기
deck.gl 레포지토리는 애플리케이션의 좋은 출발점이 될 수 있는 소규모 독립형 예제가 담긴 [예시 폴더](https://github.com/visgl/deck.gl/tree/master/examples)를 포함하고 있습니다.

이 폴더를 원하는 위치에 복사하고 다음과 같이 간단하게 실행할 수 있습니다:

deck.gl 레포지토리가 없다면 이를 복제하세요

```bash
git clone git@github.com:visgl/deck.gl.git
```

가장 안정적인 결과를 얻으려면 예제를 실행할 때 `master`브랜치 대신 최신 릴리즈 브랜치(예를 들어, `8.0-release`)를 확인하는것을 권장합니다.

```bash
git checkout 8.0-release
```

관심 있는 예제가 있는 폴더로 이동하세요.

```bash
cd deck.gl/examples/get-started/pure-js/basic
```

그 후 원하는 설치 프로그램을 사용하여 종속성을 설치하세요:

```bash
npm install
# or
yarn
```

이후 다음 명령어를 사용하여 실행하세요:

```bash
npm start
```

만약 예제가 mapbox 베이스 지도를 사용한다면 [Mapbox 접근권한 토큰(Mapbox access token)](./using-with-map.md)이 필요합니다.

```bash
export MapboxAccessToken={토큰을 여기에 넣으세요} && npm start
```

복제된 리포지토리에 있는 최신 deck.gl 소스 코드(예제의 `package.json`에 나열된 게시된 버전의 deck.gl이 아닌)를 기준으로 예제를 빌드하려면 다음과 같이 하세요.

```bash
npm run start-local
```

> `master` 브랜치의 예제들은 아직 출시되지 않은 최신 버전의 deck.gl의 기능을 사용하도록 업데이트 되었습니다. 일부 예제가 `npm start`를 통해 작동하지 않는 경우 `npm run start-local`명령어를 시도해 볼 수 있습니다.

> 모든 예제가 `npm run start-local`명령어를 지원하지만, 로컬 소스에 대해 실행할 때 몇가지 주의사항이 있습니다. 가장 중요한 것은, 예제 폴더에서 `npm run start-local`명령어를 실행하기 전에 deck.gl의 루트 폴더에서 `npm install`이나 `yarn`을 실행해야 한다는 것입니다.


## 종속성 선택하여 설치하기

NPM 모듈의 제품군은 deck.gl 프레임워크의 일부로 배포되었습니다. 아래 트리는 해당 모듈의 스코프와 종속성을 보여줍니다:

- `@deck.gl/core` - GPU 렌더링 파이프라인, 데이터 관리 및 사용자 상호작용을 처리하는 핵심 모듈
  + `@deck.gl/layers` -  모든 시각화의 기본 구성 요소인 원시 레이어
    * `@deck.gl/aggregation-layers` - 데이터를 히트맵, 등고선, 육각형 그리드 등의 대체 표현으로 합산하여 표현하는 고도화된 레이어입니다.
    * `@deck.gl/geo-layers` - 지리공간 유즈 케이스와 GIS 형식을 처리하는 부가적인 레이어입니다.
    * `@deck.gl/mesh-layers` - 3D 메시(mesh)와 [씬 그래프(scene graphs)](https://en.wikipedia.org/wiki/Scene_graph)들을 렌더링하는 부가적인 레이어입니다.
  + `@deck.gl/json` - JSON 형식을 사용하여 deck.gl 레이어와 보기(views)를 지원하는 선언적인 인터페이스입니다.
  + `@deck.gl/mapbox` -[Mapbox 사용자 지정 레이어(Mapbox custom layer)](../api-reference/mapbox/overview.md) API와 통합된 모듈입니다.
  + `@deck.gl/react` - deck.gl의 React wrapper입니다.
  + `@deck.gl/widgets` - 유용한 UI 컴포넌트를 포함하고 있습니다.
  + `@deck.gl/test-utils` - 테스팅 도구들을 제공합니다.


예를 들어, `PointCloudLayer`를 렌더링하고 싶으면 다음과 같이 설치를 진행해야 합니다:

```bash
yarn add @deck.gl/core @deck.gl/layers
```

React에서 `HexagonLayer`를 사용하려면, 다음과 같이 설치를 진행해야 합니다.

```bash
yarn add @deck.gl/core @deck.gl/layers @deck.gl/aggregation-layers @deck.gl/react
```

하위 모듈을 별도로 설치하면 애플리케이션이 가져오는 종속성을 최대한 제어할 수 있지만, 일관적인 결과를 생성하려면 하위 모듈 버전을 수동으로 동기화해야 합니다.

`deck.gl` 마스터 모듈은 `@deck.gl/test-utils`를 제외한 모든 서브모듈을 포함하고 있습니다. 대부분의 번들링 해결책 (Webpack, Rollup 등)은 운영 빌드에서 사용되지 않는 내보내기를 제외한 트리 쉐이킹 기능(tree-shaking)을 제공합니다.

