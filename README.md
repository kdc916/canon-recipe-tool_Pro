📷 Canon Recipe Generator v9.3 (LazyAI + WorkerXfer + Look Overlay)

이 프로젝트는 참고 사진(타겟) 또는 원본+타겟 2장을 기반으로,
**Canon Picture Style Editor(PSE)**에 입력 가능한 형태로 **레시피(톤 커브/6색축/기본 슬라이더/WB 가이드)**를 생성합니다.
추가로 **Look Overlay(Fuji/GR Positive)**를 강도로 섞어 “그럴듯한 감성”을 안전하게 얻도록 설계했습니다.

✅ 핵심 기능
1) 1장/2장 분석 지원

1장 모드(타겟만): 빠르게 “그 사진 느낌”을 추정해 레시피 생성

2장 모드(원본+타겟): 내 원본을 기준으로 타겟과 매칭 → 더 정교하고 안정적

2) Look Overlay (Fuji + Ricoh GR)

분석 결과에 룩 프리셋을 강도%로 섞는 방식(B안)

포함 프리셋:

Fuji_Provia / Fuji_Astia / Fuji_Reala / Fuji_RealaAce / Fuji_Velvia / Fuji_ClassicChrome / Fuji_ClassicNegative

GR_Positive (Unified): GR2/GR3 Positive Film 계열 샘플의 공통 포인트를 하나로 통합한 룩

권장 강도: 20~45% (과하면 “필터 티”가 날 수 있어 낮추는 게 안전)

3) WB(화이트밸런스) 추천

타겟 이미지의 평균 색 성향을 기반으로

Kelvin(K)

WB Shift (A/B, G/M)
를 참고값으로 제안합니다.

4) Tone Curve 5포인트 자동 산출

결과를 IN → OUT 5포인트로 뽑아
Canon PSE의 Tone Curve 입력에 바로 사용 가능하도록 제공합니다.

5) Specific Colors 6색축(H/S/L) 산출

R/Y/G/C/B/M 6축에 대해
Hue/Sat/Lum 보정 값을 계산해 제공합니다.

6) EXIF 회전(Orientation) 보정

JPEG의 EXIF Orientation을 읽어,
회전된 사진도 분석이 틀어지지 않게 처리합니다.

7) HEIC/HEIF 안내 강화

iPhone HEIC/HEIF 업로드 시 브라우저 미지원 가능성을 즉시 안내합니다.

8) 성능 최적화 (WorkerXfer + LazyAI)

Web Worker로 분석을 분리해 UI 멈춤을 줄임

픽셀 버퍼를 Transfer로 넘겨 복사 비용 감소

AI는 분석 버튼을 눌렀을 때만 지연 로딩(LazyAI) → 첫 진입 속도 개선

🧭 사용 방법

타겟 사진 업로드 (필수)

(선택) 2장 모드라면 원본 사진도 업로드

분석 모드 선택: AI 자동 / 인물 / 풍경 / 스냅 / 야경

(선택) Look Overlay 프리셋 선택 + 강도 조절

분석 시작 → 결과에서

WB 추천

Base 추천

Basic(Contrast/Saturation/ColorTone)

Tone Curve 5pt

Specific Colors 6-axis
를 복사해서 PSE에 입력

⚠️ 주의 / 한계

이 도구의 결과는 카메라/렌즈/조명/노출에 따라 달라지며, **절대값이 아닌 “재현 가이드”**입니다.

가장 정밀한 결과는 **2장 모드(원본+타겟)**에서 얻습니다.

HEIC는 브라우저마다 지원이 달라 JPG 변환 후 업로드를 권장합니다.

🔒 저작권 / 라이선스 (배포·사용·변경 금지)

본 저장소의 모든 소스코드 및 산출물은 작성자에게 저작권이 있습니다.

배포 금지: 원본/수정본 포함, 재배포 불가

사용 금지: 개인/상업 포함, 실행·사용 불가

변경 금지: 수정/파생 작업/리믹스 불가

허가가 필요하면 작성자에게 별도 문의해 주세요.

(권장) 이 문구는 “All Rights Reserved” 성격입니다.

README (EN)
📷 Canon Recipe Generator v9.3 (LazyAI + WorkerXfer + Look Overlay)

This project generates Canon Picture Style Editor (PSE)-friendly recipes from:

1-image mode (target only), or

2-image mode (source + target) for more accurate matching.

It outputs a practical recipe package:

WB suggestion (Kelvin + Shift)

Basic sliders (Contrast / Saturation / Color Tone)

Tone Curve (5 points, IN → OUT)

Specific Colors (6-axis H/S/L)

It also supports Look Overlay (Fuji / GR Positive) to blend a film-like “look” safely using a strength slider.

✅ Key Features
1) 1-shot / 2-shot Analysis

1-shot (target only): fast approximation for a target look

2-shot (source + target): matches your source to the target → more stable & accurate

2) Look Overlay (Fuji + Ricoh GR)

Blends the analysis result with a selected preset using strength%

Included looks:

Fuji_Provia / Fuji_Astia / Fuji_Reala / Fuji_RealaAce / Fuji_Velvia / Fuji_ClassicChrome / Fuji_ClassicNegative

GR_Positive (Unified): a unified Positive Film-style look derived from common traits of GR2/GR3 samples

Recommended strength: 20–45% (reduce if it feels too “filtered”)

3) White Balance Suggestion

Estimates target’s average color bias and suggests:

Kelvin (K)

WB Shift (A/B, G/M)
as a reference.

4) Tone Curve (5-point)

Outputs IN → OUT 5 control points for Canon PSE tone curve input.

5) Specific Colors (6-axis H/S/L)

Calculates adjustments for R/Y/G/C/B/M axes and outputs H/S/L offsets.

6) EXIF Orientation Fix

Reads JPEG EXIF orientation and prevents rotated images from being analyzed incorrectly.

7) HEIC/HEIF Notice

Warns users about potential browser limitations for HEIC/HEIF files.

8) Performance Optimizations (WorkerXfer + LazyAI)

Uses Web Worker to reduce UI blocking

Transfers pixel buffers using Transferables to reduce copy overhead

Lazy-loads AI models only when analysis starts → faster initial load

🧭 How to Use

Upload a target image (required)

(Optional) In 2-shot mode, upload a source image

Choose analysis mode: Auto(AI) / Portrait / Landscape / Snap / Night

(Optional) Choose Look Overlay preset and adjust strength

Click Analyze and copy results into Canon PSE:

WB suggestion

Base recommendation

Basic sliders

Tone curve 5pt

6-axis H/S/L

⚠️ Notes / Limitations

Results depend on camera/lens/light/exposure and should be treated as a recipe guideline, not absolute truth.

Best accuracy comes from 2-shot mode (source + target).

HEIC support varies by browser; convert to JPG if needed.

🔒 Copyright / License (No distribution / use / modification)

All source code and outputs in this repository are copyrighted by the author.

No Redistribution: do not distribute original or modified versions

No Use: do not use/run the code for personal or commercial purposes

No Modification: no edits, forks, derivative works, or remixes

Contact the author for explicit written permission.

This is effectively an “All Rights Reserved” policy.
