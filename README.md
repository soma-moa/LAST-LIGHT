> **Correction & Retraction Notice**
> This document has been prepared to fully correct the contents of the previously published technical white paper v5.5 (Zenodo DOI: 10.5281/zenodo.22373189, etc.) and retract certain claims.
> All claims regarding independent technical creation, defensive prior art specifications, intellectual property (IP) ownership, inventorship, non-obviousness, broad protective scope declarations, DPL licensing, and unverified numerical operation guarantees included in the previously published version are hereby retracted.
> The previously published version v5.5 and associated records remain preserved as historical public records, and this revised edition supersedes them. For technical judgment and interpretation, the cited original literature and national/international standards take ultimate precedence over this document.

* **Data Compiler:** deundeuni (Repository: soma-moa/LAST-LIGHT)
* **Date of Revision:** 2026-10-04
* **License:** CC BY 4.0
* **Original Language Notice:** This document was originally authored in Korean. In case of discrepancies between translated versions and the Korean original, the Korean text serves as the reference, but the cited original literature and relevant standards take ultimate precedence for technical content and interpretation.

---

### Safety and Uncertified Equipment Notice

This document is merely a compilation that surveys and organizes existing literature published in academic papers, patents, and national/international standards.
1. **Uncertified Equipment:** The structures, algorithms, and system configurations mentioned in this document are not officially certified safety equipment and have not undergone engineering or empirical verification.
2. **Non-Replacement of Statutory Equipment:** This material does not replace the legal or functional requirements of statutory emergency exit signs, IMO Low-Location Lighting (LLL), emergency public address systems, or fire hydrant location lights mandated by fire safety, building, ship safety, or industrial safety regulations.
3. **Prohibition of Use:** The descriptions in this document must not be relied upon to construct actual emergency evacuation guidance systems or to serve as a basis for evacuation decisions during actual disaster scenarios.

---

## 1. Revision History

* **2026-10-04:** Added Correction & Retraction Notice, converted to a literature survey and structure organization document, and incorporated review feedback.

---

## 2. Overview and Analytical Framework

This document categorizes and organizes existing technologies proposed to assist in evacuation and location estimation in sensory-deprived environments caused by fire, power outages, and smoke propagation. The three-layer categorization presented herein (Infrastructure Layer, Perception & Estimation Layer, Auxiliary Guidance Layer) serves solely as an analytical framework adopted by the compiler to systematically analyze related literature and does not claim any systemic novelty or structural originality.

---

## 3. Prior Literature Survey by Component

### (A) Reference Point Calibration for Position Drift
Various techniques utilizing external reference points to mitigate error accumulation (drift) in Pedestrian Dead Reckoning (PDR) have been investigated in the literature.
* **Marker and RFID Calibration:** Technologies employing vision-based fiducial markers or RFID tags to reset PDR positions as pedestrians pass designated locations have been studied.
* **2D Barcode Calibration:** Methods combining 2D barcode patterns with PDR to correct indoor navigation positioning errors have been proposed.
* **Landmark and Map Matching:** Approaches utilizing fixed architectural structures (landmarks) such as doors and staircases to correct errors, or applying sensor fusion (Extended Kalman Filters, etc.) to combine WiFi/BLE signals with landmark data, have been presented.
* **Visual-Inertial SLAM Drift Correction:** Research has been conducted on correcting position drift in Visual-Inertial SLAM by leveraging vanishing point features in indoor environments.

### (B) Wearable Tactile (Haptic) Directional Guidance
Various means of providing directional information through vibrotactile stimuli applied to the skin or bones in environments with degraded visual and auditory feedback have been proposed.
* **Firefighter Evacuation Assistance:** Vibrotactile waist belts, helmet-integrated directional vibration devices, and wrist-worn haptic devices (SearchSense) have been researched to aid firefighters in situational awareness and egress through dense smoke.
* **Ship Evacuation Assistance:** Smart lifejackets with embedded vibration motors and beacon-linked smartbands have been proposed for passenger evacuation from large ships.
* **Space Environment Guidance:** NASA technical memoranda have addressed tactile displays (Tactor Locator System) for astronaut situational awareness during EVA, while ISS tactile vest literature has explored applications including emergency evacuation guidance.

### (C) Low-Location Lighting and Photoluminescent Lines
Guidance systems installed near floor level to counter upper-level smoke accumulation are established under international standards and regulations.
* **International Standards:** ISO 15370 and IMO Resolution A.752(18) specify installation and performance criteria for Low-Location Lighting (LLL) on passenger ships.
* **Installation and Luminescence:** The requirement to install guidance within 300 mm of the floor is described in SOLAS and ISO 15370 related materials, and both electrical and photoluminescent materials are accepted. ISO 15370 references ISO 16069 for graphical symbols of escape route signs, whereas ISO 16069 itself is not intended for ships falling under IMO regulations and does not address tactile or audible components.

### (D) Utilization of Emergency Lights and Exit Signs as Location Anchors
Research and patents exist regarding the integration of wireless communication functions into existing emergency exit signs and emergency lighting to serve as positional reference points.
* **Patents on Wireless Beacon Integration:** Technologies incorporating BLE or WiFi modules inside emergency lights and exit signs to assist indoor positioning have been published (e.g., US 11127266, US 12156316).
* **Visible Light Positioning:** Studies on applying LED Visible Light Positioning (VLP) technology for indoor pedestrian localization have been reported in academic journals.
* **Beacon-Integrated Exit Signs:** Research has been conducted on combining BLE beacons with emergency exit signs to serve as location reference points for smartphone evacuation applications.

### (E) IoT Monitoring of Fire Safety Equipment
Technologies for remotely monitoring the status of existing fire safety equipment, including extinguishers, fire hydrants, and fire doors, have been proposed.
* **Fire Safety Infrastructure Monitoring Patents:** Technologies monitoring the status of fire extinguishers, hydrant valves, exit signs, emergency lights, and fire doors via IoT networks (US 11080988) and smart fire hydrant monitoring systems (US 8657021) have been published.
* **NFC and Sensor Integration:** Platforms monitoring fire extinguisher pressure status using NFC and sensors (SmartFire) have been investigated.

### (F) Multi-Sensor Fusion and Verification for False Alarm Suppression
Multi-sensor cross-verification techniques have been implemented to prevent unnecessary evacuations caused by detector malfunctions.
* **Multi-Sensor Fusion:** Studies combining temperature, smoke, and CO concentrations using fuzzy logic or neural networks have been conducted. Warehouse fire detection literature has reported a 42% reduction in false alarms and a 35% reduction in response time through multi-sensor information fusion.
* **Physical Structures and Dual-Detection Verification:** Patents exist for issuing alarms only upon dual-detection confirmation (US 6788198), as well as patents describing U-shaped piping structures in industrial facilities (e.g., semiconductor fabs) to suppress false hydrogen gas alarms and prevent unnecessary evacuations (US 11994809).

### (G) Adaptive Evacuation Guidance and Dynamic Signs
Dynamic evacuation systems that adaptively modify guidance directions based on disaster locations have been researched.
* **Dynamic Guidance Signage:** Research has been conducted on intelligent evacuation systems controlling sign directions based on fire locations in IoT-enabled multi-floor, multi-exit buildings.
* **Station Evacuation and Personalized Routes:** Patents describing systems for guiding personalized dynamic exit paths for pedestrians during subway station fires have been published (US 11373492), and methods combining BIM data with real-time BLE positioning for personalized route guidance have been explored.

### (H) Auditory Beacons
Directional auditory beacons designed to provide acoustic guidance toward exit paths in dense smoke have been studied extensively.
* **Acoustic Guidance Experimental Literature:** Research by van Wijngaarden, Bronkhorst, and Boer (2005) reported that in ship model experiments, 88% of participants followed the intended route using newly designed signals and delay methods, compared to 38% using conventional methods. Signal delays between beacons were measured at approximately 20 ms.
* **Smoke Tunnel Experiments:** Experiments by Boer & Withington (2004) in smoke-filled tunnels confirmed exit location success rates of 16%, 21%, and 70%, depending on the level of directional indication provided.
* **Directional Audio Patents:** Patents for directional sound beacons (US 12190717) and addressable speaker evacuation systems (US 8229131) have been published.

### (I) UWB and Short-Range Wireless Evacuation Support
Research on deploying UWB and BLE technologies for high-precision location tracking during emergency evacuations has been documented.
* **UWB Emergency Positioning:** Studies by Zhang, Alkobaisi, Bae, and Narayanappa (2013) and related journals have addressed the rapid deployment of UWB-based indoor positioning systems to support disaster response and evacuation operations.

### (J) Fire-Resistant Recording Modules and Building Black Boxes
Concepts for record-keeping devices designed to protect evacuation logs and building telemetry during disasters exist in the literature.
* **Fire-Resistant Storage:** According to flight recorder survivability references on SKYbrary, memory modules in flight recorders are specified to withstand temperatures of 1,100 °C for 60 minutes.
* **Building Data Recorders:** Concept presentations on Building Data Recorders (BDR) for storing building sensor and evacuation data (e.g., Kori Technology Group, hosted on NIST) have been published, and patents for locally recording firefighter movement paths exist (US 5815126).

### (K) Crowd Leader-Follower Evacuation
The impact of informed individuals on collective crowd evacuation performance has been researched.
* **Informed Group Evacuation:** Mathematical modeling and simulation studies (e.g., Albi et al., arXiv:2108.12231) have reported that a small minority of leaders possessing route information can significantly enhance overall crowd evacuation efficiency.

### (L) Semiconductor Fab VMB Standards
* **Industrial Safety Standards:** FM Global semiconductor facility loss prevention standards specify leak detection and interlock circuits for gas distribution equipment such as Valve Manifold Boxes (VMBs). Semiconductor manufacturing equipment environmental, health, and safety guidelines (SEMI S2) also mandate corresponding safety provisions.

---

### [Unverified Literature Items (Compiler Notes)]
The following items represent specific configurations for which direct prior studies or patents were not identified during this literature review, and are listed separately as unverified conceptual classifications:
* Specific implementations directly combining indoor fire hydrant boxes or explosion-proof enclosures as both positional reference points and data recording module containers.
* Explicit literature dedicated specifically to emergency evacuation usage for the BLE Auracast protocol itself was not identified.
* Explicit literature describing cold-chain and HACCP explosion-proof certified enclosures integrated as evacuation reference anchors was not identified.
* Explicit literature proving a direct causal link between an individual wearing a haptic receiver and naturally leading surrounding evacuees was not identified.
* System combinations linking the totality of statutory fire safety infrastructure into a unified location reference system were not identified.
* AR glass HUD evacuation guidance frameworks were not identified (requires further literature investigation).

---

## 4. Notice Regarding Referenced Standards

Standards mentioned in this document—including ISO 7010, ISO 15370, ISO 16069, IMO Resolution A.752(18), NFPC, KCs, SEMI S2, and SEMI S8—are public standards referenced by prior studies and literature. This material does not claim compliance with or official certification under any of these standards.

---

## 5. Source and Bibliographic Information

### [Verified Bibliographic Records (Title, Author, Source Confirmed)]
* Slater, Ferris, Dixon, Renshaw, Moore, Frady, Harrison et al., "Navigating in Zero-Visibility: A Haptic Guidance System for Improving Egress and Situation Awareness of Professional Firefighters," Human Factors 67(11):1152–1169, 2025, DOI 10.1177/00187208251348020
* Tian, Salcic, Wang, Pan, "A Hybrid Indoor Localization and Navigation System with Map Matching for Pedestrians Using Smartphones," Sensors 15(12):30759–30783, 2015, DOI 10.3390/s151229827
* van Wijngaarden, Bronkhorst, Boer, "Auditory Evacuation Beacons," J. Audio Eng. Soc. 53(1/2):44–53, 2005
* Boer, L.C., Withington, D.J., "Auditory guidance in a smoke-filled tunnel," Ergonomics 47(10):1131–1140, 2004, DOI 10.1080/00140130410001695942
* Zhang, Alkobaisi, Bae, Narayanappa, "Ultra wideband indoor positioning system in support of emergency evacuation," 5th ACM SIGSPATIAL International Workshop on Indoor Spatial Awareness (ISA '13), 2013
* Van Erp, Van Veen, Jansen, Dobbins, "Waypoint navigation with a vibrotactile waist belt," ACM Transactions on Applied Perception 2(2):106–117, 2005, DOI 10.1145/1060581.1060585

### [Secondary Citations (Identified from Reference Lists of Other Literature)]
* Chen, Zou, Jiang, Zhu, Soh, Xie, "Fusion of WiFi, Smartphone Sensors and Landmarks Using the Kalman Filter for Indoor Localization," Sensors 15:715–732, 2015

### [Reference Bibliography (Titles and Sources based on Search Results; Authors/Pages Unverified)]
* ISO 15370:2021 – Low-Location Lighting Arrangement on Passenger Ships
* Communication Aspects of Visible Light Positioning (VLP) Systems Using a Quadrature Angular Diversity Aperture (QADA) Receiver, PMC7180791
* SearchSense: Haptic Directional Guidance for Emergency Response
* Haptic Helmet for Emergency Responses in Virtual and Live Environments
* Evaluating Angular Accuracy of Wrist-based Haptic Directional Guidance for Hand Movement, Hong et al., Graphics Interface 2016
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
* Albi et al., arXiv:2108.12231
* Patents: US 11127266, US 12156316, US 11080988, US 8657021, US 6788198, US 11994809, US 11373492, US 12190717, US 8229131, US 5815126
* IMO Res. A.752(18), SOLAS Low-Location Lighting Regulations, ISO 16069, ISO 7010, FM Global Semiconductor Loss Prevention Data Sheets (2025), SEMI S2, EN 1838

---

## Appendix: Compilation Process and Responsibility Notice

Drafting and review tools were utilized during the preparation of this document. Final content verification and responsibility rest entirely with the data compiler.
