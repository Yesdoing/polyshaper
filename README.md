# [Polyshaper](https://polyshaper.me/)

![Polyshaper](./public/image01.gif)

## Introduction
Polyshaper는 업로드한 이미지를 기반으로 색상을 자동으로 채워주어 일러스트레이터나 포토샵보다 편하고 빠르게 로우 폴리 이미지를 제작할 수 있는 로우 폴리 이미지 제작 어플리케이션입니다.

## Period
2018년 10월 20일 ~ 11월 2일

## Prerequisites
- Chrome Browser(권장)

## Installation
```
git clone https://github.com/kimkyeseung/polyshaper.git
npm install
npm start
```

## Feature
- 메인페이지에서 이미지를 업로드할 수 있습니다.
- 이미지 파일을 드래그 앤 드랍으로 업로드 할 수 있습니다.
- 이미지 업로드 후 마우스 클릭으로 점을 찍을 수 있습니다.
- 점이 세 개가 찍히면 자동으로 삼각형이 형성되고 해당 영역의 이미지 색상 평균 값으로 채워집니다.
- 만들어진 삼각 폴리에는 각 꼭지 점마다 스냅이 생겨 일정 거리 이내의 영역을 클릭하게 되면 점에 물리도록 되어있습니다.
- EditMode로 변경시 (단축키 : ```Ctrl(command) + E```) 만들어진 면의 영역을 수정할 수 있습니다. (기본 : AddMode)
- EditMode에서는  ```Ctrl(command) + E``` + 마우스 클릭으로 해당 셀을 직접 선택하여 색상을 원하는 색상으로 변경할 수 있습니다.

![Polyshaper](./public/image02.gif)

- ```Variance```와 ```Cellsize```를 조정하고 ```Auto Populate``` 기능으로 남은 배경을 자동으로 완성시킬 수 있습니다.
- ```Variance``` : 각 폴리 들의 랜덤한 정도를 조정합니다. 0 부터 1까지 입력 가능하며 0이면 모든 셀이 가지런한 정삼각형이, 1이면 불규칙적이고 자유도가 높은 모양이 됩니다. (기본 0.4)
- ```Cellsize``` : 각 폴리의 크기를 결정합니다. 셀의 크기가 작아질 수록 이미지의 선명도가 높아지지만 폴리아트의 느낌이 줄어들고 속도가 느려지게 됩니다. 기본 크기는 60px이며 최소 10px에서 최대 200px로 설정해두었습니다.
- AddMode에서 점을 찍고 삼각형을 완성시키지 않은채 에딧모드로 변경하면 점은 취소되어 사라집니다.
- AddMode에서 점을 찍고 삼각형을 완성시키지 않은채 ```Esc```를 누르면 점은 취소되어 사라집니다.
- ```Auto Populate``` 시에 생기는 폴리 이미지는 유저가 만든 폴리와는 별개로 컨트롤 되며 유저가 만든 폴리 아래에 있는 레이어로 취급됩니다.
- ```Download Image``` 버튼을 통하여 제작한 폴리 이미지를 저장할 수 있습니다.
- ```Reset Picture``` 버튼을 통하여 업로드한 이미지를 없애고 새로 이미지를 업로드할 수 있습니다.

![Polyshaper](./public/image03.gif)

## Tech Stack
- 자바스크립트(ES2015+)를 기본으로 제작하였습니다.
- Redux 라이브러리를 사용한 Flux 아키텍처 기반 설계를 하였습니다.
- React, Webpack, CSS Modules을 사용한 컴포넌트 베이스 UI 아키텍처를 구현하였습니다.
- HTML5 Canvas를 이용하여 그래픽 아트웍을 구현하였습니다.

## Continuous Integration
- 소스관리/빌드/테스트/배포의 지속적인 통합을 위한 CircleCI를 사용하였습니다.

## Deployment
netlify를 이용하여 github repository를 배포하였습니다.

## Version Control
- Client, Server의 GIT Repoitory를 구분하여 독립적인 관리를 하였습니다.

## Planning
- Trello를 이용하여 일정을 관리하여 진행하였습니다. 

## Test
Jest와 Enzyme를 이용하여 Reducer및 Component 단위 테스트 구현

## Things to do
2주 동안의 완성을 목표로 좀 더 완성도를 높은 어플리케이션을 구현하고 싶어 Server는 애초에 기획에서 제외하였습니다. 
가능한 정교하고 디테일하게 기능 구현을 하려고 하였으며 기능 구현 가능 여부가 불확실했던 상황이있었지만 잘 마무리 되어서 기쁘게 생각합니다.
처음 기획했던 기능을 구현하고 나서는 계속해서 단축키를 비롯한 디테일한 UI의 개선이 욕심이 있습니다.

- 배경 및 사용자 추가 폴리 레이어 시각화 및 개별 컨트롤 가능하게 하기 (포토샵처럼)
- 각 폴리 셀 별 테두리 두께 및 색상 입력 가능하게 하기 
- firebase 등을 이용하여 완성된 이미지 DB나 스토리지에 보관하여 갤러리 게시판 만들어 업로드하기
- 전반적인 UI 개선으로 좋은 사용자 경험 제시하기
- Code Refactoring
- Integration Test
