# PBR 텍스처 양식화 스펙트럼 — Substance Designer 노드 그래프

**PBR Texture Stylization Spectrum — Substance 3D Designer Node Graphs**

이 저장소는 석사학위논문 **「⟨논문 제목⟩」**(김소연, 홍익대학교 대학원 게임콘텐츠전공, ⟨연도⟩)의
실험 자극물을 생성하는 데 사용한 Substance 3D Designer 절차적 노드 그래프를 공개합니다.
연구 결과의 **재현 가능성**을 확보하고, 후속 연구가 동일한 자극물 생성 파이프라인을
검증·확장할 수 있도록 하는 것이 목적입니다.

---

## 개요

본 연구는 PBR(물리 기반 렌더링) 텍스처가 **리얼리스틱**에서 **스타일라이즈드**로
이행하는 양식화 스펙트럼 위에서, 관찰자가 두 양식을 구분하기 시작하는 **전환점(임계값)**을
도출합니다. 실험 자극물은 네 가지 재질(Wood·Metal·Rock·Fabric)에 대해, 각 재질의
**양식화 인자(Style Factor, SF)**를 단계적으로 변화시켜 생성한 텍스처 세트입니다.

이 저장소의 노드 그래프는 그 자극물을 만들어 낸 **생성 장치 그 자체**입니다.
SF 파라미터를 조절하면 사실적 기준점(SF0)부터 양식화가 심화된 단계까지
연속적인 텍스처 스펙트럼이 재생성됩니다.

## 저장소 구성

```
.
├── README.md              이 문서
├── LICENSE                CC BY 4.0 라이선스 전문
├── CITATION.cff           인용 메타데이터 (GitHub·Zenodo 연동용)
└── nodes/                 Substance Designer 그래프 파일
    ├── Wood.sbs           목재 — 양식화 인자 그래프
    ├── Metal.sbs          금속 — 양식화 인자 그래프
    ├── Rock.sbs           암석 — 양식화 인자 그래프
    └── Fabric.sbs         직물 — 양식화 인자 그래프
```

> 각 `.sbs` 파일에는 `Style_Factor` 식별자를 가진 그래프가 포함되어 있으며,
> 이는 논문 본문의 SF 표기와 일치합니다.

## 요구 환경

- **Adobe Substance 3D Designer ⟨버전⟩ 이상**
- 그래프 내부의 `sbs://` 참조(`auto_levels`, `blur_hq`, `noise_clouds` 등)는
  모두 Substance 3D Designer에 **기본 내장된 라이브러리 노드**입니다.
  별도의 에셋 팩이나 외부 파일을 추가로 내려받을 필요가 없으며,
  Substance 3D Designer만 설치되어 있으면 그래프가 곧바로 열립니다.

## 사용 방법

1. Substance 3D Designer에서 `nodes/` 폴더의 원하는 재질 `.sbs` 파일을 엽니다.
2. 패키지 안의 `Style_Factor` 그래프를 선택합니다.
3. 그래프의 입력 파라미터(양식화 인자)를 조절하면 텍스처가 실시간으로 갱신됩니다.
4. 베이스 컬러·노멀·러프니스·하이트·AO 등 PBR 출력 노드에서 텍스처 맵을 내보낼 수 있습니다.

논문에 사용한 정확한 파라미터 값과 SF 단계 구성은 논문 본문 및 부록을 참조하십시오.

## 양식화 인자(Style Factor, SF) 시스템

양식화 인자(SF)는 재질의 사실성-양식화 정도를 하나의 연속 축으로 통제하는 변수입니다.
SF0은 사실적 기준점(realistic baseline)이며, SF 값이 커질수록 양식화가 심화됩니다.
각 재질 그래프는 동일한 SF 축 위에서 자극물 세트를 생성하도록 설계되어 있어,
재질 간 비교가 가능합니다.

> 각 재질의 SF 단계 수, 단계별 파라미터 값, 임계값 분석 결과는
> 논문 본문에 정리되어 있습니다.

## 논문과의 관계

이 저장소는 논문의 **부록 ⟨E⟩**에서 참조됩니다.
논문은 이 노드 그래프로 생성한 자극물을 사용해 양식화 전환점을 정량적으로 분석합니다.

- 논문: ⟨논문 제목⟩
- 저자: 김소연 (Kim Soyeon)
- 소속: 홍익대학교 대학원 게임콘텐츠전공
- 지도교수: 김현석
- 연도: ⟨연도⟩

## 인용 방법 (How to cite)

이 자료를 사용하거나 인용할 경우 아래 정보를 함께 표기해 주십시오.

> 김소연. (⟨연도⟩). *PBR 텍스처 양식화 스펙트럼 — Substance Designer 노드 그래프* [Data set].
> Zenodo. https://doi.org/⟨10.5281/zenodo.XXXXXXX⟩

영구 보존본은 Zenodo에 아카이브되어 있으며 DOI로 식별됩니다.
GitHub 저장소의 **Cite this repository** 버튼(`CITATION.cff` 기반)으로도
인용 형식을 내려받을 수 있습니다.

- **DOI:** ⟨Zenodo 릴리스 후 기입⟩
- **저장소:** https://github.com/Aryeon0228/pbr-stylization-spectrum-nodes

## 라이선스

이 저장소의 노드 그래프는 **[Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE)**
라이선스로 배포됩니다. 자유롭게 사용·수정·재배포할 수 있으며,
사용 시 원저작자(김소연)와 위 논문을 출처로 표기해야 합니다.

© ⟨연도⟩ 김소연 (Kim Soyeon). Licensed under CC BY 4.0.

## 연락처

- 김소연 — ⟨연락처 이메일⟩

---

## English summary

This repository contains the Substance 3D Designer procedural node graphs
used to generate the experimental stimuli for the master's thesis
*"⟨thesis title⟩"* (Soyeon Kim, Dept. of Game Content, Graduate School,
Hongik University, ⟨year⟩).

The study derives the **perceptual transition point** along a stylization
spectrum where PBR textures shift from *realistic* to *stylized*. Stimuli
were generated for four materials (Wood, Metal, Rock, Fabric) by varying a
**Style Factor (SF)** parameter from a realistic baseline (SF0) toward
increasing stylization.

Each `.sbs` file requires **Adobe Substance 3D Designer ⟨version⟩ or later**.
All `sbs://` dependencies are Substance Designer's built-in library nodes —
no external asset packs are needed.

Released under **CC BY 4.0**. If you use these materials, please cite the
thesis and the Zenodo archive (DOI: ⟨10.5281/zenodo.XXXXXXX⟩).
