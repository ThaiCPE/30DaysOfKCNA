- ในขณะที่ Consensus Protocol คือกลไกหลักที่ป้องกัน Split-brain ในระบบ Distribute (เช่น Raft ใน etcd, หรือ Zookeeper ใน Kafka) ทำหน้าที่: ให้มี leader แค่ตัวเดียว และทำให้ระบบยืนยันว่า ต้องมี "เสียงข้างมาก (Quorum)" ก่อนจะเขียนข้อมูล  
StatefulSet ช่วยให้มี Pod ที่มี Identity ซ้ำกันได้แค่ตัวเดียวเท่านั้น ("At Most One") นี่แหละที่ช่วยลดโอกาสเกิด Split-brain ในระบบ Distribute ที่ใช้ Quorum ได้ดี
