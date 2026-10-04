> **정정 및 철회 고지 (Correction & Retraction Notice)**
> 본 문서는 기존에 공표되었던 기술 백서 v5.5(Zenodo DOI: 10.5281/zenodo.22373189 등)의 내용을 전면 정정하고 일부 주장을 철회하기 위해 작성되었습니다.
> 기존 공개본에 포함되었던 독자적 기술 창안, 방어적 선행기술 명세, 지식재산권(IP) 보유, 발명자성, 비자명성 주장, 포괄적 보호 범위 선언, DPL 라이선스 적용 및 검증되지 않은 수치적 작동 보증은 모두 철회합니다.
> 기존 공개본 v5.5 및 관련 기록은 과거 공개 이력으로 유지되며, 본 개정판이 해당 내용을 대체합니다. 기술적 판단 및 해석은 본 문서가 아닌 인용된 원 문헌 및 국가·국제 표준을 최우선으로 합니다.

* **자료 정리자:** deundeuni (저장소: soma-moa/LAST-LIGHT)
* **최종 개정일:** 2026-10-04
* **적용 라이선스:** CC BY 4.0
* **원안 언어 고지:** 본 문서는 한국어로 작성되었습니다. 번역본과 차이가 있는 경우 한국어 원문을 참조하되, 실질적인 내용과 기술적 해석은 원 문헌 및 표준이 최우선합니다.

---

### 안전 및 미인증 관련 고지

본 문서는 학술 논문, 특허, 국제·국가 표준 등 기존에 발표된 선행 문헌을 조사하고 정리한 자료집에 불과합니다.
1. **미인증 설비:** 본 문서에 언급된 구조, 알고리즘, 시스템 구성은 공식 인증을 받은 안전 설비가 아니며, 공학적·실증적 검증이 완료되지 않았습니다.
2. **법정 설비 비대체성:** 본 자료는 소방법, 건축법, 선박안전법, 산업안전보건법 등 관련 법령에 의해 설치가 의무화된 법정 비상구 유도등, IMO 저위치 비상조명(LLL), 비상방송, 소화전 표시등 등의 법적·기능적 의무를 대체하지 않습니다.
3. **사용 금지:** 본 문서의 서술에 의존하여 실제 피난 유도 시스템을 구축하거나 재난 상황 시 피난 판단의 근거로 사용해서는 안 됩니다.

---

## 1. 개정 이력

* **2026-10-04:** 정정 및 철회 고지 추가, 선행 문헌 조사 및 구조 정리 문서로 전환, 검수 의견 반영.

---

## 2. 개요 및 분석 틀

본 문서는 화재, 정전, 연기 확산 등 감각이 제한되는 환경에서 피난 및 위치 추정을 보조하기 위해 제안된 기존 기술들을 요소별로 분류하고 정리한 문서입니다. 본 문서에 제시된 3계층 분류(인프라 계층, 인지·추정 계층, 보조 유도 계층)는 정리자가 관련 문헌을 체계적으로 파악하기 위해 채택한 분석 틀에 불과하며, 본 문서에서 어떠한 시스템적 신규성이나 조합의 독창성을 주장하지 않습니다.

---

## 3. 구성요소별 선행 문헌 정리

### (가) 위치 드리프트의 기준점 보정
보행자 관성 항법(PDR)의 위치 오차 누적(Drift)을 완화하기 위해 외부 기준점을 활용하는 기법들이 문헌에서 다수 연구되었습니다.
* **마커 및 RFID 보정:** 비전 기반 기준 마커(Fiducial Marker)나 RFID 태그를 설치하여 보행자가 해당 위치를 통과할 때 PDR 위치를 재설정하는 기술이 연구되었습니다.
* **2D 바코드 보정:** 2D 바코드 패턴과 추측항법(PDR)을 결합하여 실내 보행 항법 오차를 보정하는 기술이 제시되었습니다.
* **랜드마크 및 지도 매칭:** 문, 계단 등 고정된 건축 구조물(랜드마크)을 인식하여 오차를 보정하거나, 센서 퓨전(확장 칼만 필터 등)을 통해 WiFi/BLE 신호와 랜드마크 정보를 결합하는 방식이 제시되었습니다.
* **시각-관성 SLAM 오차 보정:** 실내 환경의 소실점(Vanishing Point) 특징을 활용하여 시각-관성 SLAM의 위치 드리프트를 보정하는 연구가 수행되었습니다.

### (나) 착용형 촉각(햅틱) 방향 안내
시각 및 청각 정보가 차단된 상황에서 피부나 뼈에 전달되는 진동 자극을 통해 방향 정보를 전달하는 수단이 다수 제안되었습니다.
* **소방관 피난 보조:** 짙은 연기 속에서 소방관의 상황 인지 및 피난을 돕기 위해 허리 진동 벨트, 헬멧 내장형 방향 진동 장치, 손목 진동 장치(SearchSense) 등이 연구되었습니다.
* **선박 피난 보조:** 대형 여객선 탈출을 위해 진동 모터가 내장된 스마트 구명조끼 및 비콘 연동 스마트밴드 방식이 제시되었습니다.
* **우주 환경 보조:** NASA 기술 메모에서는 EVA 중 우주비행사의 상황인식을 높이기 위한 촉각 디스플레이(Tactor Locator System)가 다뤄졌으며, ISS 촉각 조끼 문헌에서는 비상 탈출 안내가 용도 중 하나로 제시되었습니다.

### (다) 저위치 유도등 및 축광 유도선
연기가 상부로 차단되는 현상에 대응하여 바닥 부근에 설치되는 유도 체계는 국제 표준 및 규정으로 정립되어 있습니다.
* **국제 표준:** ISO 15370 및 IMO Resolution A.752(18)에서는 승객선 내 저위치 비상조명(Low-Location Lighting, LLL)의 설치 및 성능 기준을 규정하고 있습니다.
* **설치 위치 및 축광:** 바닥면으로부터 300mm 이내의 저위치 설치 기준은 SOLAS 및 ISO 15370 관련 자료에 서술되어 있으며, 전기식 및 무전원 축광 재료가 모두 인정됩니다. ISO 15370은 탈출 경로 표지의 도형 등에 대해 ISO 16069를 참조하나, ISO 16069는 IMO 규정 대상 선박에는 사용하지 않도록 되어 있고 촉각·음향 구성요소는 다루지 않습니다.

### (라) 비상등 및 비상구 표지의 위치 앵커 활용
기존 비상 유도등 및 비상구 표지에 무선 통신 기능을 결합하거나 위치 기준점으로 활용하는 연구 및 특허가 존재합니다.
* **무선 비콘 결합 특허:** 비상 조명 및 비상구 표지판 내부에 BLE 또는 WiFi 모듈을 탑재하여 위치 측위를 보조하는 기술이 공개되어 있습니다 (예: US 11127266, US 12156316).
* **가시광 측위:** LED 조명의 가시광 측위(VLP) 기술을 실내 보행자 위치 추정에 활용하는 연구가 학술지에 보고되었습니다.
* **비콘 내장 비상구 표지:** BLE 비콘을 비상구 표지에 결합하여 스마트폰 피난 애플리케이션의 위치 기준점으로 사용하는 방식이 연구되었습니다.

### (마) 소방 설비 IoT 감시
소화기, 소화전, 방화문 등 기존 소방 설비의 상태를 원격으로 모니터링하기 위한 기술이 제안되었습니다.
* **소방 인프라 모니터링 특허:** 소화기, 소화전 밸브, 피난 표지, 비상등, 방화문의 상태를 IoT 네트워크로 감시하는 기술(US 11080988) 및 스마트 소화전 모니터링 기술(US 8657021)이 공개되어 있습니다.
* **NFC 및 센서 결합:** 소화기 압력 상태를 NFC 및 센서로 점검하는 플랫폼(SmartFire) 연구가 진행된 바 있습니다.

### (바) 비화재보 억제를 위한 이종 센서 융합·검증
감지기 오작동에 따른 불필요한 대피를 방지하기 위해 다중 센서 신호를 교차 검증하는 기술이 적용되어 왔습니다.
* **다중 센서 융합:** 온도, 연기, CO 농도를 퍼지 논리나 신경망으로 결합하는 연구가 수행되었습니다. 창고 화재 감지 문헌에서는 다중 센서 융합을 통해 오경보율을 42% 감소시키고 응답 시간을 35% 단축한 결과가 보고되었습니다.
* **물리 구조 및 이중 감지 확인:** 이중 감지 확인 시에만 경보를 발령하는 특허(US 6788198)가 존재하며, 반도체 팹 등 산업 현장에서 배관의 U자 구조를 통해 수소 감지기의 오경보와 불필요한 대피를 방지하는 특허(US 11994809) 등이 공개되어 있습니다.

### (사) 적응형 피난 유도 및 동적 표지
재난 위치에 따라 유도 방향을 가변적으로 변경하는 동적 피난 체계가 연구되었습니다.
* **동적 유도 사이니지:** IoT 기반 multi-floor, multi-exit 건물에서 화재 발생 지점에 따라 표지판의 유도 방향을 제어하는 지능형 피난 시스템 연구가 진행되었습니다.
* **역사 피난 및 개인화 경로:** 지하철 역사 화재 시 보행자별 동적 탈출 경로를 안내하는 시스템 특허(US 11373492)가 공개되어 있으며, BIM 데이터와 BLE 실시간 측위를 결합하여 개인별 최적 대피 동선을 안내하는 기술이 탐구되었습니다.

### (아) 음향 비콘
짙은 연기 속에서 출구 방향을 청각적으로 유도하기 위한 지향성 음향 비콘 연구가 다수 존재합니다.
* **음향 유도 실험 문헌:** van Wijngaarden, Bronkhorst, Boer(2005)의 연구에 따르면 선박 모형 실험에서 새로 설계한 신호와 지연 방식은 참가자의 88%가 의도한 경로를 따랐고, 기존 방식은 38%였다고 보고되었습니다. 비콘 간 신호 지연은 약 20ms 수준으로 조사되었습니다.
* **연기 터널 실험:** Boer & Withington(2004)의 연구에서는 연기로 차있는 터널 환경에서 지시 수준에 따른 출구 발견 비율이 각각 16%, 21%, 70%로 차이를 보이는 점이 확인되었습니다.
* **지향성 음향 특허:** 지향성 음향 비콘(US 12190717) 및 주소 지정이 가능한 스피커 피난 시스템(US 8229131) 특허가 공개되어 있습니다.

### (자) UWB 및 근거리 무선 대피 지원
긴급 대피 시 고정밀 위치 추적을 위해 UWB 및 BLE 기술을 활용하는 연구가 진행되었습니다.
* **UWB 응급 측위:** Zhang, Alkobaisi, Bae, Narayanappa(2013) 연구 및 관련 학술지에서는 재난 대응 및 대피 지원을 위한 UWB 기반 실내 측위 시스템의 신속 배치 가능성이 다뤄졌습니다.

### (차) 내화 기록 모듈 및 건물 블랙박스
재난 발생 시 피난 및 건물 상태 로그를 보호하기 위한 기록 장치 개념이 존재합니다.
* **내화 저장 장치:** SKYbrary에 게재된 자료에 따르면 항공기 기록 장치의 메모리 모듈은 1,100℃에서 60분을 견뎌야 한다고 서술됩니다.
* **건물 데이터 레코더:** NIST 사이트에 게시된 Kori Technology Group의 발표 자료 등에서 건물 센서 및 대피 데이터를 저장하는 건물 데이터 레코더(Building Data Recorder) 개념이 다뤄진 바 있으며, 소방관 이동 경로를 로컬에 저장하는 특허(US 5815126)가 공개되어 있습니다.

### (카) 군중 리더-팔로워 피난
피난 시 일부 정보 전달자의 역할이 군중 대피에 미치는 영향이 연구되었습니다.
* **정보 유무에 따른 집단 대피:** 대피 경로 정보를 알고 있는 소수의 리더가 전체 군중의 대피 효율성을 향상시킨다는 수학적 모델 및 시뮬레이션 연구(Albi et al., arXiv:2108.12231 등)가 공표되었습니다.

### (타) 반도체 팹 VMB 및 규격
* **산업 안전 규격:** FM Global 반도체 시설 규격에 따르면 VMB(Valve Manifold Box) 등 가스 분배 장치에는 누출 감지 및 인터락 회로가 규정되어 있습니다. 반도체 제조 장비 환경·보건·안전 지침인 SEMI S2 역시 관련 안전성을 요구합니다.

---

### [문헌 미확인 항목 (정리자 메모)]
아래 항목들은 본 문헌 조사 과정에서 직접적인 선행 연구 또는 특허를 확인하지 못하였으므로, 검증되지 않은 개념 분류로 따로 기재합니다.
* 옥내 소화전함, 방폭 함체 등을 위치 기준점과 데이터 기록 모듈 수용체로 직접 결합한 특정 구현 방식
* BLE Auracast 프로토콜 자체의 피난 전용 사용에 관한 선행 표준
* 콜드체인 및 HACCP 방폭 인증 함체를 피난 위치 기준점으로 통합 활용하는 구체적 서술
* 착용형 촉각 수신기를 착용한 개인이 주변 피난자를 이끄는 행동 양식과 햅틱 기기 간의 직접적 인과관계 결합 서술
* 법정 피난 인프라 전체를 단일 위치 기준점 체계로 묶는 통합 조합 서술
* AR 글래스 HUD 피난 안내 체계 (추후 추가 조사 필요)

---

## 4. 참조 표준 관련 고지

본 문서에 언급된 ISO 7010, ISO 15370, ISO 16069, IMO Resolution A.752(18), NFPC, KCs, SEMI S2, SEMI S8 등은 관련 연구 및 선행 문헌이 참조한 표준 규격일 뿐이며, 본 자료는 해당 표준에 대한 적합성이나 인증 충족 여부를 주장하지 않습니다.

---

## 5. 출처 및 서지 정보

### [서지 대조 완료 (제목·저자·게재지 확인)]
* Slater, Ferris, Dixon, Renshaw, Moore, Frady, Harrison 외, "Navigating in Zero-Visibility: A Haptic Guidance System for Improving Egress and Situation Awareness of Professional Firefighters," Human Factors 67(11):1152–1169, 2025, DOI 10.1177/00187208251348020
* Tian, Salcic, Wang, Pan, "A Hybrid Indoor Localization and Navigation System with Map Matching for Pedestrians Using Smartphones," Sensors 15(12):30759–30783, 2015, DOI 10.3390/s151229827
* van Wijngaarden, Bronkhorst, Boer, "Auditory Evacuation Beacons," J. Audio Eng. Soc. 53(1/2):44–53, 2005
* Boer, L.C., Withington, D.J., "Auditory guidance in a smoke-filled tunnel," Ergonomics 47(10):1131–1140, 2004, DOI 10.1080/00140130410001695942
* Zhang, Alkobaisi, Bae, Narayanappa, "Ultra wideband indoor positioning system in support of emergency evacuation," 5th ACM SIGSPATIAL International Workshop on Indoor Spatial Awareness (ISA '13), 2013
* Van Erp, Van Veen, Jansen, Dobbins, "Waypoint navigation with a vibrotactile waist belt," ACM Transactions on Applied Perception 2(2):106–117, 2005, DOI 10.1145/1060581.1060585

### [2차 인용 서지 (다른 문헌의 참고문헌 목록에서 확인)]
* Chen, Zou, Jiang, Zhu, Soh, Xie, "Fusion of WiFi, Smartphone Sensors and Landmarks Using the Kalman Filter for Indoor Localization," Sensors 15:715–732, 2015

### [참고 서지 (제목·게재지는 검색 결과 기준, 저자·쪽수·원문 미대조)]
* ISO 15370:2021 – Low-Location Lighting Arrangement on Passenger Ships
* Communication Aspects of Visible Light Positioning (VLP) Systems Using a Quadrature Angular Diversity Aperture (QADA) Receiver, PMC7180791
* SearchSense: Haptic Directional Guidance for Emergency Response
* Haptic Helmet for Emergency Responses in Virtual and Live Environments
* Evaluating Angular Accuracy of Wrist-based Haptic Directional Guidance for Hand Movement, Hong 외, Graphics Interface 2016
* Building Data Recorder Presentation Material (Kori Technology Group, NIST Hosted Material)
* A multi-purpose tactile vest for astronauts in the international space station
* Flight Data Recorder Fire Protection Regulations (SKYbrary Reference Material)
* Indoor pedestrian navigation system using a modern smartphone
* "The Implementation of a Smart Lifejacket for Assisting Passengers in the Evacuation of Large Passenger Ships," Applied Sciences 13(4):2522, 2023, DOI 10.3390/app13042522
* "Effectiveness assessment and simulation of a wearable guiding device for ship evacuation," J. Mar. Sci. Technol. (2024)
* "Using Smartphones for Indoor Fire Evacuation," Int. J. Environ. Res. Public Health 19(10):6061, 2022
* "SmartFire: Intelligent Platform for Monitoring Fire Extinguishers and Their Building Environment," Sensors 19(10):2390, 2019
* "Fast Deployment of a UWB-Based IPS for Emergency Response Operations," Sensors 23, 2023
* "Warehouse Fire Detection System Based on Multi-Sensor Information Fusion," Sensors 2026, DOI 10.3390/s26123763
* "Intelligent Evacuation Sign Control Mechanism in IoT-Enabled Multi-Floor Multi-Exit Buildings"
* "Real-time Intelligent Exit Path Indicator Using BLE Beacon Enabled Emergency Exit Sign Controller," International Journal of Advanced Smart Convergence
* "Wearable indoor pedestrian dead reckoning system"
* NASA/TM–20210017508 (Tactile Cueing)
* Albi 외 arXiv:2108.12231
* 특허: US 11127266, US 12156316, US 11080988, US 8657021, US 6788198, US 11994809, US 11373492, US 12190717, US 8229131, US 5815126
* IMO Res. A.752(18), SOLAS 저위치 조명 규정, ISO 16069, ISO 7010, FM Global 반도체 시설 데이터시트(2025), SEMI S2, EN 1838

---

## 부록: 작성 과정 및 책임 고지

작성 과정에서 초안·검수 도구를 사용했으며, 최종 내용 확인과 책임은 작성자에게 있다.
