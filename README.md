<div dir="rtl">

# Aqua AI 💧

**نظام ذكي للكشف المبكر عن تسرب المياه، يعمل بالطاقة الشمسية وتقنية إنترنت الأشياء على الحافة (Edge-IoT)**

مشروع متدربي قسم الدعم الفني (حاسب آلي) — الكلية التقنية بظهران الجنوب، المؤسسة العامة للتدريب التقني والمهني.

🔗 **المعاينة ثلاثية الأبعاد (Demo):** https://alwadai1.github.io/aqua-ai/
🔗 **صفحة المشروع على منصة رواد التقنية:** https://www.ruaad.tech/projects/176

<img src="assets/qr-ruaad.png" width="140" alt="QR — صفحة المشروع على منصة رواد التقنية">

## وصف المشروع
Aqua AI نظام منخفض التكلفة يراقب خط المياه لحظياً ويكتشف التسرب مبكراً. يقارن قراءات حساسَي تدفق عند مدخل الخط ومخرجه، ويحلل الفرق بمعالج ESP32 في موقع الخط نفسه، ثم ينبّه ويوقف المضخة تلقائياً عند ارتفاع الخطر، ويعمل بالكامل بالطاقة الشمسية.

## المشكلة
يضيع جزء من المياه المعالجة بسبب التسربات وأعطال الأنابيب، وكثيراً ما لا تُكتشف إلا متأخرة بعد فحص يدوي. وفي البيئات الجافة كل قطرة مهمة، كما أن ضخ ماء مهدر يستهلك طاقة بلا فائدة.

## الحل المقترح
إنذار مبكر عند نقطة الفقد نفسها: يحسب النظام نسبة التسرب من فرق التدفق خلال فترة زمنية، ويعرض الحالة بثلاثة ألوان (أخضر، أصفر، أحمر)، ويفصل المضخة عبر الريليه عند الخطر، دون حاجة لشبكة الكهرباء.

## كيف يعمل
1. **القياس:** حساس التدفق الأول يقيس الماء الداخل، والثاني يقيس الماء الخارج.
2. **المقارنة:** ESP32 يقارن القراءتين على نافذة زمنية لتجنب الإنذار الكاذب.
3. **التقدير:** يحسب نسبة التسرب ومؤشر الخطر.
4. **الاستجابة:** تنبيه على الشاشة بالألوان، وإيقاف المضخة تلقائياً عند الخطر.

## المكونات
| المكون | المواصفات |
|---|---|
| وحدة التحكم | ESP32 |
| حساسا تدفق | YF-S201 (1–30 L/min) |
| حساس ضغط (اختياري) | MPX5050 (0–50 kPa) |
| مضخة مياه | 12V DC عبر ريليه 5V |
| الطاقة | لوح شمسي 20W + منظم شحن + بطارية 12V 7Ah |
| تغذية المنطق | محوّل 12V → 5V + فيوز |
| العرض | شاشة LCD 16×2 I2C |
| البرمجة | Arduino IDE (C++) |

**التكلفة الفعلية للمكونات:** 1,347 ريال.

## حالة المشروع
نموذج أولي قيد الاختبار. نتائج الأداء (دقة الكشف، زمن الاستجابة، كمية المياه الموفرة) تُضاف بعد اكتمال الاختبارات العملية.

## الفريق
**المشرف:** م. عبدالله محمد الوادعي — التوجيه الفني والمراجعة والتحقق من النتائج.

| العضو | الدور | المهام |
|---|---|---|
| حسين محمد سعيد القحطاني | **قائد الفريق** | تنسيق العمل والجدول الزمني، متابعة المهام والمشتريات، تجميع التوثيق، تقديم المشروع أمام اللجنة |
| وسام محمد سعيد القحطاني | البرمجة والذكاء الاصطناعي | برمجة ESP32، قراءة الحساسات، خوارزمية مقارنة التدفق ومؤشر التسرب، شاشة LCD والتنبيهات |
| عبدالله محمد سعيد القحطاني | الإلكترونيات والطاقة | منظومة الطاقة الشمسية والبطارية، توصيل الريليه والمضخة ومحوّل الجهد، الفيوز والسلامة الكهربائية، المخطط الكهربائي |
| محمد جابر قطمان القحطاني | التجميع الهيدروليكي والاختبار | تركيب الخزان والأنابيب والحساسات على القاعدة، معايرة حساسات التدفق، تجارب التسرب وتسجيل النتائج |

## محتويات المستودع
- `index.html` — النموذج ثلاثي الأبعاد التفاعلي (يعمل من GitHub Pages)
- `assets/` — الإنفوجرافيك ورمز QR
- `docs/` — العرض التقديمي للمشروع

</div>

---

## English summary

**Aqua AI** is a low-cost, solar-powered Edge-IoT system that detects water leaks early. An ESP32 compares inlet and outlet readings from two YF-S201 flow sensors over a time window, estimates a leakage percentage, shows a green/yellow/red status on an I2C LCD, and cuts the 12V pump through a relay when risk is high. Power comes from a 20W solar panel, a charge controller and a 12V 7Ah battery.

- **3D demo:** https://alwadai1.github.io/aqua-ai/
- **Project page:** https://www.ruaad.tech/projects/176
- **Status:** prototype under test; measured results will be added after lab testing.
- **Team** — Technical College, Dhahran Al-Janoub (TVTC):
  - Hussein Mohammed Saeed Al-Qahtani — **Team leader** (coordination, documentation, presentation)
  - Wesam Mohammed Saeed Al-Qahtani — Programming & AI (ESP32 firmware, leak-detection logic)
  - Abdullah Mohammed Saeed Al-Qahtani — Electronics & power (solar system, relay, wiring, safety)
  - Mohammed Jaber Qatman Al-Qahtani — Hydraulics & testing (assembly, sensor calibration, leak tests)
  - Supervisor: Eng. Abdullah Mohammed Alwadai
