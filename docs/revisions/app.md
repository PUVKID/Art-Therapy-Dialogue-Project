<a id="-그림-자료--대화와-pdf를-연결하는-기본-앱"></a>

# 그림 자료 · 대화와 PDF를 연결하는 기본 앱

그림 업로드→YOLO 탐지 여부→상담형 메시지→PDF를 Gradio 화면에서 연결하는 노트북 앱입니다. 텍스트 질문 버튼은 별도 요청을 처리합니다.

분야: 컴퓨터 비전·자연어 처리 › YOLO·Gradio › 탐지 요약과 대화·보고서

[목적](#purpose) · [기능](#features) · [입출력](#flow) · [구성](#files) · [준비](#setup) · [사용법](#usage) · [결과](#results) · [제약](#limits) · [변경](#changes)

<a name="purpose"></a>

<a id="-이-단계에서-하는-일"></a>

## 연구 목적

모델로 전달하는 그림 분석 정보는 탐지 성공·실패와 시각을 담은 텍스트입니다. 그림 원본이나 상세 좌표를 언어 모델이 직접 보는 요청과는 구분됩니다.

<a name="features"></a>

<a id="-주요-기능과-처리-방식"></a>

## 방법과 구현

| 구성 | 실제 역할 |
| --- | --- |
| 그림 분석 | analyze_and_suggest가 RGB를 BGR로 바꾸어 저장하고 YOLO를 호출합니다. |
| 탐지 조건 | conf0.05·imgsz640으로 검출한 상자의 존재를 요약합니다. |
| 별도 질문 | ask_gpt는 질문 한 건만 보내며 이전 그림·대화 이력을 자동결합하지 않습니다. |
| PDF | build_pdf가 분석 요약·생성 메시지·입력 그림을 A4에 저장합니다. |

<a name="flow"></a>

<a id="-입력--처리--출력"></a>

## 입력·처리·출력

| 입력 | 처리 | 출력 |
| --- | --- | --- |
| 그림 업로드 | 임시 JPEG 저장·YOLO추론 | 탐지 여부와시각 |
| 탐지 요약 | gpt-4o-mini 텍스트 요청 | 상담형 메시지 |
| 그림·요약·메시지 | FPDF 문서 생성 | 입력 그림 표시와 PDF다운로드 |

<a name="files"></a>

<a id="-파일과-핵심-처리"></a>

## 파일별 역할

| 파일 | 이용 방법 |
| --- | --- |
| [그림 자료/app.ipynb](../../%EA%B7%B8%EB%A6%BC%20%EC%9E%90%EB%A3%8C/app.ipynb) | 설정·함수·실행 셀 |

<a id="-함수셀로-찾아가기"></a>

### 관련 함수와 셀

관련 함수와 셀을 파일별로 정리했습니다. 실행 전 설정과 호출 순서, 출력 경로를 확인하세요.

| 파일 | 핵심 정의 |
| --- | --- |
| [그림 자료/app.ipynb](../../%EA%B7%B8%EB%A6%BC%20%EC%9E%90%EB%A3%8C/app.ipynb) | 셀 4: `build_pdf`<br>셀 5: `analyze_and_suggest`<br>셀 6: `ask_gpt` |

<a name="setup"></a>

<a id="️-환경과-설정"></a>

## 실행 환경과 설정

| 항목 | 조건·기본값 |
| --- | --- |
| 패키지 | Gradio·Ultralytics·FPDF2·OpenAI·OpenCV |
| 경로 | YOLO_MODEL_PATH·PROJECT_DIR·FONT_PATH |
| 인증 | 본인 환경의 OPENAI_API_KEY |
| 입출력 | input/temp.jpg·result/report.pdf |

<a name="usage"></a>

<a id="-준비와-사용-순서"></a>

## 실행 순서

1. 노트북 설정셀에서 모델·작업·폰트 경로를 본인 환경에 맞춥니다.
2. 입력 폴더와 모델 가중치를 준비한 뒤 초기화셀을 확인합니다.
3. Gradio 화면에서 그림을 올려 분석 버튼을 누르고 메시지와 PDF를 확인합니다.
4. 오른쪽 질문은 독립 요청으로 사용하고 필요한 결과는 다음 실행 전에 별도로 보관합니다.

<a name="results"></a>

<a id="-결과를-읽는-방법"></a>

## 결과와 해석

화면의 탐지 성공은 검출 상자가 한 개 이상 있다는 뜻입니다. 그림 전체에 대한 이해나 심리 진단 정확도를 의미하지 않습니다.

출력 이미지는 상자를 새로 그린 것이 아니라 입력 RGB입니다. API 예외 문자열이 메시지와 PDF에 들어갈 수 있으므로 정상 응답인지 확인합니다.

<a name="limits"></a>

<a id="️-알려진-제약과-확인-지점"></a>

## 제약과 확인 사항

| 상황 | 확인할 내용 |
| --- | --- |
| 고정 파일명 | 여러 요청의 그림·PDF 저장이 분리돼 있지 않습니다. |
| 초기화 | API 키·가중치·입력 폴더·폰트가 필요합니다. |
| 연구범위 | 원고의 통합 상담 설계와 실제 두 호출 구성을 구분하며 치료 효과로 판정하지 않습니다. |

<a name="changes"></a>

<a id="-이전-단계와의-변화"></a>

## 직전 단계와 비교

원고의 그림 분석 구조를 읽을 수 있는 기본 앱입니다. 평가 그림을 그리는 4차 노트북과 입력·출력 및 실행 목적이 다릅니다.

[직전 단계 전체 비교·구성](../revision-diffs/app.diff) · [전체 파일 크기·해시](../revision-manifests/app.json)

<details>
<summary>이 단계의 파일 기록과 전체 해시</summary>

아래 표는 해당 단계가 기록될 당시의 파일 정보입니다. 현재 첨부는 [프로젝트 자료 안내](../PAPERS.md)에서 확인할 수 있습니다.

| 파일 | 종류 | 바이트 | SHA-256 |
|---|---|---:|---|
| [그림 자료/app.ipynb](../../%EA%B7%B8%EB%A6%BC%20%EC%9E%90%EB%A3%8C/app.ipynb) | .ipynb | 8196 | `25549c1d0f12e0d8a000d9b1185a575e4acc7a596522e79a3964c00e2f16e9d3` |
| [그림 자료/그림 1.png](../../%EA%B7%B8%EB%A6%BC%20%EC%9E%90%EB%A3%8C/%EA%B7%B8%EB%A6%BC%201.png) | .png | 63869 | `0a562e57a4cf3df48b12530ea02befbd245e854f855f4ccf2e08dc80424fef3a` |
| [그림 자료/그림 2.png](../../%EA%B7%B8%EB%A6%BC%20%EC%9E%90%EB%A3%8C/%EA%B7%B8%EB%A6%BC%202.png) | .png | 324481 | `182eef375de5b5be3fd2056ba7a7be797cbdbb4a26207c05dce09b19d9ea0958` |
| [그림 자료/그림 3.png](../../%EA%B7%B8%EB%A6%BC%20%EC%9E%90%EB%A3%8C/%EA%B7%B8%EB%A6%BC%203.png) | .png | 50719 | `550b5d3b61833be5239b0027eef409d7bc103e122767cb01861741f852d15209` |
| [그림 자료/미술치료 논문 그림 1.drawio](../../%EA%B7%B8%EB%A6%BC%20%EC%9E%90%EB%A3%8C/%EB%AF%B8%EC%88%A0%EC%B9%98%EB%A3%8C%20%EB%85%BC%EB%AC%B8%20%EA%B7%B8%EB%A6%BC%201.drawio) | .drawio | 8310 | `0f0190e3df762ca02c17353022ab592577f9d170409b59b3bad71ec2f153afc4` |
| [그림 자료/미술치료 논문 그림 3.drawio](../../%EA%B7%B8%EB%A6%BC%20%EC%9E%90%EB%A3%8C/%EB%AF%B8%EC%88%A0%EC%B9%98%EB%A3%8C%20%EB%85%BC%EB%AC%B8%20%EA%B7%B8%EB%A6%BC%203.drawio) | .drawio | 7609 | `efa11289474acf761f9c26baa4beb3f87e40e7e5dcf8836661a4655727c85cf4` |

</details>

---

[프로젝트](../../README.md) · [전체 차수](../REVISION_INDEX.md) · [자료 폴더](../../%EA%B7%B8%EB%A6%BC%20%EC%9E%90%EB%A3%8C)
