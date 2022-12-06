# mono-berry

yarn berry 를 이용해서 monorepo 를 구성해 본 프로젝트.
monorepo란 [여러 개의 개별 프로젝트를 **잘 정의된 관계**를 통해서 하나의 repo에 담은 것](https://news.hada.io/topic?id=6061)을 말함.

# How to

## yarn 설정하기

1. 로컬에 yarn이 설치되어 있지 않다면 설치.

```bash
npm install -g yarn
```

2. 프로젝트에서 yarn berry를 사용하도록 설정. (pwd 프로젝트 파일의 root에서 설정합니다)

```bash
yarn set version berry
```

berry 설정 후 프로젝트 내부에서 `yarn -v`으로 yarn 버전 확인시 v2 이상으로 깔렸음을 확인 할 수 있음.

3. yarn 프로젝트 초기화.

```bash
yarn init -w
```

`-w` flag와 함께 초기화해주면 `package.json` 파일이 자동 생성됨.
프로젝트 root에 위치한 `package.json`의 `workspace`에 추가된 위치들을 개별 프로젝트로 취급함.
위 커맨드로 `package.json` 생성시 workspace에 이미 `packages` 라는 폴더 위치가 추가되어 있음.

## workspace 추가하기

1. 원하는 위치에 하위 폴더를 생성한다.
2. `./packages.json` 의 workspace에 해당 위치를 추가한다.

그러고나면 `yarn workspace [프로젝트 이름]` 으로 접근할 수 있다.
