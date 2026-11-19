# 🔫 Tactical Guns Minecraft Bedrock Add-on (Version 0.0.1)

[![Minecraft Bedrock](https://img.shields.io/badge/Minecraft-Bedrock%201.21%2B%20--%2026.xx%2B-brightgreen.svg)](https://minecraft.net/)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20iOS%20%7C%20Android%20%7C%20Console-blue.svg)]()
[![Type](https://img.shields.io/badge/Type-Behavior%20%26%20Resource%20Pack-orange.svg)]()
[![Release](https://img.shields.io/badge/Release-v0.0.1%20Planning-blue.svg)]()

**Tactical Guns** คือ Add-on สำหรับ **Minecraft Bedrock Edition** ที่นำเสนอระบบอาวุธปืนสไตล์ Tactical FPS (CS:GO / Valorant) เข้าสู่โลกมายคราฟต์แบบสมดุล สนุก และลื่นไหล โดยมุ่งเน้นการใช้งานระบบ **Pure JSON** แท้ ไม่ต้องเปิดใช้งาน Experimental Script API ทำให้รองรับข้ามแพลตฟอร์มได้อย่างเสถียร 100%

---

## 🎯 แผนพัฒนาเวอร์ชัน 0.0.1 (Version 0.0.1 Roadmap)

ในเวอร์ชันตั้งต้น 0.0.1 โปรเจกต์มุ่งเน้นการสร้างปืนกระบอกแรก **Glock-18**:

### 1. ⚡ Full-Automatic Machine Pistol
- รองรับการยิงรัวแบบ **Full-Automatic** (กดคลิกขวาค้างเพื่อยิงรัวต่อเนื่องเป็นชุด) ให้ความรู้สึกกระชับหนักแน่น

### 2. 🎯 บัลลิสติกส์กระสุนสมจริง (High-Velocity Projectile)
- กระสุนบินเร็วสูงพิเศษ (High Velocity) แรงโน้มถ่วงต่ำมาก ทำให้วิถีกระสุนพุ่งตรงเข้าเป้าหมายแบบเกือบไร้ความโค้ง
- ดาเมจสมดุล 4–5 หน่วย (2–2.5 หัวใจต่อนัด)

### 3. ♾️ กระสุนไม่จำกัดสำหรับทดสอบ (Infinite Ammo)
- ในเวอร์ชัน 0.0.1 ปืนสามารถยิงได้ไม่จำกัด เพื่อโฟกัสการทดสอบฟิสิกส์กระสุน อัตราการลั่นไก เสียง และแรงปะทะได้อย่างเต็มที่ (ระบบแม็กกาซีน 20 นัด และไอเทมกระสุน 9mm จะได้รับการอัปเดตใน v0.0.2)

### 4. 🗡️ สไตล์ภาพ 2D Handheld Extrusion
- แสดงผลด้วยภาพ 2D Pixel Art เมื่อถือในมือจะมีความหนา 3D แบบ Handheld Extrusion กลมกลืนกับดาบและไอเทมดั้งเดิมของ Minecraft

### 5. 🛠️ การได้มาและสูตรคราฟต์ (Acquisition)
- **Creative Mode:** ค้นหาได้ในแท็บ **Equipment**
- **Command:** `/give @s gun:glock18`
- **Survival Crafting Recipe:** สามารถคราฟต์ได้โดยใช้แท่งเหล็ก (Iron Ingot) และดินปืน (Gunpowder)

---

## 📚 เอกสารและการออกแบบสถาปัตยกรรม (Documentation)

- [DESIGN_ALIGNMENT.md](./DESIGN_ALIGNMENT.md) - สรุปข้อตกลงการออกแบบและข้อมูลจำเพาะเชิงลึก
- [GLOSSARY.md](./GLOSSARY.md) - คำศัพท์เฉพาะทางของโดเมนปืนในโปรเจกต์
- [docs/adr/0001-pure-json-architecture.md](./docs/adr/0001-pure-json-architecture.md) - สถาปัตยกรรม Pure JSON
- [docs/adr/0002-infinite-ammo-v001.md](./docs/adr/0002-infinite-ammo-v001.md) - การใช้ Infinite Ammo ใน v0.0.1
- [docs/adr/0003-handheld-2d-extruded-item.md](./docs/adr/0003-handheld-2d-extruded-item.md) - การแสดงผลโมเดล 2D Extruded

---

## 🎮 เวอร์ชันที่รองรับ (Compatibility)

- **Minecraft Bedrock Edition:** รองรับเวอร์ชัน **1.21.xx จนถึง 26.xx+ ขึ้นไป**
- ใช้งานได้บนทุกแพลตฟอร์ม (Windows, Android, iOS, Xbox, PlayStation, Nintendo Switch)
