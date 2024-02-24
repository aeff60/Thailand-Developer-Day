---
theme: seriph
class: text-center
background: https://cdn.discordapp.com/attachments/1008943745493897227/1210633673532252190/image.png?ex=65eb4578&is=65d8d078&hm=1ba305f9c9f734a9754505702938a2ee0da873197eb61dcfdfce3d781223138c&

highlighter: shiki
lineNumbers: true

info: |
  <style>
    .reveal {
      background-color: black;
    }
  </style>
drawings:
  persist: false
defaults:
  foo: true
transition: slide-left
title: "Azure App Service: The easy way to build and deploy REST APIs"
mdc: true

---

# Azure App Service

The easy way to build and deploy REST APIs

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
transition: fade-out
---

# Agenda



- **Introduction to Azure App Service**
- **Setting Up Your Azure App Service Environment**
- **Building REST APIs with Azure App Service**
- **Deploying REST APIs with Azure App Service**
- **Real world scenarios showcasing the use of Azure App Service for REST API**

<br>
<br>

อ่านเพิ่มเติมเกี่ยวกับ [Azure คืออิหยัง?](https://www.borntodev.com/2021/08/31/what-is-microsoft-azure/)

---

# Introduction to Azure App Service

<div align="center" style="margin-top: 30px; margin-bottom: 30px;">
  <img src="https://cdn.discordapp.com/attachments/1008943745493897227/1210626409333137468/image.png?ex=65eb3eb4&is=65d8c9b4&hm=19857232c37d6595675226104820c7df00b205d306038ce0cdf1c3b6a1142441&" alt="Azure App Service" width="300">
</div>

<div align="center">
<a href="https://azure.microsoft.com/en-us/products/app-service">Azure App Services</a> คือ บริการโฮสต์เว็บแอปพลิเคชัน เว็บ API และ Mobile Backend <br>
บนแพลตฟอร์ม Azure Cloud โดยผู้ใช้บริการไม่จำเป็นต้องกังวลเกี่ยวกับ Infrastructure ใดๆ
</div>

---

# Azure App Service ทำอะไรได้บ้าง?

<div align="center" style="margin-top: 30px; margin-bottom: 30px;">
  <img src="https://cdn.discordapp.com/attachments/1008943745493897227/1210816633971544174/image.png?ex=65ebefdd&is=65d97add&hm=4ccc4bacf31923822ecc14e11727b9f60d606964d1328ecdf3cf65e14bd86c14&" alt="Azure App Service" width="7000">
</div>


---

# สามารถใช้กับ Runtime ตัวไหนได้บ้าง?

<div align="center" style="margin-top: 30px; margin-bottom: 30px;">
  <img src="https://cdn.discordapp.com/attachments/1008943745493897227/1210817473599897631/image.png?ex=65ebf0a5&is=65d97ba5&hm=3018635cd9c9c5a96c2c3844b78a47a9498fb8e71d8c82bc18c5bcbc915ceee1&" alt="Azure App Service" width="7000">
</div>

---

# OS ไหนใช้ได้บ้าง?

<div align="center" style="margin-top: 30px; margin-bottom: 30px;">
  <img src="https://cdn.discordapp.com/attachments/1008943745493897227/1210817988739997828/image.png?ex=65ebf120&is=65d97c20&hm=48ab102de91db5a852d311710ed2567fd77ed4230d54a3973f1b113439e75959&" alt="Azure App Service" width="7000">
</div>

---


# Deploy ได้แค่ Source Code หรอ?

<div align="center" style="margin-top: 30px; margin-bottom: 30px;">
  <img src="https://cdn.discordapp.com/attachments/1008943745493897227/1210818540890882098/image.png?ex=65ebf1a4&is=65d97ca4&hm=5591e67c84d54e6c8bed43247f8b4c7eb2dc0dbfa406282ac9a97fa7b2fe25fb&" alt="Azure App Service" width="7000">
</div>

---

# CI CD ใช้ได้ป่าว?

<div align="center" style="margin-top: 30px; margin-bottom: 30px;">
  <img src="https://cdn.discordapp.com/attachments/1008943745493897227/1210818873180291072/image.png?ex=65ebf1f3&is=65d97cf3&hm=63e7df2bd3f2b5d55805effc6b83f84becbcdc048604289074c3c03eeb285421&" alt="Azure App Service" width="7000">
</div>

---

# Vertical Scale

<div align="center" style="margin-top: 30px; margin-bottom: 30px;">
  <img src="https://cdn.discordapp.com/attachments/1008943745493897227/1210819569309196298/image.png?ex=65ebf299&is=65d97d99&hm=46d97f3c8913f300d77d0521469b21f280667d6200e7d49d0beab9434f7f4c8d&" alt="Azure App Service" width="7000">
</div>

---

# Horizontal Scale

<div align="center" style="margin-top: 30px; margin-bottom: 30px;">
  <img src="https://cdn.discordapp.com/attachments/1008943745493897227/1210819973233119262/image.png?ex=65ebf2f9&is=65d97df9&hm=33539ff42c6a50c17cc148483483eb66e38a936cd5ddc70ac960cf4e261cbcc7&" alt="Azure App Service" width="7000">
</div>

---

# Horizontal Scale (Scale out)

<div align="center" style="margin-top: 30px; margin-bottom: 30px;">
  <img src="https://cdn.discordapp.com/attachments/1008943745493897227/1210821060056977408/image.png?ex=65ebf3fc&is=65d97efc&hm=312f4dfc82a1c7197f5430dbc215ed568b377a77800d04f587c37f7eadfd30f7&" alt="Azure App Service" width="7000">
</div>


---

# Vertical Scale (Scale up)

<div align="center" style="margin-top: 30px; margin-bottom: 30px;">
  <img src="https://cdn.discordapp.com/attachments/1008943745493897227/1210821346259640410/image.png?ex=65ebf440&is=65d97f40&hm=ec106ca8e794004dd5df81fd8ebb4d745a2eb01f1dc81a31878ea52911d4b1bd&" alt="Azure App Service" width="7000">
</div>

---

# Azure App Service เหมาะกับใคร?
- นักพัฒนาซอฟต์แวร์ที่ต้องการโฮสต์เว็บแอปพลิเคชัน เว็บ API หรือ Mobile Backend
- นักพัฒนาซอฟต์แวร์ที่ต้องการเริ่มต้นใช้งาน Cloud Computing
- นักพัฒนาซอฟต์แวร์ที่ต้องการประหยัดเวลาและค่าใช้จ่ายในการดูแล Infrastructure
- นักพัฒนาซอฟต์แวร์ที่ต้องการระบบที่มีความปลอดภัยสูง

---

# YouTube Clone API Example Project

<div align="center" style="margin-top: 30px; margin-bottom: 30px;">
<iframe width="750" height="415" src="https://www.youtube.com/embed/RLn2cDVNiwg?si=YZEqBUUuH-9RIBl4&amp;start=3477" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
</div>

---

## YouTube Clone API Example Project

<div align="center" style="margin-top: 30px; margin-bottom: 30px;">
  <img src="https://cdn.discordapp.com/attachments/1008943745493897227/1210824970012196904/image.png?ex=65ebf7a0&is=65d982a0&hm=d94388871d848ab2f5c34df5e821a4ec73a8ba6687ed4e588098cba433be96c7&" alt="Azure App Service" width="600"><br>
  <a href="https://github.com/aeff60/Youtube-Clone-API" >Github : Youtube Clone API</a>
</div>

---
