# yomojomo-models

[요모조모](https://github.com/sohee0401/yomojomo) 앱이 기기 안에서 쓰는 AI 모델 파일을 배포하는 저장소입니다.
모델 파일은 저장소가 아니라 **Releases**에 올려 둡니다.

## Gemma 4 E2B IT (QAT, UD-Q4_K_XL)

릴리스: [`gemma-4-e2b-it-qat-q4kxl`](https://github.com/sohee0401/yomojomo-models/releases/tag/gemma-4-e2b-it-qat-q4kxl)

| 파일 | 크기 (bytes) | SHA-256 |
|---|---|---|
| `gemma-4-E2B-it-qat-UD-Q4_K_XL-00001-of-00002.gguf` | 1,344,739,200 | `a63101bee719ae80e141f4b5fa34173306f5d2a053ff1ef20784c7825058d931` |
| `gemma-4-E2B-it-qat-UD-Q4_K_XL-00002-of-00002.gguf` | 1,275,631,968 | `4c54e332c98f1f12476764c3e8a680c4995ce1f24ee3c4d3f4c304f92c881c1c` |

- GitHub 릴리스 파일은 하나에 2 GiB까지라서 llama.cpp `llama-gguf-split`로 두 조각으로 나눴습니다.
- 두 파일을 같은 폴더에 두고 **첫 번째 파일 경로**로 불러오면 llama.cpp(llama.rn)가 나머지 조각을 함께 읽습니다. 합칠 필요는 없습니다.
- 앱에서는 질문 답변(“요모조모에게 물어보기”)에만 씁니다. 텍스트 전용이라 이미지용 `mmproj` 파일은 넣지 않았습니다.

### 출처

- 원본 모델: [google/gemma-4-E2B-it](https://huggingface.co/google/gemma-4-E2B-it) (Google)
- 양자화: [unsloth/gemma-4-E2B-it-qat-GGUF](https://huggingface.co/unsloth/gemma-4-E2B-it-qat-GGUF)의 `gemma-4-E2B-it-qat-UD-Q4_K_XL.gguf`
  (SHA-256 `e531007218dfab990486a5de7676a6932d6ea8dea233d1f698d7c21cf8a16889`, 2,620,370,976 bytes)
- 나누기: llama.cpp b11146 `llama-gguf-split --split --split-max-size 1400M`. 텐서와 메타데이터는 바꾸지 않았습니다.

### 라이선스

Gemma 4는 Apache License 2.0으로 배포됩니다 ([Gemma 4 license](https://ai.google.dev/gemma/docs/gemma_4_license)).
이 저장소의 파일도 같은 [Apache License 2.0](LICENSE)을 따릅니다.
