- runC เป็น Native Runtime ที่สอดคล้องกับ Open Container Initiative (OCI)
  
- https://medium.com/@sathabhronchangchuea/kubernetest-ความเเตกต่างระว่าง-deployments-statefulsets-daemonsets-1ea91453e61e
  
- CronJob Controller: รับผิดชอบในการจัดการ CronJob โดยจะจัดตารางการทำงานของ Job ตามกำหนดการของ CronJob (เช่น ทุกชั่วโมง)  
Job Creation: เมื่อถึงเวลาที่ CronJob ต้องทำงาน มันจะสร้าง Resource Job ซึ่ง Job นี้เป็นตัวแทนของงานที่ต้องดำเนินการ  
Job Controller: เมื่อ Job ถูกสร้างขึ้นแล้ว มันจะรับผิดชอบในการจัดการ Job นี้ โดยทำให้มั่นใจว่า Pod ที่ระบุโดย Job ได้ถูกสร้างและทำงานสำเร็จ  
Pod Execution: Job Controller สร้าง Pod หนึ่งตัวหรือมากกว่าตามข้อกำหนดของ Job โดย Pod เหล่านี้จะดำเนินการ (Execute) ตามงานที่กำหนดโดย Job และ Job Controller จะรอจนกว่า Pod จะทำงานเสร็จสมบูรณ์  
CronJob Controller สร้าง Job จากนั้น > Job Controller สร้าง Pod และรอจนกว่าจะทำงานเสร็จ

- kubelet คือตัว Agent ที่ทำงานบนทุก Node ใน Cluster มีหน้าที่ดูแลให้ Container ทำงานอยู่ภายใน Pod

- โดย Default, API Server อนุญาตให้ทำคำขอทั้งหมด (--authorization-mode=AlwaysAllow) อย่างไรก็ตาม สำหรับ Production Environment แนะนำให้ใช้ Mode การอนุญาตที่เข้มงวดมากขึ้น เช่น RBAC (การควบคุมการเข้าถึงตามบทบาท) หรือ Node

- การใช้ประโยชน์จาก Kubernetes Cluster Autoscaler เพื่อให้เริ่มและหยุด Node โดยอัตโนมัติตามความต้องการ เป็นวิธีที่คุ้มค่าที่สุด  
Burst Processing ได้รับประโยชน์จากความยืดหยุ่นที่ Cluster Kubernetes บน Cloud มอบให้ ด้วย Kubernetes Cluster Autoscaler คุณสามารถขยาย Cluster ของคุณเมื่อมีความต้องการ Resource เพิ่มเติม (เช่น เช้าวันจันทร์เมื่อ Batch Job ต้องทำงาน) และลดขนาดลงในช่วงที่มีความต้องการต่ำ (เช่น หลังจาก Batch Job เสร็จสิ้น) ซึ่งทำให้มั่นใจได้ว่าคุณจ่ายเงินเฉพาะสำหรับ Resource ที่คุณต้องการจริงเท่านั้น หลีกเลี่ยงการจัดสรร Resource มากเกินไป และลดต้นทุน
