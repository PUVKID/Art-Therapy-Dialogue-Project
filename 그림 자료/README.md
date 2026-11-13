<a id="-그림-자료"></a>

# 그림 자료

<!-- reading-levels17:start -->
**읽기 수준 선택** · [LEVEL 1 - Beginner](../docs/%EC%9D%BD%EA%B8%B0%EC%95%88%EB%82%B4/%EB%A0%88%EB%B2%A81.md) · [LEVEL 2 - Explorer](../docs/%EC%9D%BD%EA%B8%B0%EC%95%88%EB%82%B4/%EB%A0%88%EB%B2%A82.md) · [LEVEL 3 - Practitioner](../docs/%EC%9D%BD%EA%B8%B0%EC%95%88%EB%82%B4/%EB%A0%88%EB%B2%A83.md) · [LEVEL 4 - Advanced](../docs/%EC%9D%BD%EA%B8%B0%EC%95%88%EB%82%B4/%EB%A0%88%EB%B2%A84.md) · [LEVEL 5 - Expert](../docs/%EC%9D%BD%EA%B8%B0%EC%95%88%EB%82%B4/%EB%A0%88%EB%B2%A85.md)

**논문 읽기:** 곽윤석·김남기의 논문은 Journal of KIIT 24(10), 77–84쪽, 2026-10-31에 게재되었습니다. 전체 8쪽 게재본은 [공식 DOI 페이지](https://doi.org/10.14801/jkiit.2026.24.10.77)에서 읽을 수 있습니다. **HWP는 기존 투고 원고**입니다. 게재본 PDF는 저장소에 첨부하지 않습니다. 과거 차수의 파일 구성도·해시·쪽수는 해당 투고 자료의 이력으로 읽어 주세요.
<!-- reading-levels17:end -->

그림 업로드→YOLO 탐지 여부→상담형 메시지→PDF를 Gradio 화면에서 연결하는 노트북 앱입니다. 텍스트 질문 버튼은 별도 요청을 처리합니다.

| 주요 구성 | 내용 |
| --- | --- |
| 그림 분석 | analyze_and_suggest가 RGB를 BGR로 바꾸어 저장하고 YOLO를 호출합니다. |
| 탐지 조건 | conf0.05·imgsz640으로 검출한 상자의 존재를 요약합니다. |
| 별도 질문 | ask_gpt는 질문 한 건만 보내며 이전 그림·대화 이력을 자동결합하지 않습니다. |
| PDF | build_pdf가 분석 요약·생성 메시지·입력 그림을 A4에 저장합니다. |

<a id="-이용-순서"></a>

## 이용 순서

1. 노트북 설정셀에서 모델·작업·폰트 경로를 본인 환경에 맞춥니다.
2. 입력 폴더와 모델 가중치를 준비한 뒤 초기화셀을 확인합니다.
3. Gradio 화면에서 그림을 올려 분석 버튼을 누르고 메시지와 PDF를 확인합니다.
4. 오른쪽 질문은 독립 요청으로 사용하고 필요한 결과는 다음 실행 전에 별도로 보관합니다.

| 차수·단계 | 주요 내용 | 자료 | 직전 비교 |
| --- | --- | --- | --- |
| [그림 자료 · 기본 앱](../docs/revisions/app.md) | [상세 설명](#layout18-table-2-row-1-field-1) | [폴더](.) | [전체 비교](../docs/revision-diffs/app.diff) |

<a id="layout18-table-2-row-1-field-1"></a>

**[그림 자료 · 기본 앱](../docs/revisions/app.md)**

**주요 내용**

그림 업로드→YOLO 탐지 여부→상담형 메시지→PDF를 Gradio 화면에서 연결하는 노트북 앱입니다. 텍스트 질문 버튼은 별도 요청을 처리합니다.


[프로젝트](../README.md) · [전체 차수](../docs/REVISION_INDEX.md)
