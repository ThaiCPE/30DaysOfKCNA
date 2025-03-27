- ในสถาปัตยกรรมของ Service Mesh, Service Proxy (เช่น Envoy, Linkerd Proxy หรือ Istio Sidecar) จะถูกนำไปใช้คู่กับ Instance ของแต่ละบริการ เพื่อจัดการการสื่อสารระหว่างบริการต่างๆ  
Control Plane ประกอบด้วย Component ต่างๆ ที่มีหน้าที่รับผิดชอบในการกำหนดค่า, จัดการ, และตรวจสอบพฤติกรรมของ Service Proxy ซึ่งรวมถึงคุณสมบัติต่างๆ เช่น:
  - Traffic Routing
  - Load Balancing
  - การเข้ารหัส
  - การพิสูจน์ตัวตน (Authentication)
  - Observability   
องค์ประกอบเหล่านี้ทำงานร่วมกันเพื่อ Enable ความสามารถขั้นสูงใน Traffic Management, ความปลอดภัย, และ Observability ใน Microservices Environment แบบ Distribute
