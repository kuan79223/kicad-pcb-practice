[← 返回專案列表](../README.md)

# Project 02 · 2N3904 共射極放大器

**實驗目標：** 使用 KiCad 完成 2N3904 共射極放大器（Common-Emitter Amplifier）的原理圖、元件封裝配置、PCB 佈線、ERC／DRC 驗證及 Gerber 製造檔輸出。

> **學習實作專案。** 本電路已完成 LTspice 模擬及 KiCad PCB 設計，但尚未進行實體製板、焊接與量測，因此模擬結果不代表實際硬體性能。

## 1. 電路設計（Circuit Design）

| 項目 | 設計配置 |
|---|---|
| 設計軟體 | KiCad |
| 電源輸入 | DC 12 V，J1 |
| 電晶體 Q1 | 2N3904（NPN） |
| R1 / R2 | 47 kΩ / 10 kΩ，基極偏壓 |
| R3（RC） | 4.7 kΩ，集極電阻 |
| R4（RE） | 1 kΩ，射極電阻 |
| R5（RL） | 10 kΩ，輸出負載 |
| C1 / C2 | 10 µF，輸入／輸出耦合電容 |
| J1 / J2 / J3 | 電源／訊號輸入／訊號輸出 |

![共射極放大器原理圖](images/Schematic.png)

**電路原理：** 使用 R1、R2 建立基極分壓偏壓，使 2N3904 工作於順向主動區；透過集極電阻產生電壓放大，並利用 C1、C2 隔離直流偏壓。輸出訊號相對輸入約有 180° 相位反轉。

LTspice 模擬於約 1 kHz 時得到 9.896 dB 電壓增益與 −179.83° 相位差。

## 2. PCB 佈局與 3D 檢視（PCB Layout & 3D）

本專案採用 THT 插件式元件，包含 TO-92 電晶體、軸向電阻、徑向電解電容及外部連接端子。

已完成元件配置、銅箔佈線、電路板外框及正面絲印設計。

**PCB Layout 與絲印**

![PCB 佈局與絲印](images/PCB%20Layout%20%2B%20Silkscreen.png)

電源、訊號輸入與輸出分別透過 J1、J2、J3 連接，並標示 +12V、GND、IN、OUT，方便後續焊接及量測。

**3D 檢視**

尚未收錄 3D 截圖，待完成檢視後補上。

## 3. 設計規則檢查（DRC）

![KiCad DRC 檢查結果](images/DRC%20Result.png)

| 檢查項目 | 結果 |
|---|---|
| ERC 違規 | 0 |
| DRC 違規 | 0 |
| 未連接項目 | 0 |
| 原理圖與 PCB 一致性違規 | 0 |
| 忽略的 DRC 測試類型 | 5 |

**檢查結果：** 目前啟用的 ERC／DRC 規則均未發現違規。五類忽略測試仍須在正式製造前確認。

## 4. Gerber 與鑽孔檔檢視（Gerber & Drill）

![Gerber Viewer 檢視結果](images/Gerber%20Viewer.png)

已透過 KiCad Gerber Viewer 檢視銅箔、阻焊、正面絲印及 Edge.Cuts 板框等六個 Gerber 圖層。

Excellon 鑽孔檔（.drl）仍需另外確認。

本 Repository 以設計學習紀錄為主，暫不收錄製造檔案，也尚未委託 PCB 製造。

## 5. KiCad 原始設計檔案（Source Files）

- [KiCad 專案設定（.kicad_pro）](W02_D09_CommonEmitter_Amplifier.kicad_pro)
- [電路原理圖（.kicad_sch）](W02_D09_CommonEmitter_Amplifier.kicad_sch)
- [PCB Layout（.kicad_pcb）](W02_D09_CommonEmitter_Amplifier.kicad_pcb)

可使用 KiCad 開啟專案，檢視原理圖、元件封裝、PCB 佈線及設計規則。

## 6. 設計限制與後續驗證（Limitations）

- **尚未實體驗證：** 未進行 PCB 製板、焊接及電路量測。
- **元件規格：** 實作前須確認 2N3904 腳位、電解電容極性、封裝尺寸及額定規格。
- **電路性能：** LTspice 模擬結果仍須透過示波器及函數產生器進行實測驗證。
- **製造確認：** 正式送廠前需完成鑽孔檔、忽略規則及製造規格檢查。

---

[← 返回專案列表](../README.md)
