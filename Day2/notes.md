- runC เป็น Native Runtime ที่สอดคล้องกับ Open Container Initiative (OCI)
- https://medium.com/@sathabhronchangchuea/kubernetest-ความเเตกต่างระว่าง-deployments-statefulsets-daemonsets-1ea91453e61e
- CronJob Controller: CronJob Controller รับผิดชอบในการจัดการ CronJobs โดยจะจัดตารางการทำงานของ Jobs ตามกำหนดการของ CronJob (เช่น ทุกชั่วโมง)
การสร้าง Job: เมื่อถึงเวลาที่ CronJob ต้องทำงาน ตัวควบคุม CronJob จะสร้างทรัพยากร Job ซึ่ง Job นี้เป็นตัวแทนของงานที่ต้องดำเนินการ
ตัวควบคุม Job: เมื่อ Job ถูกสร้างขึ้นแล้ว ตัวควบคุม Job จะรับผิดชอบในการจัดการ Job นี้ โดยทำให้มั่นใจว่า Pods ที่ระบุโดย Job ได้ถูกสร้างและทำงานสำเร็จ
การทำงานของ Pod: ตัวควบคุม Job สร้าง Pod หนึ่งตัวหรือมากกว่าตามข้อกำหนดของ Job โดย Pods เหล่านี้จะดำเนินการตามงานที่กำหนดโดย Job และตัวควบคุม Job จะรอจนกว่า Pod จะทำงานเสร็จสมบูรณ์
