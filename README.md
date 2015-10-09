aheui-llvm
========
이 프로그램은 아희 코드를 llvm IR로 변환해주는 컴파일러 프론트엔드입니다.
Rust 언어로 짜여져 있으며, 예제 런타임 라이브러리 역시 Rust로 짜여져 있습니다.

### 사용법
1.  aheui-llvm을 실행하여, 아희 소스코드의 LLVM IR을 얻습니다.
    ```
    cargo run -- README.md
    ```

1.  llc로 이를 빌드하여 object 파일을 얻습니다.
    ```
    llc -filetype=obj -relocation-model=pic README.md.ll
    ```

1.  `make rt`로 `librt-####-0.0.rlib` 라이브러리를 얻습니다.
1.  `rustc -o hello rtmain.rs -L . -C link-args="README.md.o"`를 하면
    `hello` 실행 파일이 나옵니다.

이에 대한 예제로 `make hello`가 준비되어 있습니다.

```
밤밣따빠밣밟따뿌
빠맣파빨받밤뚜뭏
돋밬탕빠맣붏두붇
볻뫃박발뚷투뭏붖
뫃도뫃희멓뭏뭏붘
뫃봌토범더벌뿌뚜
뽑뽀멓멓더벓뻐뚠
뽀덩벐멓뻐덕더벅
```
