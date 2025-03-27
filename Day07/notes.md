- ในสถาปัตยกรรมของ Service Mesh, Service Proxy (เช่น Envoy, Linkerd Proxy หรือ Istio Sidecar) จะถูกนำไปใช้คู่กับ Instance ของแต่ละบริการ เพื่อจัดการการสื่อสารระหว่างบริการต่างๆ  
Control Plane ประกอบด้วย Component ต่างๆ ที่มีหน้าที่รับผิดชอบในการกำหนดค่า, จัดการ, และตรวจสอบพฤติกรรมของ Service Proxy ซึ่งรวมถึงคุณสมบัติต่างๆ เช่น:
  - Traffic Routing
  - Load Balancing
  - การเข้ารหัส
  - การพิสูจน์ตัวตน (Authentication)
  - Observability  

  องค์ประกอบเหล่านี้ทำงานร่วมกันเพื่อ Enable ความสามารถขั้นสูงใน Traffic Management, ความปลอดภัย, และ Observability ใน Microservices Environment แบบ Distribute

- Rook เป็นเครื่องมือที่มีคุณสมบัติต่างๆ เช่น:
  - การปรับขนาดอัตโนมัติ (Self-scaling)
  - การซ่อมแซมตัวเอง (Self-healing)
  - การตรวจสอบและติดตาม (Monitoring)
  - การทำให้งานจัดการจัดเก็บข้อมูลเป็นอัตโนมัติ  

  Rook ช่วยลดความซับซ้อนในการจัดการระบบจัดเก็บข้อมูลแบบ Distribute และรวมเข้ากับ Kubernetes อย่างราบรื่น ช่วยให้ผู้ดูแลระบบสามารถ Deploy และจัดการ Cluster จัดเก็บข้อมูลได้ง่ายเช่นเดียวกับการ Deploy Resource Kubernetes อื่นๆ

- ใน File Object Definition ของ Kubernetes มี 3 Field หลักที่ต้องมีเสมอ:
  1. apiVersion: ระบุ Version ของ Kubernetes API ที่ Object ใช้ สร้างความเข้ากันได้ (Compatibility) และกำหนดโครงสร้างของ Object
  2. kind: ระบุประเภทของ Object Kubernetes ที่กำลังถูก Define เช่น Pod, Service, Deployment ฯลฯ กำหนดพฤติกรรมและ Function การทำงานของ Object
  3. metadata: ประกอบด้วย Metadata เกี่ยวกับ Object เช่น ชื่อ Namespace, Label และคำอธิบาย (Annotation) ใช้โดย Kubernetes เพื่อระบุและจัดการ Object ภายใน Cluster  

  Field เหล่านี้มีความสำคัญอย่างยิ่งเพื่อให้ Kubernetes สามารถแปลและประมวลผล Object ได้อย่างถูกต้อง
