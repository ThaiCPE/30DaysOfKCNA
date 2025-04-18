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

- การออกแบบกลยุทธ์สำหรับการกู้คืนจากภัยพิบัติและความทนทานต่อความผิดพลาด: เช่นเดียวกับที่วิศวกรซ่อมบำรุงสร้างแผนฉุกเฉินสำหรับการชำรุดเสียหายหรืออุบัติเหตุ วิศวกรความน่าเชื่อถือระบบ (SRE) วางแผนสำหรับความล้มเหลวหรือการหยุดชะงักของระบบ เพื่อให้มั่นใจว่าบริการสามารถกู้คืนและทำงานต่อไปได้อย่างรวดเร็ว  
การวิเคราะห์ Metric ประสิทธิภาพของระบบ: เช่นเดียวกับการตรวจสอบบันทึกการซ่อมบำรุงและข้อมูลประสิทธิภาพสำหรับรถบรรทุกแต่ละคัน SRE วิเคราะห์ Metric จากระบบตรวจสอบของ App เพื่อระบุพื้นที่ที่สามารถปรับปรุงและเพิ่มประสิทธิภาพ  
โดยการพิจารณาความรับผิดชอบของ SRE ในบริบทของการจัดการรถบรรทุกขนส่ง เราสามารถเห็นความเชื่อมโยงที่แสดงให้เห็นถึงการมุ่งเน้นในความน่าเชื่อถือ ประสิทธิภาพ และการบำรุงรักษาเชิงป้องกันที่มีอยู่ในบทบาทนี้

- Kubernetes เริ่มต้นมาพร้อมกับ Namespace พื้นฐาน 4 รายการนี้:  
default - Namespace มาตรฐานสำหรับ Object ที่ไม่ได้ระบุ Namespace  
kube-system - สำหรับ Component ของระบบ Kubernetes เอง  
kube-public - สามารถเข้าถึงได้โดยทุกผู้ใช้ รวมถึงผู้ใช้ที่ไม่ได้รับการพิสูจน์ตัวตน มักใช้สำหรับ Resource ที่ต้องการให้มองเห็นได้ทั่วทั้ง Cluster  
kube-node-lease - ใช้สำหรับเก็บ Object "lease" ที่เกี่ยวข้องกับแต่ละ Node ช่วยปรับปรุงประสิทธิภาพของ Node Heartbeat

- ภายใน Kubernetes "Probe" หมายถึงกลไก Diagnostic ที่ใช้โดย Kubelet เพื่อตรวจสอบสุขภาพของ Container ที่ทำงานภายใน Pod, Probe ได้รับการกำหนดค่าภายใน PodSpec ของ Kubernetes Pod และใช้เพื่อกำหนดว่า Container ภายใน pod มีสุขภาพดีและพร้อมให้บริการ Traffic หรือไม่ มี Probe สามประเภท:
  - Liveness Probe: กำหนดว่า Container ยังคงทำงานอยู่และมีสุขภาพดีหรือไม่ หากล้มเหลว Kubernetes จะ Restart Container
  - Readiness Probe: กำหนดว่า Container พร้อมให้บริการ Traffic หรือไม่ หากล้มเหลว Pod จะถูกลบออกจากตัว Load Balancer และไม่มี Traffic ที่ถูกส่งไปยัง Pod นั้น
  - Startup Probe: คล้ายกับ Liveness Probe แต่ทำงานเฉพาะในช่วงเริ่มต้นของ Container เท่านั้น ช่วยหน่วงเวลา Liveness และ Readiness Probe จนกว่า App ภายใน Container จะ Start
