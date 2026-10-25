name: Gerar APK
on: workflow_dispatch
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: unzip -q EsticaTela.zip
      - uses: actions/setup-java@v4
        with:
          distribution: temurin
          java-version: 17
      - uses: gradle/actions/setup-gradle@v4
        with:
          gradle-version: 8.7
      - run: gradle assembleDebug --no-daemon -p EsticaTela
      - uses: actions/upload-artifact@v4
        with:
          name: EsticaTela-apk
          path: EsticaTela/app/build/outputs/apk/debug/app-debug.apk
