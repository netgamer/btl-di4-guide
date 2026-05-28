# BTL DI 4 운영 조치 가이드

Oracle → PostgreSQL 이관 후 BTL DI 4 워크플랜 에러 수정 가이드.

## 보기

👉 **https://netgamer.github.io/btl-di4-guide/**

## 케이스 목록

### 잡 에러 (BTL Designer 추출 노드 SQL / 모델 수정)

- **J-1**: `value too long for type character(1)` — 리터럴 오버플로
- **J-2**: CASE 키워드 누락 / 컬럼 prefix 누락 — 구문 오류
- **J-3**: TO_CHAR / REPLACE 함수명이 컬럼명으로 치환됨 / NO() 등
- **J-4**: 필드가 모델에 존재하지 않음 — di_model 컬럼명 불일치 (4-A 모델 수정 / 4-B 타겟 노드 재추가)

### SQL 실행 / 접속 에러

- **S-1**: "xxx is a procedure" — FUNCTION/PROCEDURE 충돌 (DB routine 수정 필요, 예외)
- **S-2**: `role "postgres" does not exist` — 접속 계정 불일치

## 원칙

- 모든 잡/모델/접속 수정은 **BTL DI 4 Designer 에서 직접** 진행.
- DB 쿼리로 직접 수정하는 방식은 사용하지 않음 (Designer 로 불가능한 경우만 예외).

## 업데이트 이력

- 2026-05-28: 초기 배포
