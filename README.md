ทำแอพเล่นๆ (จริงๆแค่ HTML) เพราะจะไปเดินงาน SET in The City 2026 ซึ่งเคยไปเดินงานอื่นที่คล้ายๆแบบนี้ จะยืนงงว่า ต้องเดินไปตรงไหนยังไง ตอนอยู่ในงาน 

# SET in the City 2026 Agenda App — Release Notes

> Changelog สำหรับแนบใน GitHub Release / README  
> เรียงจาก version ล่าสุดไปเก่าสุด  
> Project: SET in the City 2026 mobile-first agenda planner  
> Maintainer note: บางรายการของ v1–v6 เป็นสรุปจากลำดับการพัฒนาและ feedback ระหว่างทำงาน ไม่ใช่ diff ทางเทคนิคแบบ commit-by-commit

---

## v9 — 2026-06-20

### Highlights
- ปรับ **My Plan** ให้เป็น timeline มากขึ้น โดยเรียงตามลำดับเวลาเป็นหลัก
- เพิ่ม **Table Header Filter** แบบง่าย คล้าย Excel filter สำหรับหน้า Table
- เหมาะสำหรับการใช้งานจริงระหว่างเดินงาน เพราะเห็นลำดับ session ตามเวลาได้ชัดขึ้น

### New Features
- เพิ่ม **My Plan Timeline**
  - แสดงรายการใน My Plan ตามลำดับเวลา
  - ไม่แยกกลุ่ม “เวลาชนกัน” ไปแสดงก่อนรายการอื่นทั้งหมดแล้ว
  - ถ้ามี session ที่เวลา overlap กัน ระบบจะ group เฉพาะช่วงเวลาที่ชนกันไว้ในตำแหน่งเวลาจริง
  - ช่วยให้ดูแผนการเดินงานตามเวลาได้ต่อเนื่องกว่าเดิม

- เพิ่ม **Table Header Filter**
  - เพิ่มปุ่ม `▼` ที่หัว column ในหน้า Table
  - กดเพื่อเลือกดูเฉพาะค่าที่ต้องการใน column นั้น
  - เริ่มรองรับ filter ใน column ที่เหมาะกับการใช้งานจริง:
    - Priority
    - Suggestion
    - My Choice
    - Date
    - Room
    - Stage

### Improvements
- ปรับหน้า My Plan ให้ลดความสับสนเมื่อตารางเวลาชนกัน
- ปรับ count/status ในหน้า Table ให้แสดงจำนวน row หลัง filter
- เพิ่ม visual state ให้ header filter ที่กำลัง active
- Footer version updated to `v9, 2026-06-20 by a(-_-)m`

### Fixes
- แก้พฤติกรรม My Plan เดิมที่แสดงกลุ่มเวลาชนกันก่อนรายการอื่น ทำให้ลำดับเวลาไม่ต่อเนื่อง
- ลดความสับสนจากกรณี session ช่วงบ่ายที่เวลา overlap กันถูกแสดงก่อน session ช่วงเช้า

### Notes
- Table Header Filter กระทบเฉพาะหน้า Table เท่านั้น
- Agenda, Posters, My Plan, Go / Maybe choices และ Copy Journey ยังคงทำงานตามเดิม
- ข้อมูล Go / Maybe ยังใช้ localStorage key เดิม จึงควรรักษาแผนที่เลือกไว้ได้ใน browser เดิม

---

## v8 — 2026-06-19

### Highlights
- ปรับปรุง UI ของ Priority checkbox ให้แสดงสถานะ checked / unchecked ชัดเจนขึ้น
- แก้ปัญหาบาง browser หรือ mobile webview ที่ checkbox ทำงานได้ แต่เครื่องหมายเลือกไม่แสดงบนหน้าจอ

### Improvements
- เปลี่ยน Priority checkbox เป็น custom visual checkbox
  - Checked: แสดงกล่องสีเขียวพร้อมเครื่องหมาย ✓
  - Unchecked: แสดงกล่องว่าง
- คง logic การ filter P1–P4 เหมือนเดิม
- Footer version updated to `v8, 2026-06-19 by a(-_-)m`

### Fixes
- แก้ปัญหา checkbox ใน Priority filter ที่บางเครื่องมองไม่เห็นสถานะ check/uncheck
- ลดความเสี่ยงจากการพึ่ง native checkbox rendering ของ browser

### Notes
- เป็น version ที่แก้เฉพาะ UI rendering ของ checkbox โดยไม่เปลี่ยนโครงสร้างข้อมูลหลัก

---

## v7 — 2026-06-19

### Highlights
- รุ่น baseline ที่ใช้งานได้ดีสำหรับ mobile-first agenda planner
- รวม Agenda, Posters และ Table ไว้ในไฟล์ HTML เดียว ใช้งาน offline ได้
- รองรับการเลือกแผนด้วย Go / Maybe และ Copy Journey

### Features
- เพิ่ม tab หลัก:
  - Agenda
  - Posters
  - Table
- เพิ่ม quick filters:
  - ทั้งหมด
  - แนะนำ P1-P2
  - เวลาชนกัน
  - My Plan
- เพิ่ม filters หลัก:
  - Date filter
  - Priority filter P1–P4
  - Room filter
  - Search by topic / speaker / room
- เพิ่ม decision buttons:
  - Go
  - Maybe
- เพิ่ม My Plan พร้อม toggle `รวม Maybe ใน My Plan`
- เพิ่ม Copy Journey สำหรับคัดลอกแผนไปแชร์หรือนำไปใช้ต่อ
- เพิ่ม Clear Go Plan และ Clear Maybe
- เพิ่ม Posters tab สำหรับแสดงภาพ poster ของงาน
- เพิ่ม Raw Table tab สำหรับดูข้อมูล agenda ทั้งหมด

### Improvements
- เปลี่ยนชื่อ tab จาก Ads เป็น Posters เพื่อให้ตรงกับเนื้อหาจริง
- ปรับ title หลักเป็น `SET in the City 2026`
- เพิ่ม footer version info
- ปรับ Table ให้มี column:
  - My Choice
  - Suggestion

### Notes
- Single-file offline HTML app
- No external libraries required
- User choices stored locally in browser using localStorage
- รุ่นนี้เป็น baseline ที่ผ่านการใช้งานจริงก่อนต่อยอดเป็น v8/v9

---

## v6 — 2026-06-19

### Highlights
- ปรับปรุง My Plan และ Copy Journey ให้เหมาะกับการใช้งานจริงมากขึ้น
- ลดความซับซ้อนของ decision model ให้เหลือสถานะหลักที่ใช้จริง

### Improvements
- ปรับ decision model เป็น:
  - Go
  - Maybe
  - ไม่มีสถานะ = ไม่สนใจ / ยังไม่เลือก
- ลดความซับซ้อนจาก status เดิม เช่น Backup / Skip / Conflict
- ปรับ My Plan ให้รองรับการรวม Maybe แบบ optional
- เพิ่ม logic สำหรับ clear เฉพาะ Go และ clear เฉพาะ Maybe
- ปรับข้อความ confirm ก่อนล้างรายการให้ชัดเจนขึ้น

### Fixes
- ลดความสับสนจากการใช้หลายสถานะมากเกินไป
- แยกการล้าง Go และ Maybe ออกจากกัน เพื่อไม่ให้ผู้ใช้ลบแผนผิดกลุ่ม

### Notes
- การตรวจเวลาชนกันยังคำนวณจากรายการใน My Plan
- Maybe จะถูกนำมาคิดใน My Plan เฉพาะเมื่อเปิด `รวม Maybe ใน My Plan`

---

## v5 — 2026-06-19

### Highlights
- เพิ่ม/ปรับ **Copy Journey** ให้เหมาะกับ mobile และ browser ที่มีข้อจำกัดเรื่อง clipboard
- ทำให้การคัดลอกแผนเป็น action ที่ปลอดภัยและไม่เปลี่ยนข้อมูลใน localStorage

### New Features
- เพิ่ม Copy Journey modal
  - เมื่อกด Copy Journey จะสร้างข้อความ Journey จาก My Plan
  - พยายาม copy เข้า clipboard อัตโนมัติ
  - ถ้า copy สำเร็จ แสดง toast และปิด modal อัตโนมัติ
  - ถ้า copy ไม่สำเร็จ คง modal ไว้เพื่อให้ผู้ใช้ copy ด้วยตัวเอง

### Improvements
- Copy Journey เป็น read-only action
  - ไม่ clear แผน
  - ไม่เปลี่ยน Go / Maybe
  - ไม่แก้ localStorage
- ข้อความ Journey แสดงตามลำดับเวลาและมี warning เมื่อเวลาอาจชนกัน
- ปรับ toast message ให้สื่อสารชัดเจน:
  - `Copy Journey แล้ว !`
  - `Copy Journey ไม่สำเร็จ !!`

### Fixes
- ลดความเสี่ยงจาก browser ที่ block Clipboard API
- ลดจำนวนปุ่มใน modal เพื่อไม่ให้ผู้ใช้สับสน

---

## v4 — 2026-06-19

### Highlights
- ปรับโครงสร้าง controls ให้เหมาะกับ mobile มากขึ้น
- ใช้ accordion/collapse เพื่อไม่ให้หน้าแรกแน่นเกินไป

### Improvements
- จัดกลุ่ม controls เป็น:
  - View
  - Date
  - Filters
- ค่าเริ่มต้นบน mobile:
  - View เปิดอยู่
  - Date ปิดอยู่
  - Filters ปิดอยู่
- ค่าเริ่มต้นบน desktop/tablet:
  - controls สำคัญสามารถเปิดเพื่อใช้งานได้สะดวกขึ้น
- ปรับ Quick Filters ให้ใช้งานเป็นลำดับ:
  - ทั้งหมด
  - แนะนำ P1-P2
  - เวลาชนกัน
  - My Plan

### Fixes
- ลดความแน่นของ UI บนหน้าจอมือถือ
- ทำให้ผู้ใช้เริ่มจาก view ที่แนะนำได้เร็วขึ้น

---

## v3 — 2026-06-19

### Highlights
- เพิ่ม Posters tab และจัดระเบียบภาพ poster ให้เป็นส่วนหนึ่งของ app
- ทำให้ไฟล์ HTML ใช้งานเป็นเอกสารอ้างอิงภาพ poster ได้โดยไม่ต้องเปิดไฟล์แยก

### New Features
- เพิ่ม Posters tab สำหรับแสดงภาพ poster/ภาพประกอบงาน
- จัด poster เป็น card แนวตั้ง เหมาะกับ mobile
- เพิ่ม poster title เพื่อให้รู้ว่าแต่ละภาพเกี่ยวกับ section ไหน

### Improvements
- แยกการดู agenda ออกจากการดู poster
- ลดความสับสนจากการนำภาพ poster ไปปนในหน้า Agenda
- ทำให้ app เป็น single-file offline reference ได้มากขึ้น

### Notes
- ภาพ poster ถูกฝังใน HTML เพื่อให้ใช้งานแบบ offline และแชร์ไฟล์เดียวได้

---

## v2 — 2026-06-19

### Highlights
- ยกระดับจาก agenda table ธรรมดาเป็น mobile-first agenda picker
- เพิ่ม card-based layout เพื่อให้อ่านง่ายบนมือถือ

### New Features
- เพิ่ม Agenda card layout
- เพิ่ม Priority P1–P4
- เพิ่ม Room filter
- เพิ่ม Search
- เพิ่ม conflict view สำหรับดู session ที่เวลา overlap กัน
- เพิ่ม localStorage เพื่อเก็บการเลือกของผู้ใช้ใน browser

### Improvements
- ลดการพึ่งพาตารางแนวนอนบนมือถือ
- ทำให้แต่ละ session อ่านง่ายขึ้นด้วย card ที่มี:
  - เวลา
  - ห้อง
  - หัวข้อ
  - วิทยากร
  - ความเห็น/คำแนะนำ
  - ปุ่มเลือกแผน

### Notes
- เป็นช่วงแรกที่ app เริ่มทำหน้าที่เป็น “agenda planner” มากกว่า “agenda list”

---

## v1 — 2026-06-19

### Highlights
- Initial version ของ SET in the City 2026 mobile agenda app
- สร้างจากข้อมูล agenda ที่รวบรวมจาก poster/หน้า event และจัดเป็น HTML ใช้งานง่าย

### Features
- Single-file HTML
- แสดงรายการ agenda จากข้อมูลที่จัดโครงสร้างแล้ว
- รองรับการเปิดใช้งานบน mobile browser
- ใช้งานได้โดยไม่ต้องติดตั้ง app
- ไม่ต้องใช้ external libraries

### Notes
- v1 เป็น proof-of-concept สำหรับเปลี่ยน agenda จากรูป/ตารางให้เป็นหน้าดูงานแบบ mobile-friendly
- หลังจาก v1 จึงค่อยพัฒนาไปสู่ filter, My Plan, Posters, Table และ Copy Journey ใน version ถัดไป

---

## Current Recommended Download Asset Name

สำหรับ GitHub Release แนะนำให้ใช้ asset filename คงที่:

```text
SET_in_the_City_2026_by_AOM.html
```

Latest download URL:

```text
https://github.com/aomemail/SET_in_the_City/releases/latest/download/SET_in_the_City_2026_by_AOM.html
```

เมื่อออก version ใหม่ ให้ upload release asset ด้วยชื่อไฟล์เดิม เพื่อให้ URL เดิมชี้ไปยัง version ล่าสุดได้เสมอ

