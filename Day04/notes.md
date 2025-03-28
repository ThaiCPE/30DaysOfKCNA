- Kubernetes Cluster Autoscaler ช่วยให้คุณจัดการจำนวน Node ใน Cluster ของคุณโดยอัตโนมัติเพื่อตอบสนองต่อความต้องการ

- OPA (Open Policy Agent) คือเครื่องมือกำหนด Policy อเนกประสงค์ที่สามารถใช้เพื่อบังคับใช้ Policy ข้ามระบบต่างๆ รวมถึง Kubernetes  
ใน Kubernetes, OPA สามารถถูก Integrate เพื่อตรวจสอบ (Validate) คำขอการเข้าถึง บังคับใช้ (Apply) Policy สำหรับการสร้าง Resource และบังคับใช้ Custom Policy สำหรับความปลอดภัย, Compliance, และข้อกำหนดอื่นๆ

- IaC ย่อมาจาก Infrastructure **as** Code

- ใน Framework แบบ Serverless Dev ไม่จำเป็นต้องจัดการกับ Capacity, การ Deploy, การปรับขนาด, ความทนทานต่อความล้มเหลว และระบบปฏิบัติการอีกต่อไป

- Container Orchestration เกี่ยวข้องกับการจัดการ App ที่อยู่ในรูปแบบ Container โดยอัตโนมัติ ซึ่งรวมถึงการ Deploy, การปรับขนาด, เครือข่าย และการจัดการ App Lifecycle เหล่านั้น หนึ่งในคุณลักษณะสำคัญคือ Dynamic Scheduling ซึ่งหมายถึงความสามารถในการวาง Container บน Node ที่เหมาะสมที่สุดใน Cluster โดยอัตโนมัติ โดยพิจารณาจากความพร้อมของ Resource, ข้อจำกัด และ Policy ต่างๆ

- StatefulSets ใช้สำหรับ App ที่รักษาสถานะถาวรหรือมีเอกลักษณ์เฉพาะตัว เช่น ฐานข้อมูล แต่ละ Pod ใน StatefulSet โดยทั่วไปจะมีชื่อที่ไม่ซ้ำกัน และจำเป็นต้อง Discovery และสื่อสารระหว่าง Pod เหล่านี้อย่างสม่ำเสมอ แม้แต่เมื่อมีการปรับขนาดเพิ่มหรือลด  
StatefulSets อาจเป็นเหมือนการจัดการ Team พนักงานในองค์กร พนักงานแต่ละคนมีชื่อที่ไม่ซ้ำกันและหน้าที่เฉพาะ แม้ว่า Team จะเติบโตหรือเล็กลง ก็สำคัญที่จะต้องรักษาการสื่อสารที่สม่ำเสมอระหว่างพวกเขา ดังนั้น คุณจึงต้องการระบบการสื่อสาร (Service) ที่สามารถระบุตำแหน่งของพนักงานแต่ละคนได้อย่างเชื่อถือได้ โดยไม่คำนึงถึงการเปลี่ยนแปลงใน Team
