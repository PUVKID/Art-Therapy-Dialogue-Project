# 📝 2026-10-30 연구 원문과 차수 공개 보완

원격 기준 커밋: `879303a27b7aa8031c3df336847407987cfddc8b`

기존 공개 파일을 삭제하지 않고 원본 논문·문서·연구 코드·결과표·발표자료를 추가했습니다. 연구 번호와 원본 폴더 차수·원고 수정·발표 차수를 구별하고 각 파일·직전 단계의 전체 차이와 크기·SHA-256을 연결했습니다. 현재 원문 PDF/HWP와 나중 공식 URL 교체 지점은 [논문 표](PAPERS.md)에 있습니다.

## 실제 수정 파일

- `CHANGELOG.md`: 현재 원문·이전 정제 사본과 차수 안내의 정합성을 보완했습니다.
- `README.md`: 논문 직접 링크·모든 실제 단계·파일 종류·비교를 보완하고 기존 이모지 구조를 유지했습니다.
- `docs/VERSIONS.md`: 현재 원문·이전 정제 사본과 차수 안내의 정합성을 보완했습니다.
- `docs/versions/latest.md`: 현재 원문·이전 정제 사본과 차수 안내의 정합성을 보완했습니다.

## 실제 추가 파일

- `docs/PAPERS.md`
- `docs/PUBLIC_CHANGELOG_2026-10-30.md`
- `docs/REVISION_INDEX.md`
- `docs/revision-diffs/app.diff`
- `docs/revision-diffs/paper-1.diff`
- `docs/revision-diffs/paper-2.diff`
- `docs/revision-diffs/paper-3.diff`
- `docs/revision-diffs/paper-4.diff`
- `docs/revision-diffs/paper-5.diff`
- `docs/revision-manifests/app.json`
- `docs/revision-manifests/paper-1.json`
- `docs/revision-manifests/paper-2.json`
- `docs/revision-manifests/paper-3.json`
- `docs/revision-manifests/paper-4.json`
- `docs/revision-manifests/paper-5.json`
- `docs/revisions/app.md`
- `docs/revisions/paper-1.md`
- `docs/revisions/paper-2.md`
- `docs/revisions/paper-3.md`
- `docs/revisions/paper-4.md`
- `docs/revisions/paper-5.md`
- `그림 자료/그림 1.png`
- `그림 자료/그림 2.png`
- `그림 자료/그림 3.png`
- `그림 자료/미술치료 논문 그림 1.drawio`
- `그림 자료/미술치료 논문 그림 3.drawio`
- `논문/1차/관련문서/정보기술학회_단편논문_미술치료_심사용.hwp`
- `논문/1차/관련문서/투고신청서.hwp`
- `논문/1차/원문_논문.hwp`
- `논문/1차/원문_논문.pdf`
- `논문/2차/관련문서/2차_정보기술학회_단편논문_미술치료_심사용.hwp`
- `논문/2차/관련문서/2차_투고신청서.hwp`
- `논문/2차/관련문서/심사답변서 1.hwp`
- `논문/2차/관련문서/심사답변서 2.hwp`
- `논문/2차/관련문서/심사답변서 3.hwp`
- `논문/2차/원문_논문.hwp`
- `논문/2차/원문_논문.pdf`
- `논문/3차/관련문서/3차_정보기술학회_논문_미술치료_심사용.hwp`
- `논문/3차/관련문서/3차_투고신청서.hwp`
- `논문/3차/원문_논문.hwp`
- `논문/3차/원문_논문.pdf`
- `논문/4차/관련문서/4차_정보기술학회_논문_미술치료_심사용.hwp`
- `논문/4차/관련문서/심사답변서 1.hwp`
- `논문/4차/관련문서/심사답변서 2.hwp`
- `논문/4차/관련문서/심사답변서 3.hwp`
- `논문/4차/원문_논문.hwp`
- `논문/4차/원문_논문.pdf`
- `논문/5차/원문_논문.hwp`
- `논문/5차/원문_논문.pdf`
- `자료/3차/미술치료 논문 그림 3.drawio`
- `자료/3차/미술치료 논문 그림 3.png`
- `자료/4차/그림 5_원본.ipynb`
- `자료/4차/그림/그림 1.png`
- `자료/4차/그림/그림 2.png`
- `자료/4차/그림/그림 3.drawio.png`
- `자료/4차/그림/그림 5.png`
- `자료/4차/미술치료 논문 그림 1.drawio`
- `자료/4차/미술치료 논문 그림 3.drawio`
- `자료/4차/평가점수_원본표.txt`

## 비교와 검증 범위

- [전체 단계·직전 단계 차이](REVISION_INDEX.md)에 파일별 근거와 원고 설명을 연결했습니다. 공백·주석·코드셀·Markdown·텍스트·수치·실험 설정을 전체 비교하며 ipynb의 바이너리 이미지 출력만 바이트 길이·SHA-256·원문 링크로 표시합니다. 원문 ipynb 자체는 보존합니다.
- UTF-8, 비밀 패턴, 실제 로컬 링크, 노트북 JSON, source/public SHA 및 코드 셀 보존, PDF 열기를 검사했습니다. 원본0바이트 노트북은 그대로 남기며 JSON·실행·성능 근거에서 제외합니다.
- 의료 원본 후보가 포함된 노트북 이미지 출력만 제외한 사본은 비공개 대응표에 source/public 해시와 변환 이유를 구별해 기록했습니다.
- 원문에 실린 본인·공동저자의 성명·소속·이메일·전화·ORCID·이력·사진은 최신 공개 지시에 따라 보존합니다. 기존 원격 정제 사본은 이력으로 유지합니다.
- 인증키·비밀번호, 대용량 모델·원데이터, 연구와 무관한 결제 자료·도구 설치 캐시와 본인 비저자·공개권한 근거 불명확 외부 원고는 별도 제외·보류 근거로 관리합니다. 원본은 수정·삭제하지 않았습니다.
- 새 학습·임상·제조 장비·추천 성능 실험은 수행하지 않았습니다. 저장 표와 원고 보고값을 새 실측으로 소개하지 않습니다.
- 이 변경 기록 시점에는 원격 쓰기·커밋·푸시를 수행하지 않았고 부모 통합 독립 검토와 반영을 기다립니다.
