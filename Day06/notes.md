- SIG ย่อมาจาก Special Interest Group ในบริบทของ Kubernetes SIG เป็นกลุ่มผู้มีส่วนร่วมที่มุ่งเน้นไปที่ Area หรือ Domain เฉพาะภายในโครงการ แต่ละ SIG มีหน้าที่รับผิดชอบในการดูแล มีส่วนร่วม และปรับปรุง Area ที่ได้รับมอบหมาย เช่น เครือข่าย, การจัดเก็บข้อมูล, ความสามารถในการขยายขนาด หรือเอกสารประกอบ  
เราสามารถเปรียบเทียบ SIG กับแผนกต่างๆ ในองค์กรได้ ในบริษัท แผนกที่แตกต่างกัน (เช่น การตลาด การขาย หรือวิศวกรรม) จะมุ่งเน้นไปที่ Area ที่เชี่ยวชาญเฉพาะและร่วมมือกันเพื่อบรรลุเป้าหมายร่วมกัน ในทำนองเดียวกัน SIG ใน Kubernetes จะมุ่งเน้นไปที่แง่มุมเฉพาะของโครงการและทำงานร่วมกันเพื่อพัฒนาและปรับปรุง Area เหล่านั้น

- 4C ในความปลอดภัยของ Cloud Native:
  - Code  
แนวทางปฏิบัติการเขียน Code อย่างปลอดภัย  
การ Review Code  
การ Scan หาช่องโหว่
  - Container  
Container Image ที่ปลอดภัย  
ความปลอดภัยของ Runtime  
หลักการสิทธิ์ขั้นต่ำสุด (Least Privilege)
  - Cluster  
การรักษาความปลอดภัย Kubernetes API  
การควบคุมการเข้าถึง (RBAC)  
การสื่อสารที่ปลอดภัย
  - Cloud/Infrastructure  
การรักษาความปลอดภัยโครงสร้างพื้นฐาน  
การควบคุมการเข้าถึง  
การปฏิบัติตามข้อกำหนด

- runsc (gVisor): เป็น Container Runtime แบบเบา (Lightweight) ที่ Run Container ภายใน Environment แบบ Sandbox โดยให้ Layer การแยกอิสระเพิ่มเติมด้วยการจำลอง User-space Kernel ซึ่งช่วยให้ Container มี Kernel ที่แยกออกมาโดยไม่มี Overhead ของ Virtualizaion เต็มรูปแบบ  
Kata Container: เป็นโครงการ Open-source ที่รวมความปลอดภัยของ VM เข้ากับความเร็วและความสามารถในการจัดการ Container โดยใช้ VM แบบเบาเพื่อ Run แต่ละ Container ให้การแยกอิสระที่แข็งแรงระหว่าง Container โดยไม่มี Overhead ด้านประสิทธิภาพของ VM แบบดั้งเดิม  
runsc (gVisor) และ Kata Container เป็น Container Runtime ที่ให้การแยกอิสระแบบ Sandbox เพิ่มเติมและความปลอดภัยที่สูงขึ้นเมื่อเทียบกับ Container Runtime แบบดั้งเดิมอย่าง Docker หรือ containerd

- Service Mesh Interface (SMI) เป็นข้อกำหนดสำหรับการใช้งาน Function Service Mesh ข้ามการใช้งาน Service Mesh ที่แตกต่างกัน มันให้ Standard Set ของ API สำหรับควบคุมและสังเกตพฤติกรรมของ Service Mesh ซึ่งช่วยให้เกิดความสามารถในการทำงานร่วมกันระหว่าง Solution Service Mesh ต่างๆ  
SMI เหมือนกับมาตรฐาน Remote Control สากล เช่นเดียวกับที่อุปกรณ์ Electronics จากผู้ผลิตที่แตกต่างกันสามารถควบคุมได้โดยใช้ Remote Control สากลที่เป็นไปตามมาตรฐานร่วมกัน Service Mesh ก็สามารถสื่อสารและทำงานร่วมกันได้อย่างมีประสิทธิภาพโดยใช้ข้อกำหนด SMI

- Ingress ใน Kubernetes เป็น Object API ที่จัดการการเข้าถึงจากภายนอกไปยังบริการต่างๆ ภายใน Cluster โดยให้การกำหนด Routing HTTP และ HTTPS ไปยังบริการต่างๆ ตามชื่อ Host, เส้นทาง (Path) หรือเกณฑ์อื่นๆ มัน Expose Route จากภายนอก Cluster ไปยังบริการภายใน Cluster ทำหน้าที่เสมือน Entry Point สำหรับการรับ External Traffic  
Ingress เหมือนกับประตูทางเข้าหลักของอาคาร เช่นเดียวกับที่ประตูทางเข้าหลักควบคุมการเข้าถึงไปยังส่วนหรือชั้นต่างๆ ภายในอาคาร Ingress ก็ควบคุมการเข้าถึงบริการต่างๆ ภายใน Cluster Kubernetes ตามกฎการกำหนด Routing ที่กำหนดไว้

- Cloud Native Service Discovery เป็นแง่มุมที่สำคัญของสถาปัตยกรรมระบบ Distribute โดยเฉพาะอย่างยิ่งใน Environment ของ Microservices ซึ่งช่วยให้ App และ Microservices สามารถค้นพบและสื่อสารกันและกันได้อย่าง Dynamic โดยไม่ต้อง Hardcode IP Address หรือพึ่งพาการกำหนดค่าแบบ Static วิธีนี้ช่วยให้บริการสามารถขยายขนาดได้, มีความทนทาน, และ Loosely Couple ซึ่งช่วยอำนวยความสะดวกในการสื่อสารและ Interact ภายใน Cloud Environment  
Service Discovery เหมือนกับ Directory ในอาคารสำนักงานขนาดใหญ่ เช่นเดียวกับที่ Directory ช่วยให้ค้นหาตำแหน่งของสำนักงานหรือแผนกต่างๆ ภายในอาคาร Service Discovery ก็ช่วยให้องค์ประกอบต่างๆ ภายในระบบ Distribute สามารถระบุตำแหน่งและสื่อสารกันและกันอย่าง Dynamic โดยไม่คำนึงถึงตำแหน่งเครือข่ายหรือการกำหนดค่าเฉพาะ
