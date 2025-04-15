- Stateful Set ต้องการ Headless Service สำหรับ Network Identity ของ Pod  
Headless Service เป็นประเภทของ Service ที่ไม่มี ClusterIP และจะส่งคืน IP Address ของ Pod โดยตรงเมื่อมีการค้นหา DNS ซึ่งทำให้แต่ละ Pod ใน StatefulSet มี Network Identity ที่คงที่และคาดเดาได้ในรูปแบบ <pod-name>.<service-name>.<namespace>.svc.cluster.local

![image](https://github.com/user-attachments/assets/715e7b3b-848b-469b-99bb-68e9e63fac53)

- Service Mesh คือชื่อของเครื่องมือที่จัดการการสื่อสารระหว่าง Pod โดย Inject Sidecar Proxy Container เข้าไปในแต่ละ Pod และนำทาง Traffic เครือข่ายผ่าน Proxy Container นั้น ตัวอย่างของ Service Mesh ที่นิยมใช้คือ Istio, Linkerd และ Consul Connect ซึ่งช่วยให้สามารถจัดการ Traffic ระหว่าง Microservices, การรักษาความปลอดภัย และการตรวจสอบการสื่อสารได้โดยไม่ต้องแก้ไข Code ของ App

- Workload เป็น App ที่ทำงานบน Kubernetes

- วิศวกรรมความน่าเชื่อถือ (SRE) มีคำจำกัดความดังนี้:
SLI (Service Level Indicator) คือการวัดเชิงปริมาณของลักษณะบางอย่างของระดับการให้บริการที่มอบให้
SLA (Service Level Agreement) มักเป็นสัญญาตามกฎหมายที่กำหนดระดับบริการที่ตกลงกันกับลูกค้าหรือผู้ใช้สำหรับระยะเวลาที่ยาวกว่า (เช่น ทั้งปี) และมักมีการระบุบทลงโทษหรือผลที่ตามมาทางกฎหมายหากไม่สามารถปฏิบัติตามได้
SLO (Service Level Objective) เป็นเป้าหมายภายในที่มักจะเข้มงวดกว่า SLA และมักถูกวัดในระยะเวลาสั้นกว่า (เช่น รายเดือน) เพื่อให้แน่ใจว่า Team สามารถตอบสนองต่อปัญหาก่อนที่จะส่งผลกระทบต่อ SLA
โดยทั่วไป SLO มักจะเข้มงวดกว่า SLA เพื่อให้มี "Buffer" สำหรับการแก้ไขปัญหาก่อนที่จะเกิดการละเมิด SLA ซึ่งอาจนำไปสู่ผลกระทบทางกฎหมายหรือการเงิน

![image](https://github.com/user-attachments/assets/27be23ef-9f35-4893-9644-4799c030a2d0)
