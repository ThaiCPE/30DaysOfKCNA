- บริการ Kubernetes ที่ไม่มีที่อยู่ IP ของ Cluster เรียกว่า Headless Service  
Headless Service สร้างขึ้นโดยการตั้งค่า Field clusterIP เป็น None

- CI/CD ย่อมาจาก Continuous Integration / Continuous Deployment

- Kubernetes Secrets ใช้เก็บข้อมูลที่ Sensitive เช่น รหัสผ่าน, Token OAuth และ Key SSH  
ข้อมูลที่เก็บใน Secrets จะถูกเข้ารหัสแบบ base64 โดย Default อย่างไรก็ตาม สิ่งสำคัญที่ควรทราบคือการเข้ารหัสแบบ base64 ไม่ใช่การเข้ารหัสลับ—แต่เป็นเพียงรูปแบบการเข้ารหัสที่สามารถถอดกลับได้  
แม้ว่าการเข้ารหัสแบบ base64 จะให้การอำพราง (Obfuscation) ข้อมูลในระดับพื้นฐาน แต่ไม่ได้ให้ความปลอดภัยที่แข็งแกร่งต่อการเข้าถึงโดยไม่ได้รับอนุญาต

- Kube-proxy คือ Network Proxy ที่ทำงานบนทุก Node ใน Cluster Kubernetes หน้าที่หลักของมันคือการ Maintain Network Rule บนแต่ละ Node เพื่อ Forward Traffic ไปยัง Pod หรือบริการที่เหมาะสมตามที่อยู่ IP และหมายเลข Port

- API ที่มีความเสถียร (Stable) ใน Kubernetes ควรได้รับการ Support อย่างน้อยหนึ่งปีหลังจากถูกประกาศเลิกใช้ นโยบายนี้ช่วยให้มั่นใจว่าผู้ใช้มีเวลาเพียงพอในการย้ายไปใช้ Version ใหม่ของ API ก่อนที่องค์ประกอบที่ถูกประกาศเลิกใช้จะถูกลบออกในรุ่นที่จะ Release ในอนาคต  
https://kubernetes.io/docs/reference/using-api/deprecation-policy/#:~:text=Rule%20%237

- K3s คือ Kubernetes Distribution ที่มีความสอดคล้องอย่างสมบูรณ์ซึ่งได้รับการปรับให้เหมาะสมกับ Environment ที่มี Resource จำกัด ทำให้เหมาะอย่างยิ่งสำหรับกรณีการใช้งาน IoT และ Edge Computing มันถูกออกแบบให้มีน้ำหนักเบา ติดตั้งง่าย และใช้งานง่าย
