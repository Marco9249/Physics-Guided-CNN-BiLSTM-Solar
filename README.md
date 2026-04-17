# 🌞 Physics-Guided Neural Networks for Solar Irradiance Forecasting

## 📖 نظرة عامة
هذا المشروع مخصص للورقة العلمية "Outperforming Self-Attention Mechanisms in Solar Irradiance Forecasting via Physics-Guided Neural Networks".
الكود المرفق هنا يعتمد على بيئة العمل (MATLAB) ويوفر تطبيق عملي واضح للنتائج المذكورة في الورقة.

هذا المشروع يعتمد على معمارية معينة حيث تتمركز طبقة الانتباه (Attention Layer) مباشرة بعد طبقة BiLSTM. كما يتم الاعتماد بشكل أساسي على البيانات المستخرجة من نظام متغيرات NASA POWER، مع تطبيق نافذة بيانات منزلقة بمقدار 3 خطوات زمنية (Sliding Window of 3 Time Steps) لضمان المعالجة الزمنية المثلى.

## 📐 معمارية النموذج
النماذج مبنية كالتالي:
- مدخلات فيزيائية مهندسة بعناية.
- شبكات طي أحادية البعد (1D-CNN) لاستخراج الخصائص.
- شبكة الذاكرة طويلة قصيرة المدى ثنائية الاتجاه (BiLSTM) لاستخلاص التبعيات الزمنية.
- طبقة الانتباه التي تأتي بعد طبقة BiLSTM لمعالجة البيانات بشكل أفضل.

## 🛠 المتطلبات
- بيئة عمل MATLAB.
- أداة التعلم العميق Deep Learning Toolbox.
- ملفات البيانات الخاصة ببدائل القياس.

## 🔖 الاقتباس المرجعي (APA 7th Edition)
Abdullah, M. E. B. (2026). *Outperforming Self-Attention Mechanisms in Solar Irradiance Forecasting via Physics-Guided Neural Networks*. arXiv. https://arxiv.org/abs/2604.13455

---
© محفوظة رسميًا للباحث المهندس / م. محمد عزالدين بابكر عبدالله - 2026
