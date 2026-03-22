# ml-clustering-credit-card
This is part of the course CS372.

# Clustering - Credit Card

## เกี่ยวกับโปรเจกต์ (About This Project)
โปรเจกต์นี้เป็นการนำโมเดล Machine Learning อัลกอริทึม **Clustering** (Unsupervised Learning) มาใช้สำหรับจัดกลุ่มลูกค้าตามพฤติกรรมการใช้งานบัตรเครดิต เพื่อค้นหา Customer Segments ที่ซ่อนอยู่ในข้อมูล โดยจัดทำขึ้นเพื่อการศึกษาและการส่งการบ้านในรายวิชา **CS372** เท่านั้น

โปรเจกต์นี้อ้างอิงและถูกพัฒนาเพิ่มเติม (Amplify) จากแนวทางไฟล์ตัวอย่าง:
- [Clustering Feature Combination Test : Mall Customers Data Set](https://colab.research.google.com/drive/1iZelmhkzmOGlp7LxO5_ovTCdnpqQigUX?usp=sharing)
- [Clustering Feature Combination Test : Movie Preference Dataset](https://colab.research.google.com/drive/15M-0rPuUQ4TKwbyzxoDdkl6owCWNmcRL?usp=sharing)
- [k-means vs DBSCAN vs OPTICS](https://colab.research.google.com/drive/1gsG98tNUbAHiFPjfV7JUtCuIM4CUiObW?usp=sharing)

**อ้างอิงชุดข้อมูล (Dataset):** [Credit Card Dataset for Clustering (Kaggle)](https://www.kaggle.com/arjunbhasin2013/ccdata)

---

## ขั้นตอนการทำงาน (Workflow)
1. **Data Preprocessing:** ทำความสะอาดข้อมูล จัดการค่าว่าง (Missing Values) เช่น คอลัมน์ `CREDIT_LIMIT` และปรับสเกลข้อมูลด้วย `StandardScaler`
2. **Feature Selection:** ทำการทดสอบจับคู่ตัวแปร (Feature Combination) เพื่อหาตัวแปรที่ดีที่สุดในการจัดกลุ่ม โดยประเมินจากค่า *Silhouette Score* และ *Davies-Bouldin Index*
3. **Clustering Benchmark:** นำตัวแปรที่ดีที่สุด (เช่น `PURCHASES` และ `PAYMENTS`) มาเปรียบเทียบประสิทธิภาพระหว่าง 3 อัลกอริทึม ได้แก่:
   - **K-Means**
   - **DBSCAN**
   - **OPTICS**

---

## สรุปผลการวิเคราะห์ (Key Insights)
จากการวิเคราะห์พฤติกรรมการใช้จ่าย (`PURCHASES`) และการชำระเงินคืน (`PAYMENTS`) โมเดลสามารถแบ่งกลุ่มลูกค้าหลักๆ ออกได้เป็น 2 กลุ่มอย่างชัดเจน:
* **Cluster 0 (กลุ่มลูกค้าทั่วไป):** กลุ่มลูกค้าส่วนใหญ่ของฐานข้อมูล มียอดการรูดซื้อสินค้าทั่วไปในชีวิตประจำวัน (Low Spenders) และมีการชำระยอดบัตรคืนในระดับที่สอดคล้องกับการใช้จ่าย
* **Cluster 1 (กลุ่มลูกค้าระดับสูง / VVIP):** กลุ่มลูกค้าส่วนน้อยแต่มียอดการใช้จ่ายสูงมาก (High Spenders) และมีกำลังซื้อ/สภาพคล่องทางการเงินสูงมาก สามารถชำระเงินคืนในยอดที่สูงลิ่วสอดคล้องกับยอดที่รูดไป เป็นกลุ่มที่สร้างมูลค่า (Value) ให้กับธุรกิจได้อย่างมหาศาล

---

## รายละเอียดไฟล์ใน Repository
- `CC GENERAL.csv` / `cc_general_mini.csv` : ชุดข้อมูลดิบที่ใช้ในการวิเคราะห์
- `clustering_credit_card_6609520116.ipynb` : ไฟล์ Source Code หลักสำหรับการเตรียมข้อมูลและทำ Feature Combination
- `clustering_benchmark_credit_card_6609520116.ipynb` : ไฟล์ Source Code สำหรับการเปรียบเทียบโมเดล (K-Means, DBSCAN, OPTICS) และแสดงผลกราฟ

---

**ผู้จัดทำ:** กมลพันธ์ กันธายอด (6609520116)
