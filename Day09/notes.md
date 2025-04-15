- Stateful Set ต้องการ Headless Service สำหรับ Network Identity ของ Pod  
Headless Service เป็นประเภทของ Service ที่ไม่มี ClusterIP และจะส่งคืน IP Address ของ Pod โดยตรงเมื่อมีการค้นหา DNS ซึ่งทำให้แต่ละ Pod ใน StatefulSet มี Network Identity ที่คงที่และคาดเดาได้ในรูปแบบ <pod-name>.<service-name>.<namespace>.svc.cluster.local

![image](https://github.com/user-attachments/assets/715e7b3b-848b-469b-99bb-68e9e63fac53)

