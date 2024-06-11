[Revisiting React Data Fetching](https://techup.notion.site/Revisiting-React-Data-Fetching-a33430b64b374ab6876b20165fa16f2d)

# Instruction
- ให้อ่านคำอธิบายของแต่ละ Mission แล้วลองเขียนโค้ดตาม Mission
- ก่อนเริ่ม Mission ให้ Clone Repo อันนี้ 
 - ให้ติดตั้ง Package ที่จำเป็นของทั้ง Client และ Server ก่อน
 - ด้วยการพิมพ์ Command npm install
 - อย่าลืมนำว่าก่อน npm install ต้อง cd เข้าไปใน Folder ให้ถูกต้องก่อน
- เว็บไซต์จะเป็นแนว E-Commerce (เว็บไซต์ขายของ)

# Mission #4 (State, Data Fetching, Rendering Lists)
- Goal: ทำให้ผู้ใช้งานสามารถเห็นรายการสินค้าบนหน้าเว็บไซต์ได้
- ให้ Checkout ไปที่ Branch mission-4-start ด้วยการพิมพ์ Command git checkout mission-4-start เพื่อเริ่มทำ Mission
- API Document
 - Endpoint ของ Server คือ http://localhost:4000
 - Server ได้กำหนด API ไว้ดังนี้
   
    
    | HTTP Methods| Endpoint           | Description |
    | ---         | ---                 | ---           |
    | GET         | <endpoint>/products | API ที่เอาไว้ดูข้อมูลสินค้าทั้งหมด |



Steps
- Todo 1: ให้ Import ตัว Package ชื่อ axios และให้ Import ตัว React Hook Function ชื่อ useState และ useEffect จาก Package ชื่อ react
เช่น
import axios from "axios";
import { useState, useEffect } from "react";

​
- Todo 2: ให้ Declare ตัว State ชื่อ products มารอรับ Data จาก Server เช่น
const [products, setProducts] = useState([]);
​
- Todo 3: Declare ตัว Function getProducts เพื่อเอาไว้สร้าง Request ไปขอข้อมูลจาก Server
- Todo 4: ใช้ useEffect เพื่อ Execute Function getProducts เมื่อ Component ถูก Render ครั้งแรก เช่น
useEffect(() => {
	Execute ตัว Function ที่อยากให้ทำงานตอน Component Render แค่ครั้งแรกครั้งเดียวเท่านั้น
}, []);
​
- Todo 5: นำข้อมูลจาก State products มา Render ด้วย Array.map เช่น
{
  products.map((item) => {
    return (
      // Component ที่อยากจะ Render เป็น List
    );
  })
}



# Mission #4-1 (State, Data Fetching, Rendering Lists)
- Goal:  ทำให้ผู้ใช้งานค้นหาสินค้าบนหน้าเว็บไซต์ได้
- ให้ Checkout ไปที่ Branch mission-4-1-start ด้วยการพิมพ์ Command git checkout mission-4-1-start เพื่อเริ่มทำ Mission
- API Document
 - Endpoint ของ Server คือ http://localhost:4000
 - Server ได้กำหนด API ไว้ดังนี้

| HTTP Methods | Endpoint                           | Description     |
| ---         | ---                                 | ---             |
| GET         | <endpoint>/products?search=<คำค้นหา>  | API ที่เอาไว้ค้นหาสินค้า |
