# Design Alignment Summary (สรุปข้อตกลงและสถาปัตยกรรมโปรเจกต์)

**โปรเจกต์:** Tactical Guns Add-on (v0.0.1)  
**แพลตฟอร์มเป้าหมาย:** Minecraft Bedrock Edition (รองรับเวอร์ชัน 1.21.xx จนถึง 1.26.xx+ ขึ้นไป)  
**สไตล์เกมเป้าหมาย:** Tactical Shooter (CS:GO / Valorant)  
**เป้าหมายเวอร์ชัน 0.0.1:** ปืน Glock-18 จำนวน 1 กระบอก  
**วันที่จัดทำ:** 19 พฤศจิกายน 2026  

---

## 1. วัตถุประสงค์หลัก (Core Objectives)
สร้างระบบอาวุธปืน Tactical ใน Minecraft Bedrock Edition โดยประเดิม v0.0.1 ด้วยปืนพกกลยอดนิยม **Glock-18**:
1. ให้ความรู้สึกการยิงแบบเกม Tactical FPS ยอดนิยม (CS:GO / Valorant) แต่ผสานเข้ากับโลก Minecraft ได้อย่างลงตัว
2. รองรับการยิงแบบ **Full-Automatic** (กดคลิกขวาค้างเพื่อยิงรัวต่อเนื่องเป็นชุด)
3. ใช้ระบบ **Pure JSON** (Behavior Pack + Resource Pack) ไม่ต้องพึ่งพา Script API หรือ Experimental Gameplay ที่อาจเสี่ยงต่อการหลุดอัปเดต
4. รูปลักษณ์ 2D Pixel Art พร้อมความหนาแบบ 3D Extrusion (เหมือนถือดาบและเครื่องมือในเกมวานิลลา)
5. กระสุนความเร็วสูง (High Velocity) วิถีพุ่งตรงสมจริง ดาเมจสมดุล 4–5 หน่วย (2–2.5 หัวใจ)

---

## 2. ข้อมูลจำเพาะทางสถาปัตยกรรม (Architectural Specifications)

### 2.1 เวอร์ชันและโครงสร้างแพ็กเกจ (Version & Compatibility)
- **Min Engine Version:** `[1, 21, 0]` (การันตีความเข้ากันได้ตั้งแต่ 1.21.0 ถึง 1.26.xx+)
- **Format Version:** `2` สำหรับ `manifest.json` และ `1.20.80` / `1.21.0` สำหรับ Item / Entity Definitions
- **Namespace:** `gun:`
- **รหัสไอเทมและเอนทิตี:**
  - ตัวปืน: `gun:glock18`
  - เอนทิตีกระสุน: `gun:bullet`
- **โครงสร้างแพ็กเกจ (Dual-Pack Structure):**
  - **Behavior Pack (`GunAddon_BP`):**
    - `manifest.json`
    - `items/gun_glock18.json` (คอมโพเนนต์การยิง, Cooldown, หมวดหมู่ Creative)
    - `entities/gun_bullet.json` (ฟิสิกส์กระสุน, ดาเมจ, ความเร็ว, วิถีพุ่งตรง)
    - `recipes/gun_glock18.json` (สูตรคราฟต์ Survival)
  - **Resource Pack (`GunAddon_RP`):**
    - `manifest.json`
    - `textures/item_texture.json` (Texture definition)
    - `textures/items/glock18.png` (2D Pixel Art ปืน Glock-18)
    - `texts/en_US.lang` (Localization ชื่อปืน)

---

## 3. รายละเอียดกลไกการทำงาน (Gameplay Mechanics)

### 3.1 การลั่นไกและโหมดการยิง (Firing Mode & Rate of Fire)
- **โหมดการยิง:** Full-Automatic (กดคลิกขวาค้างเพื่อยิงรัว)
- **Cadence / Delay:** อัตราการลั่นต่อเนื่องสม่ำเสมอผ่านคอมโพเนนต์ `minecraft:throwable` / `minecraft:projectile` หรือ Event Looping ที่ให้จังหวะลั่นไกสมจริง
- **การใช้กระสุน (v0.0.1):** **Infinite Ammo** (ยิงฟรีไม่มีวันหมด) เพื่อเน้นทดสอบฟิสิกส์กระสุน แรงปะทะ การแสดงผล และดาเมจ ก่อนพัฒนาเป็นระบบแม็กกาซีน 20 นัด และไอเทมกระสุน 9mm ใน v0.0.2

### 3.2 บัลลิสติกส์และความแรงกระสุน (Ballistics & Damage)
- **ความเร็ว (Velocity):** ค่าสูง (ประมาณ 4.0 - 5.0) เคลื่อนที่เร็วเสมือนกระสุนจริง
- **แรงโน้มถ่วง (Gravity):** ต่ำมาก (0.00 - 0.01) ทำให้กระสุนพุ่งตรงเข้าเป้าหมายในระยะหวังผล ไม่ย้อยตกพื้นเร็วเหมือนลูกธนู
- **พลังโจมตี (Direct Damage):** 4–5 แต้มต่อหนึ่งนัด (เทียบเท่า 2 ถึง 2.5 หัวใจ) ให้ความรู้สึกสมดุลเมื่อยิงรัวใส่ศัตรู

### 3.3 เสียงและภาพ (Audio & Visuals)
- **เสียงลั่นไก:** ใช้เสียงวานิลลาของ Minecraft (เช่น `random.bow` หรือ `crossbow.shoot` ที่มีระดับเสียงกระชับ)
- **โมเดลและมุมมอง:** ภาพ 2D Pixel Art คุณภาพสูง ขนาด 16x16 หรือ 32x32 เมื่อผู้เล่นถือในมือ (ทั้ง First-person และ Third-person) ตัวเกมจะทำการยืดความหนาเป็น 3D (Handheld extrusion) เช่นเดียวกับดาบและอุปกรณ์ดั้งเดิมของเกม

### 3.4 การได้รับไอเทม (Acquisition)
1. **Creative Mode:** ค้นหาได้ในแท็บ **Equipment** (หมวดหมู่อาวุธ)
2. **Commands:** `/give @s gun:glock18`
3. **Survival Crafting Recipe:**
   - วัตถุดิบ: **Iron Ingot (แท่งเหล็ก)** + **Gunpowder (ดินปืน)**
