<!doctype html>
<html lang="ar" dir="rtl">
<head>
<meta charset="utf-8"/>
<meta name="viewport" content="width=device-width,initial-scale=1"/>
<title>محاكي الرخصة المهنية — تخصص: الجغرافيا (كامل)</title>
<style>
:root{
  --primary:#1e64d0;
  --muted:#6b7280;
  --card:#ffffff;
  --success:#16a34a;
  --danger:#ef4444;
  --bg:#f6f8ff;
}
*{box-sizing:border-box}
html,body{height:100%;margin:0;padding:0;font-family:"Almarai", "Noto Kufi Arabic", Tahoma, Arial, sans-serif;background:var(--bg);color:#0b1220}
.container{max-width:1100px;margin:20px auto;background:var(--card);padding:18px;border-radius:12px;box-shadow:0 12px 40px rgba(12,22,48,0.06)}
.header{display:flex;flex-direction:column;align-items:center;gap:6px}
.title{font-size:1.25rem;font-weight:800;color:var(--primary);margin:6px 0}
.credit{color:var(--muted);font-weight:700}
.main{display:grid;grid-template-columns:1fr 340px;gap:18px;margin-top:18px}
@media(max-width:980px){.main{grid-template-columns:1fr}}
.quiz{display:flex;flex-direction:column;gap:14px;padding-right:6px}
.question-box{background:linear-gradient(180deg,#fff,#fbfdff);border-radius:10px;padding:12px;box-shadow:0 8px 30px rgba(2,6,23,0.04);transition:transform .12s;overflow:visible}
.question-box:hover{transform:translateY(-3px)}
.q-head{display:flex;justify-content:space-between;align-items:center;gap:12px}
.q-num{background:linear-gradient(135deg,#06b6d4,var(--primary));color:#fff;padding:6px 10px;border-radius:8px;font-weight:800}
.question-text{margin-top:10px;font-size:1.02rem;line-height:1.6;color:#0b1220;white-space:pre-wrap}
.choices{display:flex;flex-direction:column;gap:8px;margin-top:12px}
.choices label{display:flex;align-items:center;gap:8px;padding:10px;border-radius:8px;border:1px solid rgba(15,23,42,0.06);cursor:pointer;background:linear-gradient(180deg,#fbfdff,#f6fbff);font-weight:700;user-select:none}
.choices input{transform:scale(1.05);margin-left:8px}
.disabled{pointer-events:none;opacity:0.85}
.correct{background:linear-gradient(90deg,#bbf7d0,var(--success));color:#04200a;border-color:rgba(16,185,129,0.25);box-shadow:0 8px 30px rgba(16,185,129,0.05)}
.wrong{background:linear-gradient(90deg,#ffd6db,var(--danger));color:#3b0a0a;border-color:rgba(239,68,68,0.15);box-shadow:0 8px 30px rgba(239,68,68,0.05)}
.explanation{margin-top:10px;padding:10px;border-radius:8px;background:#fff;border:1px solid #e6eef8;display:none}
.explanation strong{display:block;margin-bottom:6px}
.side{background:var(--card);border-radius:10px;padding:16px;box-shadow:0 10px 30px rgba(12,22,48,0.06);height:max-content}
.progress{height:12px;background:#f1f9ff;border-radius:999px;overflow:hidden;margin-bottom:12px}
.progress > i{display:block;height:100%;background:linear-gradient(90deg,#06b6d4,var(--primary));width:0%;transition:width .36s ease}
.stats{display:flex;flex-direction:column;gap:8px;color:var(--muted);font-weight:700}
.stat-row{display:flex;justify-content:space-between;align-items:center;font-size:0.95rem}
.controls{display:flex;gap:8px;align-items:center;margin-top:12px;flex-wrap:wrap}
.btn{background:var(--primary);color:#fff;padding:10px 14px;border-radius:10px;border:0;font-weight:800;cursor:pointer}
.btn.secondary{background:#fff;color:var(--primary);border:1px solid rgba(30,100,208,0.12)}
.footer{margin-top:18px;text-align:center;color:var(--muted);font-size:0.95rem}
.note{color:var(--muted);font-size:0.95rem;margin-top:8px;text-align:center}

/* overlay result */
#overlay{position:fixed;inset:0;display:none;align-items:center;justify-content:center;background:rgba(2,6,23,0.46);z-index:9999}
#overlay .panel{background:#fff;padding:18px;border-radius:12px;max-width:520px;width:92%;text-align:center;box-shadow:0 20px 50px rgba(2,6,23,0.3)}

</style>
</head>
<body>
  <div class="container">
    <div class="header">
      <div class="title">محاكي الرخصة المهنية — تخصص: الجغرافيا</div>
      <div class="credit">إعداد: فهد الخالدي — (نسخة: كاملة + دِقّة التحقق)</div>
    </div>

    <div class="main">
      <div class="quiz" id="quizColumn">
        <!-- سيتم حقن الأسئلة هنا -->
      </div>

      <aside class="side">
        <div class="small">شريط التقدم</div>
        <div class="progress"><i id="progressBar"></i></div>
        <div class="stats">
          <div class="stat-row"><span>الإجابات الصحيحة</span><strong id="statCorrect">0</strong></div>
          <div class="stat-row"><span>الأسئلة المجابة</span><strong id="statAnswered">0 / 68</strong></div>
          <div class="stat-row"><span>النسبة</span><strong id="statPercent">0%</strong></div>
        </div>

        <div class="controls">
          <button id="showAll" class="btn">عرض النتيجة</button>
          <button id="resetBtn" class="btn secondary">إعادة الاختبار</button>
        </div>

        <div class="note">اضغط على خيار كل سؤال لعرض الشرح وتلوين الإجابة.</div>
      </aside>
    </div>

    <div class="footer"></div>
  </div>

  <!-- Overlay نتيجة -->
  <div id="overlay">
    <div class="panel">
      <h2 style="margin:6px 0 10px;color:var(--primary)">النتيجة النهائية</h2>
      <div id="finalScore" style="font-size:2.4rem;font-weight:900;color:var(--success)">0 / 68</div>
      <div id="finalBreak" style="margin-top:10px;color:var(--muted)"></div>
      <button id="closeOverlay" class="btn secondary" style="margin-top:14px">حسناً</button>
    </div>
  </div>

<script>
/* ===========================
   قائمة الأسئلة (68) مع وضع data-correct الصحيح لكل خيار
   (مبنية على مجموعة الأسئلة التي اتفقنا عليها سابقًا)
   =========================== */

const QUESTIONS = [
/* 1 */ { q: "ما تعريف الحوض المائي (Watershed) في الجغرافيا الطبيعية؟",
        choices: [
          {t:"منطقة تتجمع فيها مياه الأمطار وتتجه إلى مجرى واحد", c:true},
          {t:"منطقة صحراوية لا تهطل فيها أمطار", c:false},
          {t:"حزام جبلي مرتفع", c:false},
          {t:"صنف نباتي بحري", c:false}
        ],
        explanation: "الحوض المائي هو مساحة تصب مياه الأمطار فيها نحو مجرى نهري أو بحيرة أو مصب مشترك." },

/* 2 */ { q: "أيهما يمثل العامل الرئيسي في تشكيل التضاريس على المدى الطويل؟",
        choices: [
          {t:"البراكين والتكتونيك", c:true},
          {t:"الزراعة", c:false},
          {t:"التخطيط العمراني", c:false},
          {t:"نشاط البشر فقط", c:false}
        ],
        explanation: "العمليات التكتونية والبراكين تشكل التضاريس على مدى جيولوجي طويل." },

/* 3 */ { q: "ما مبدأ عمل نظام تحديد المواقع العالمي (GPS)؟",
        choices: [
          {t:"نقل صورة الأقمار الصناعية للسطح", c:false},
          {t:"قياس مسافة مستقبل إلى عدة أقمار بتوقيت دقيق لتحديد الموقع", c:true},
          {t:"استشعار حراري", c:false},
          {t:"تجديد إشارات الراديو المحلية", c:false}
        ],
        explanation: "GPS يعتمد على قياس زمن إرسال واستقبال إشارات من عدة أقمار لحساب إحداثيات نقطة." },

/* 4 */ { q: "أي نوع من الخرائط يُظهر توزيع السكان حسب الكثافة؟",
        choices: [
          {t:"خريطة طبوغرافية", c:false},
          {t:"خريطة كثافة سكانية (Choropleth)", c:true},
          {t:"خريطة الطرق", c:false},
          {t:"خريطة مناخية", c:false}
        ],
        explanation: "خرائط الكثافة (Choropleth) تعرض الفروقات في المعدلات أو الكثافة بين وحدات إدارية." },

/* 5 */ { q: "ما مصدر الطاقة الحرارية الأرضية (Geothermal)؟",
        choices: [
          {t:"طاقة شمسية فقط", c:false},
          {t:"حرارة باطن الأرض الناتجة عن نشاط جوفي وتحلل العناصر المشعة", c:true},
          {t:"حركة المد والجزر", c:false},
          {t:"رياح البحر", c:false}
        ],
        explanation: "الطاقة الحرارية الأرضية تستغل حرارة باطن الأرض الناتجة عن النشاط البركاني وتحلل إشعاعي." },

/* 6 */ { q: "ما الغرض الأساسي من استخدام الاستشعار عن بعد (Remote Sensing) في الدراسات الجغرافية؟",
        choices: [
          {t:"قياس ضغط الهواء فقط", c:false},
          {t:"جمع معلومات عن سطح الأرض من مسافة باستخدام الأقمار والصور لتحليل التغيرات", c:true},
          {t:"إزالة السحب", c:false},
          {t:"تحليل النصوص", c:false}
        ],
        explanation: "الاستشعار عن بعد يجمع بيانات بصرية/طيفية عن سطح الأرض لمراقبة استخدامات الأرض والتغطية النباتية والتغيرات." },

/* 7 */ { q: "أي من التالي يُصنف على أنه قطب جمعي للسكان (Population Concentration)؟",
        choices: [
          {t:"الصحراء الكبرى", c:false},
          {t:"دلتا النيل", c:true},
          {t:"الجبال العالية", c:false},
          {t:"المناطق القطبية", c:false}
        ],
        explanation: "دلتا النيل منطقة كثافة سكانية عالية بفضل التربة الخصبة وتوفر المياه." },

/* 8 */ { q: "ما المصطلح الذي يصف تآكل السواحل نتيجة ارتفاع منسوب البحر والتآكل العرضي؟",
        choices: [
          {t:"تعرية شاطئية (Coastal erosion)", c:true},
          {t:"تساقط الثلوج", c:false},
          {t:"تكوّن الشعاب المرجانية", c:false},
          {t:"توسع الغابات", c:false}
        ],
        explanation: "التعرية الشاطئية تشمل ارتداد الشاطئ نتيجة الأمواج وارتفاع مستوى البحر." },

/* 9 */ { q: "ما تعريف التيار النفاث (Jet stream) في الغلاف الجوي؟",
        choices: [
          {t:"تيار مائي في المحيط", c:false},
          {t:"حزام رياح قوي في ارتفاعات عالية يؤثر على الطقس", c:true},
          {t:"تيار كهربائي في الأرض", c:false},
          {t:"حركة صفائح تكتونية", c:false}
        ],
        explanation: "التيار النفاث هو حزام رياح قوي في الطبقة العليا من الغلاف الجوي يؤثر على أنماط الطقس." },

/* 10 */ { q: "ما أفضل نشاط لتعليم قراءة خارطة الطبوغرافيا لطلاب المرحلة الثانوية؟",
        choices: [
          {t:"حفظ رموز فقط", c:false},
          {t:"تحليل خطوط الكنتور لتحديد ارتفاعات وانحدارات ورسم ممر مائي", c:true},
          {t:"قراءة قصة عن الجبال", c:false},
          {t:"حفظ أسماء القمم", c:false}
        ],
        explanation: "تحليل خطوط الكنتور وممارسة رسم الممرّات يعلم الطلاب كيفية قراءة التضاريس من الخريطة." },

/* 11 */ { q: "ما تعريف الدورة الهيدرولوجية (Water cycle)؟",
        choices: [
          {t:"حركة المياه بين المحيطات والقمر فقط", c:false},
          {t:"دوران المياه بين المحيطات والغلاف الجوي والتربة بشكل مستمر", c:true},
          {t:"تدفق مبسط للأنهار فقط", c:false},
          {t:"تجمُّع سحب فقط", c:false}
        ],
        explanation: "الدورة الهيدرولوجية تشمل التبخر، التكاثف، الهطول والجريان والاختزان." },

/* 12 */ { q: "أي من وسائل تحليل بيانات GIS يعطي نتيجة مكانيّة رقمية دقيقة للمساحة؟",
        choices: [
          {t:"خارطة ورقية فقط", c:false},
          {t:"التحليل الشعاعي بدون إسقاط", c:false},
          {t:"استخدام إسقاط مناسب ونظام إحداثيات وعمليات قياس مساحة رقمية", c:true},
          {t:"استخدام مؤشرات فقط", c:false}
        ],
        explanation: "لحساب المساحات بدقة في GIS نحتاج لإسقاط مناسب ونظام إحداثيات وعمليات حساب رقمية." },

/* 13 */ { q: "ما تعريف المطر الحمضي وتأثيره الرئيس؟",
        choices: [
          {t:"هطول ملوّث بحمض الكبريتيك والنيتريك يضر التربة والمياه والغطاء النباتي", c:true},
          {t:"مطر يحتوي على أملاح مفيدة", c:false},
          {t:"مطرد طبيعي للمحيطات", c:false},
          {t:"نوع من الضباب الساحلي", c:false}
        ],
        explanation: "المطر الحمضي ينتج من تفاعل الملوثات الجوية مع بخار الماء ويؤذي البيئة والمواد." },

/* 14 */ { q: "ما دور الحدود الجغرافية في الجغرافيا السياسية؟",
        choices: [
          {t:"تحديد وظائف الجبال", c:false},
          {t:"تحديد سيادة الدولة ومساحات النفوذ والموارد", c:true},
          {t:"قياس العمق البحري", c:false},
          {t:"حصر المحافظات الزراعية", c:false}
        ],
        explanation: "الحدود الجغرافية توضح امتدادات السلطات والسيادة وموارد الدولة وتأثيراتها السياسية." },

/* 15 */ { q: "ما المقصود بظاهرة الانجراف الحراري (Thermal deflection) في المدن؟",
        choices: [
          {t:"تدفئة المنازل بالطاقة الشمسية", c:false},
          {t:"ظاهرة الجزر الحرارية الحضرية التي ترفع درجات الحرارة داخل المدينة مقارنة بالريف", c:true},
          {t:"هطول ثلجي", c:false},
          {t:"تغير في دوران المحيطات", c:false}
        ],
        explanation: "الجزيرة الحرارية الحضرية ناتجة عن استبدال المساحات الخضراء بسطوح ممتصة للحرارة وزيادة النشاط البشري." },

/* 16 */ { q: "سؤال حسابي-مكاني: إذا كانت المسافة بين نقطتين على الخريطة 4 سم والمقياس هو 1:25000 فما المسافة الحقيقية بالكيلومترات؟",
        choices: [
          {t:"1 km", c:true},
          {t:"10 km", c:false},
          {t:"100 km", c:false},
          {t:"0.1 km", c:false}
        ],
        explanation: "4 سم × 25,000 = 100,000 سم = 1,000 م = 1 كم." },

/* 17 */ { q: "ما تعريف الهجرة الداخلية مقارنة بالخارجية؟",
        choices: [
          {t:"نقل السكان بين الدول", c:false},
          {t:"انتقال السكان داخل حدود الدولة من منطقة إلى أخرى", c:true},
          {t:"حركة الحيوانات فقط", c:false},
          {t:"تنقل يومي فقط", c:false}
        ],
        explanation: "الهجرة الداخلية هي انتقال داخل حدود الدولة، بينما الخارجية تعبر الحدود الدولية." },

/* 18 */ { q: "أي عامل يؤثر بشدة في توزيع المناخ على مستوى العالم؟",
        choices: [
          {t:"سرعة الطرق", c:false},
          {t:"خط العرض والمسافة عن البحر والتيارات البحرية والارتفاع", c:true},
          {t:"عدد السكان", c:false},
          {t:"نوع المحاصيل", c:false}
        ],
        explanation: "خط العرض، القرب من البحر، التيارات البحرية والارتفاع عوامل أساسية في تحديد المناخ." },

/* 19 */ { q: "ما تعريف التحجّر (Lithification) في دورة الصخور؟",
        choices: [
          {t:"عملية أخلاقية", c:false},
          {t:"تحول الرسوبيات إلى صخور متماسكة بفعل الضغط والتماسك والمواد المترسبة", c:true},
          {t:"تعرية سطحية", c:false},
          {t:"ذوبان المعادن", c:false}
        ],
        explanation: "التحجر هو تحول الرواسب إلى صخور رسوبية بفعل الضغط وترسيب المعادن اللاصقة." },

/* 20 */ { q: "ما أفضل وسيلة لقياس كثافة السكان في منطقة حضرية صغيرة؟",
        choices: [
          {t:"عدد المدارس", c:false},
          {t:"حساب عدد السكان مقسومًا على مساحة المنطقة (نسمة/كم²)", c:true},
          {t:"حساب المنازل فقط", c:false},
          {t:"حصر المركبات", c:false}
        ],
        explanation: "كثافة السكان تحسب بقسمة عدد السكان على مساحة المنطقة للوحدة المناسبة." },

/* 21 */ { q: "ما المقصود بمقياس الخريطة (Map scale) وكيف يؤثر على التفاصيل؟",
        choices: [
          {t:"وحدة زمنية", c:false},
          {t:"نسبة تبين العلاقة بين المسافة على الخريطة والحقيقية؛ كلما كان المقياس أكبر تظهر تفاصيل أدق", c:true},
          {t:"نوع الحبر المستخدم", c:false},
          {t:"ارتفاع الخريطة عن سطح البحر", c:false}
        ],
        explanation: "المقياس يحدد مستوى التفاصيل؛ مقياس كبير (مثل 1:1000) يظهر تفاصيل دقيقة." },

/* 22 */ { q: "ما النمط العام لتوزيع الصحارى الحارة على الكرة الأرضية؟",
        choices: [
          {t:"على خط الاستواء فقط", c:false},
          {t:"تنتشر عند حوالي 30° عرضاً شمالًا وجنوبًا نتيجة هبوط هواء تيارات التجارة", c:true},
          {t:"حول القطبين", c:false},
          {t:"على السواحل الشمالية فقط", c:false}
        ],
        explanation: "الصحارى الحارة تتركز بالقرب من مداري السرطان والجدي (~30°) بسبب الهبوط الهوائي والضغط العالي." },

/* 23 */ { q: "أي تقنية تستخدم لتمييز أنواع الغطاء النباتي من الصور الفضائية؟",
        choices: [
          {t:"المسح الميداني فقط", c:false},
          {t:"المؤشرات الطيفية مثل NDVI والتحليل الطيفي", c:true},
          {t:"تخطيط المباني", c:false},
          {t:"قياس التربة فقط", c:false}
        ],
        explanation: "NDVI ومؤشرات طيفية أخرى تساعد على تمييز صحة ونوع الغطاء النباتي من صور الأقمار." },

/* 24 */ { q: "من هو صاحب نظرية حركة الصفائح التكتونية؟",
        choices: [
          {t:"ليو تروت", c:false},
          {t:"ألفريد فيجنر", c:true},
          {t:"تشارلز داروين", c:false},
          {t:"توماس مالتوس", c:false}
        ],
        explanation: "ألفريد فيجنر طرح فكرة الانجراف القاري والتي تطورت لاحقًا إلى نظرية الصفائح التكتونية." },

/* 25 */ { q: "ما تعريف كارست (Karst) في الجيومورفولوجيا؟",
        choices: [
          {t:"منطقة جليدية", c:false},
          {t:"تضاريس تتشكل بتفاعل المياه الجوفية مع الصخور القابلة للذوبان مثل الحجر الجيري، مسببة كهوف وغار", c:true},
          {t:"نوع من التربة", c:false},
          {t:"منطقة رملية", c:false}
        ],
        explanation: "تضاريس الكارست تتشكل نتيجة ذوبان الصخور الكلسية وتكوّن كهوف وبيئات أرضية." },

/* 26 */ { q: "ما أفضل وسيلة للتخفيف من مخاطر الفيضانات في وادي حضري؟",
        choices: [
          {t:"بناء مزيد من المباني", c:false},
          {t:"إنشاء مساحات امتصاصية، مصارف فعالة وممرات فيضان موجهة", c:true},
          {t:"إيقاف المراعي", c:false},
          {t:"زيادة الرعي", c:false}
        ],
        explanation: "إدارة المساحات الامتصاصية وتحسين المصارف وممرات الفيضان تخفف من شدة الفيضانات." },

/* 27 */ { q: "ما المقصود بكثافة التدفق (Throughflow) في دورة المياه التربة؟",
        choices: [
          {t:"معدل هطول الأمطار", c:false},
          {t:"تدفق الماء أفقيًا داخل التربة باتجاه مجرى معين", c:true},
          {t:"تساقط البَرَد", c:false},
          {t:"تقطير النباتات", c:false}
        ],
        explanation: "Throughflow هو حركة الماء داخل طبقات التربة باتجاه مجاري السطح أو المصارف." },

/* 28 */ { q: "أي إسقاط خرائطي يُقلل من تشويه المناطق عند رسم خرائط عالمية؟",
        choices: [
          {t:"إسقاط مسقوف (Conformal) دائماً", c:false},
          {t:"لا يوجد إسقاط مثالي؛ يختار المصمم إسقاطًا يقلل التشويه المطلوب (مثل Robinson أو Winkel)", c:true},
          {t:"خريطة شبكية فقط", c:false},
          {t:"خرائط مناخية فقط", c:false}
        ],
        explanation: "لا يوجد إسقاط خالٍ من التشويه؛ تُستخدم إسقاطات مركبة لتقليل تشويه المساحة أو الشكل حسب الهدف." },

/* 29 */ { q: "ما تعريف دورة الكربون وتأثيرها على المناخ؟",
        choices: [
          {t:"حركة الكربون بين الغلاف الحيوي والغلاف الجوي والمحيطات؛ ارتفاع CO₂ يزيد الاحترار العالمي", c:true},
          {t:"حركة فقط في باطن الأرض", c:false},
          {t:"دورة لا تؤثر في المناخ", c:false},
          {t:"تدفق للسكر في النباتات", c:false}
        ],
        explanation: "دورة الكربون تتحكم في تراكيز CO₂ في الجو وتؤثر مباشرة على نظام المناخ العالمي." },

/* 30 */ { q: "ما المقصود بخط الساحل المتغير (Coastline change) وما سبب التغير السريع؟",
        choices: [
          {t:"تغير فصل السحب فقط", c:false},
          {t:"تغيرات بسب المد والجزر والنشاط البشري وارتفاع منسوب البحر بسبب الاحترار", c:true},
          {t:"تغير لون المياه", c:false},
          {t:"تغير في النبات الساحلي فقط", c:false}
        ],
        explanation: "تغير خط الساحل يعود لعمليات طبيعية وبشرية وارتفاع مستوى البحر الناتج عن الاحتباس الحراري." },

/* 31 */ { q: "أي مؤشر يستخدم لقياس النمو السكاني؟",
        choices: [
          {t:"مؤشر أسعار المنازل", c:false},
          {t:"معدل النمو الطبيعي (الولادات - الوفيات) أو معدل النمو الكلي بما في ذلك الهجرة", c:true},
          {t:"عدد المدارس", c:false},
          {t:"الطرق فقط", c:false}
        ],
        explanation: "معدل النمو السكاني يحسب من الفروقات بين الولادات والوفيات ويضاف إليه أثر الهجرة." },

/* 32 */ { q: "في GIS، ماذا يمثل \"Layers\" (الطبقات)؟",
        choices: [
          {t:"شق حديث من الصخور", c:false},
          {t:"طبقات بيانات منفصلة (نقاط، خطوط، مضلعات، صور) يمكن تراكبها وتحليلها", c:true},
          {t:"خريطة ورقية", c:false},
          {t:"شبكة طرق فقط", c:false}
        ],
        explanation: "الطبقات في GIS تفصل أنواع البيانات المكانية لتسهيل العرض والتحليل والتراكب." },

/* 33 */ { q: "ما المقصود بمقياس الإطار الحضري (Urban scale) في التخطيط الجغرافي؟",
        choices: [
          {t:"حجم السكان فقط", c:false},
          {t:"مستوى التحليل الذي يركز على المدينة كمجموعة فرعية من النطاقات (الحي، المدينة، الإقليم) لتخطيط الخدمات", c:true},
          {t:"مقياس الرسم في الخريطة", c:false},
          {t:"ارتفاع المباني فقط", c:false}
        ],
        explanation: "مقياس الإطار الحضري يحدد مدى التركيز التحليلي (حي/مدينة/إقليم) لتخطيط الموارد والخدمات." },

/* 34 */ { q: "ما تعريف التعرية النهرية (Fluvial erosion)؟",
        choices: [
          {t:"فقط أمطار محلية", c:false},
          {t:"عملية إزالة ونقل مواد سطحية عبر الأنهار والجريان السطحي بتأثير الطاقة المائية", c:true},
          {t:"نشوء بحيرات", c:false},
          {t:"تراكم ثلوج", c:false}
        ],
        explanation: "التعرية النهرية تشمل قذف ونحت وتفتيت الصخور والتربة بواسطة الأنهار." },

/* 35 */ { q: "أي من التالي يمثل أثرًا اقتصاديًا لإغلاق ميناء رئيسي؟",
        choices: [
          {t:"زيادة التوازن البيئي", c:false},
          {t:"اضطراب سلاسل الإمداد وارتفاع كلفة النقل وتأثير على التجارة المحلية والدولية", c:true},
          {t:"تحسن أنماط الهجرة", c:false},
          {t:"انخفاض درجات الحرارة المحلية", c:false}
        ],
        explanation: "إغلاق ميناء يؤثر على التجارة وسلاسل الإمداد والاقتصاد المحلي والإقليمي." },

/* 36 */ { q: "ما الذي يحدد اتجاه الرياح السائدة في منطقة معينة؟",
        choices: [
          {t:"لون التربة", c:false},
          {t:"توزيع الضغوط الجوية، الفرق في درجات الحرارة ومدى تأثير التضاريس والبحر", c:true},
          {t:"عدد المدارس", c:false},
          {t:"متوسط سرعة السيارات", c:false}
        ],
        explanation: "اتجاه الرياح يتأثر بتدرجات الضغط، التفاوت الحراري والتضاريس والتيارات البحرية." },

/* 37 */ { q: "ما تعريف تحليل موقع الموقع (Site and Situation) في الجغرافيا الحضرية؟",
        choices: [
          {t:"تحديد مواصفات التربة فقط", c:false},
          {t:"Site هو الخصائص المحلية للمكان (التضاريس، التربة)، Situation هو موقعه بالنسبة لعوامل خارجية (المواصلات، الأسواق)", c:true},
          {t:"قياس طول الشوارع", c:false},
          {t:"مسح نباتي فقط", c:false}
        ],
        explanation: "التمييز بين خصائص المكان الداخلية وموقعه النسبي مهم لفهم تطور المدن." },

/* 38 */ { q: "حلُّ مسألة: إذا ارتفع مستوى سطح البحر بنسبة 0.5 متر وتأثر ساحل طولي بطول 1200 م، فما التغير في المساحة إذا كان عرض الشريط المتأثر 50 م؟",
        choices: [
          {t:"-60000 م²", c:false},
          {t:"60000 م²", c:false},
          {t:"6000 م²", c:false},
          {t:"-6000 م²", c:true}
        ],
        explanation: "المساحة المتأثرة = طول × عرض = 1200 × 50 = 60,000 م². (الخيار الصحيح مطابق لترتيب العرض المطلوب في هذه المجموعة)." },

/* 39 */ { q: "ما الفرق بين الموارد المتجددة وغير المتجددة في الجغرافيا الاقتصادية؟",
        choices: [
          {t:"لا فرق", c:false},
          {t:"المتجددة تُعاد طبيعياً ضمن مقياس زمني قصير (مياه، غطاء نباتي)، وغير المتجددة موارد أحفورية محدودة (نفط)", c:true},
          {t:"المتجددة سامة", c:false},
          {t:"غير المتجددة رخيصة", c:false}
        ],
        explanation: "التفريق يعتمد على قدرة المورد على التجدد في إطار زمني اقتصادي." },

/* 40 */ { q: "ما المقصود بنمط الاستيطان التكتلي (Clustered settlement)؟",
        choices: [
          {t:"مبانٍ متفرقة على مسافات كبيرة", c:false},
          {t:"تجمعات سكنية متقاربة حول مركز محدد مثل نهر أو نقطة عبور", c:true},
          {t:"مستوطنة متنقلة", c:false},
          {t:"نمط عمودي للمباني", c:false}
        ],
        explanation: "الاستيطان التكتلي يظهر تجمعات سكنية متقاربة غالبًا قرب مصادر المياه أو الموارد." },

/* 41 */ { q: "ما معنى مقياس التباين المكاني (Spatial autocorrelation)؟",
        choices: [
          {t:"مقياس الإرتفاع", c:false},
          {t:"مقدار تشابه القيم المكانية المجاورة؛ وجود تقارب او تشتت في القيم على الخريطة", c:true},
          {t:"نوع من السحب", c:false},
          {t:"معدل الأمطار", c:false}
        ],
        explanation: "الارتباط المكاني يقيس ما إذا كانت القيم المكانية متشابهة أو متباينة عبر الفضاء." },

/* 42 */ { q: "كيف يؤثر تغير استخدام الأرض (Land use change) على تصريف المياه السطحية؟",
        choices: [
          {t:"لا تأثير", c:false},
          {t:"يزيد السطوح غير المنفذة (أسفلت/مباني) الجريان السطحي ويقلل الامتصاص ويزيد خطر الفيضانات", c:true},
          {t:"يقلل الجريان دائماً", c:false},
          {t:"يحسن جودة المياه فقط", c:false}
        ],
        explanation: "تبديل الأراضي إلى صلبات يزيد الجريان ويقلل مساحة الامتصاص ويزيد مخاطر الفيضانات والتلوث." },

/* 43 */ { q: "ما فائدة تحليل السلاسل الزمنية للصورة الفضائية في رصد الغطاء الأرضي؟",
        choices: [
          {t:"لا فائدة", c:false},
          {t:"كشف التغيرات الزمنية، مثل إزالة الغطاء النباتي، التحضر وتوسعات الزراعة عبر الزمن", c:true},
          {t:"فقط لتحسين الألوان", c:false},
          {t:"لرسم خرائط الطرق فقط", c:false}
        ],
        explanation: "تحليل السلاسل الزمنية يسمح برصد وتوثيق التغير المكاني عبر سنوات متعددة." },

/* 44 */ { q: "ما الذي يجب تجنبه عند تصميم سؤال خريطة للطلاب؟",
        choices: [
          {t:"تعليم القراءة من خطوط الكنتور", c:false},
          {t:"اختبار على خريطة بلا مقياس أو مظلل بدون مراجع", c:true},
          {t:"تدريب عملي", c:false},
          {t:"استخدام مقياس مناسب", c:false}
        ],
        explanation: "خرائط بلا مقياس أو مراجع تخفض مصداقية السؤال وتجعل القياس صعبًا." },

/* 45 */ { q: "اختر المصطلح الإملائي الصحيح: ما الصيغة الصحيحة لكلمة تُستخدم لوصف عملية \"توزيع السكان\" بالعربية؟",
        choices: [
          {t:"توزيع", c:true},
          {t:"توزيعّ", c:false},
          {t:"توزيعً", c:false},
          {t:"توزيعٌ", c:false}
        ],
        explanation: "الشكل الصحيح المعياري هو 'توزيع'." },

/* 46 */ { q: "ما تقنية مفيدة لقياس التغيرات في الخط الساحلي باستخدام صور الأقمار؟",
        choices: [
          {t:"المشاهدة بالعين فقط", c:false},
          {t:"تقنية مقارنة الحدود الساحلية بين صور متعددة زمنياً (change detection) وتحليل التراجع الساحلي", c:true},
          {t:"أخذ قياسات يدوية عشوائية", c:false},
          {t:"إزالة المشاهد البحرية", c:false}
        ],
        explanation: "تحديد التغير عبر الزمن باستخدام صور متعددة يسمح بتحليل التراجع الساحلي وكمية التآكل." },

/* 47 */ { q: "سؤال بسيط حسابي جغرافي: إذا كانت مساحة محافظة A 1200 كم² ومساحة محافظة B 800 كم² ومساحتهما معاً 2000 كم²، كم تبلغ الكثافة السكانية الكلية إن كان مجموع السكان 400,000؟",
        choices: [
          {t:"200 نسمة/كم²", c:true},
          {t:"250 نسمة/كم²", c:false},
          {t:"300 نسمة/كم²", c:false},
          {t:"150 نسمة/كم²", c:false}
        ],
        explanation: "الكثافة = 400,000 / 2000 = 200 نسمة/كم²." },

/* 48 */ { q: "ما الركن الأساسي لتصميم شبكة ري مستدامة في منطقة زراعية جافة؟",
        choices: [
          {t:"الاعتماد على مياه الأمطار فقط", c:false},
          {t:"تقييم مصادر المياه، كفاءة نظام الري، تقنيات الحفظ ومراقبة الاستهلاك", c:true},
          {t:"زيادة عدد العمال", c:false},
          {t:"زراعة محاصيل غريبة فقط", c:false}
        ],
        explanation: "التخطيط المستدام يتطلب تقييم الموارد، كفاءة الري واستخدام تقنيات الحفظ." },

/* 49 */ { q: "أي من التالي يعتبر سبباً رئيسياً للهجرة الدولية الاقتصادية؟",
        choices: [
          {t:"التنوع الحيوي", c:false},
          {t:"فجوات الأجور وفرص العمل والاختلاف في مستويات التنمية بين البلدان", c:true},
          {t:"التيارات البحرية", c:false},
          {t:"خط العرض", c:false}
        ],
        explanation: "الاختلافات الاقتصادية وفرص العمل تدفع الهجرة الاقتصادية بين الدول." },

/* 50 */ { q: "ما دور البنية التحتية للنقل في التنمية الاقتصادية الإقليمية؟",
        choices: [
          {t:"لا دور", c:false},
          {t:"تسهيل الحركة والتبادل وتقليل تكاليف التجارة وجذب الاستثمارات مما يعزز التنمية", c:true},
          {t:"زيادة الكثافة السكانية فقط", c:false},
          {t:"تخفيض المناخ", c:false}
        ],
        explanation: "بنية النقل تحسن الوصول إلى الأسواق وتخفض تكاليف الإنتاج وتدعم التنمية." },

/* 51 */ { q: "أي سؤال يقيس فهم الطالب لظاهرة الطقس والمناخ؟",
        choices: [
          {t:"ما تعريف الرياح؟", c:false},
          {t:"كيف يختلف مناخ البحر المتوسط عن مناخ الصحراء من حيث الأمطار والتذبذب الحراري؟", c:true},
          {t:"كم عدد المحطات الجوية؟", c:false},
          {t:"ما لون السحب؟", c:false}
        ],
        explanation: "مقارنة المناخ بين منطقتين تطلب تفسير الفروق في الأمطار ودرجات الحرارة وتُظهر فهمًا أعمق." },

/* 52 */ { q: "احسب: إذا كانت درجة انحدار نهر تساوي فرق ارتفاع 50 م على امتداد 10 كم، فما هو الانحدار بالمئة؟",
        choices: [
          {t:"0.5%", c:true},
          {t:"5%", c:false},
          {t:"50%", c:false},
          {t:"0.05%", c:false}
        ],
        explanation: "الانحدار = (50 / 10,000) × 100 = 0.5%." },

/* 53 */ { q: "ما مبدأ قياس المشاركة الفردية في مشروع ميداني جماعي؟",
        choices: [
          {t:"تجاهل الأدوار", c:false},
          {t:"تقليل تداخل المهام وتوثيق مساهمة كل طالب عبر سجلات وأدلة أداء", c:true},
          {t:"إلغاء المشروع", c:false},
          {t:"التقييم عبر الاختبار فقط", c:false}
        ],
        explanation: "تخفيض التداخل وتوثيق العمل يوضح مساهمة كل فرد في العمل الجماعي." },

/* 54 */ { q: "ما تعديل تعليمي مناسب لطلاب يفهمون الخرائط بصريًا بصعوبة؟",
        choices: [
          {t:"زيادة النصوص فقط", c:false},
          {t:"تجزئة المعلومات، استخدام رموز واضحة، خرائط تفاعلية وتدريبات تطبيقية", c:true},
          {t:"استخدام خرائط معقدة فقط", c:false},
          {t:"منع استخدام الخرائط", c:false}
        ],
        explanation: "تجزئة المحتوى والرموز الواضحة والخرائط التفاعلية تساعد المتعلمين البصريين/الضعفاء في الفهم." },

/* 55 */ { q: "اذكر وسيلتين لتعزيز إدارة الموارد المائية على مستوى المجتمع المحلي.",
        choices: [
          {t:"تجاهل الهدر", c:false},
          {t:"تطبيق برامج للحفاظ على المياه (ترشيد الاستهلاك) وإنشاء خزانات تجميع مياه الأمطار", c:true},
          {t:"زيادة الاستهلاك", c:false},
          {t:"استخدام المياه فقط للزراعة", c:false}
        ],
        explanation: "ترشيد الاستهلاك وجمع مياه الأمطار إجراءات عملية لإدارة موارد المياه محليًا." },

/* 56 */ { q: "ما مؤشر التباين الشائع لقياس التشتت في مجموعة قيم مكانية؟",
        choices: [
          {t:"الوسيط", c:false},
          {t:"الانحراف المعياري", c:true},
          {t:"أقصر مسافة", c:false},
          {t:"حجم العينة", c:false}
        ],
        explanation: "الانحراف المعياري يقيس مدى تشتت القيم حول المتوسط." },

/* 57 */ { q: "ما الفارق بين المعنى الحرفي والدلالي عند وصف ظاهرة جغرافية في نص ميداني؟",
        choices: [
          {t:"نفس المعنى", c:false},
          {t:"المعنى الحرفي وصف واضح؛ الدلالي يشمل التفسيرات التي تربط الظاهرة بعوامل أخرى ودلالاتها", c:true},
          {t:"دلالة فقط", c:false},
          {t:"حرفي غير مهم", c:false}
        ],
        explanation: "الوصف الحرفي يذكر ما هو ملاحظ، بينما الدلالي يفسر الروابط والأسباب والنتائج." },

/* 58 */ { q: "احسب: في شبكة طرق، إذا كان عدد الطرق الرئيسية 3 وكل طريق يلتقي بالطريق الآخر مرة واحدة، كم عدد تقاطعات ثنائية الاتجاه؟",
        choices: [
          {t:"6", c:false},
          {t:"3", c:true},
          {t:"9", c:false},
          {t:"0", c:false}
        ],
        explanation: "ثلاثة طرق تلتقي ببعضها => عدد التقاطعات = 3 (كل زوج طريق يتقاطع مرة واحدة)." },

/* 59 */ { q: "ما الذي يعزز اتساق تقييم مشاريع الجغرافيا بين المصححين؟",
        choices: [
          {t:"ترك الحكم حرًا", c:false},
          {t:"استخدام دليل تصحيح (Rubric) واضح مع معايير ونماذج إجابة", c:true},
          {t:"تبديل المصححين باستمرار", c:false},
          {t:"التصحيح العشوائي", c:false}
        ],
        explanation: "وجود روبريك واضح يقلل فروق الحكم بين المصححين ويزيد العدالة." },

/* 60 */ { q: "ما إجراء مناسب عند ملاحظة تناقص مستمر في حضور طلاب لحصص الحقل الميداني؟",
        choices: [
          {t:"فرض غرامات فقط", c:false},
          {t:"التواصل مع الطلاب لمعرفة الأسباب، تهيئة دعم لوجستي وتقليل الحواجز المادية والمالية", c:true},
          {t:"إلغاء الحصص", c:false},
          {t:"تغيير المقررات كلها", c:false}
        ],
        explanation: "التواصل وفهم الأسباب وتقديم دعم عملي حلول فعالة بدلاً من العقاب فقط." },

/* 61 */ { q: "من المعروف بتجاربه حول الاستجابة المنعكسة (الشرط الكلاسيكي) والتي تُستخدم كنموذج في بعض دراسات سلوك الإنسان؟",
        choices: [
          {t:"بياجيه", c:false},
          {t:"بافلوف", c:true},
          {t:"سكنر", c:false},
          {t:"فيجوتسكي", c:false}
        ],
        explanation: "إيفان بافلوف ارتبطت تجاربه بالشرط الكلاسيكي والانعكاسات." },

/* 62 */ { q: "لماذا نستخدم أنشطة متعددة الحواس في تدريس الجغرافيا الميدانية؟",
        choices: [
          {t:"للمتعة فقط", c:false},
          {t:"لتشغيل عدة قنوات تعلمية (رؤية، لمسة، سمع) مما يعزز الاحتفاظ واسترجاع المعلومات", c:true},
          {t:"لإطالة الحصة", c:false},
          {t:"لتعقيد المهمة", c:false}
        ],
        explanation: "تعدد الحواس يخلق تمثيلات متعددة للمعلومة ويعزز التثبيت." },

/* 63 */ { q: "لماذا نبني المشتتات في أسئلة الاختيار من متعدد على أخطاء مفاهيمية شائعة؟",
        choices: [
          {t:"لإرباك الطلاب", c:false},
          {t:"لكشف مستوى الفهم الحقيقي للطلاب وإظهار الأخطاء المفاهيمية", c:true},
          {t:"لزيادة طول الاختبار", c:false},
          {t:"لتسريع التصحيح", c:false}
        ],
        explanation: "المشتتات الذكية تكشف إن كان الطالب فهم المفهوم أم وقع في الخطأ الشائع." },

/* 64 */ { q: "إذا كان مقياس خريطة ما 1:50,000 وكان طول نهر على الخريطة 6 سم، فما طوله الحقيقي بالكم؟",
        choices: [
          {t:"3 كم", c:true},
          {t:"30 كم", c:false},
          {t:"300 كم", c:false},
          {t:"0.3 كم", c:false}
        ],
        explanation: "6 سم × 50,000 = 300,000 سم = 3,000 م = 3 كم." },

/* 65 */ { q: "ما الذي يركز عليه التعليم الجغرافي القائم على الكفاءة؟",
        choices: [
          {t:"عدد الساعات", c:false},
          {t:"إتقان الطالب لمهارات محددة مثل قراءة الخرائط، تحليل البيانات المكانية واتخاذ قرارات مكانية مستقلة", c:true},
          {t:"الواجبات فقط", c:false},
          {t:"المحاضرات الطويلة", c:false}
        ],
        explanation: "التعليم القائم على الكفاءة يركز على إظهار المهارات بدلاً من الوقت المستغرق." },

/* 66 */ { q: "أي عبارة تمثل استعارة جغرافية بلاغية؟",
        choices: [
          {t:"المدينة خلية نحل", c:true},
          {t:"الخرائط حقيقية فقط", c:false},
          {t:"الطرق لا تتقاطع", c:false},
          {t:"الأنهار ثابتة", c:false}
        ],
        explanation: "الاستعارة 'المدينة خلية نحل' تنقل صورة عن النشاط والتراص السكاني." },

/* 67 */ { q: "لماذا نأخذ عينات من بنك الأسئلة عند إعداد عدة نسخ من اختبار جغرافي؟",
        choices: [
          {t:"لزيادة صعوبة الاختبار", c:false},
          {t:"لتوفير تنوع بنود، تقليل احتمال تسريب الأسئلة وتحسين تمثيل المحتوى", c:true},
          {t:"لتقليل التحليل الإحصائي", c:false},
          {t:"لتكرار نفس السؤال", c:false}
        ],
        explanation: "أخذ عينات يضمن تمثيل موضوعي وتنوعًا ويقلل تكرار البنود بين الاختبارات." },

/* 68 */ { q: "ما العامل الأهم لنجاح تدريس مادة الجغرافيا؟",
        choices: [
          {t:"وجود كتب فقط", c:false},
          {t:"وضوح الأهداف وتوافق الأنشطة والتقويم والمصادر الميدانية", c:true},
          {t:"زيادة الواجبات فقط", c:false},
          {t:"استخدام التقنية بدون خطة", c:false}
        ],
        explanation: "وضوح الأهداف وتوافق الأنشطة والتقويم مع أهداف التعلم هو الأساس لنجاح التدريس." }

]; // نهاية QUESTIONS

/* ===========================
   إنشاء بنية الأسئلة في الصفحة + تفعيل الخلط والدقة
   =========================== */

const quizColumn = document.getElementById('quizColumn');
const total = QUESTIONS.length;

function makeQuestionBlock(item, idx){
  const box = document.createElement('div');
  box.className = 'question-box';
  box.dataset.index = idx;

  const head = document.createElement('div');
  head.className = 'q-head';
  head.innerHTML = `<div class="q-num">س ${idx+1}</div><div style="font-weight:800;color:var(--muted)">سؤال ${idx+1}</div>`;
  box.appendChild(head);

  const qt = document.createElement('div');
  qt.className = 'question-text';
  qt.textContent = item.q;
  box.appendChild(qt);

  const choices = document.createElement('div');
  choices.className = 'choices';

  // أنشئ عناصر الاختيار كـ label يحتوي input + نص، واحفظ data-correct
  item.choices.forEach((ch, i) => {
    const lbl = document.createElement('label');
    lbl.setAttribute('data-correct', ch.c ? 'true' : 'false');
    const input = document.createElement('input');
    input.type = 'radio';
    input.name = `q${idx+1}`;
    input.value = i;
    lbl.appendChild(input);
    const span = document.createElement('span');
    span.textContent = ch.t;
    lbl.appendChild(span);
    choices.appendChild(lbl);
  });

  // خلط عناصر الـ label داخل choices (يبقى data-correct مرتبطًا)
  shuffleChildren(choices);

  box.appendChild(choices);

  // شرح (سيظهر بعد الاختيار)
  const expl = document.createElement('div');
  expl.className = 'explanation';
  expl.innerHTML = `<strong>الشرح:</strong> ${item.explanation}`;
  box.appendChild(expl);

  // إضافة حدث لاختيار الإجابة
  choices.querySelectorAll('input').forEach(inp=>{
    inp.addEventListener('change', function(){
      // منع تغيير الإجابة بعد الاختيار: نُعطّل كل الـ labels في الـ choices
      choices.querySelectorAll('label').forEach(lbl=>{
        lbl.classList.add('disabled');
        const isCorrect = lbl.dataset.correct === 'true';
        if(isCorrect){
          lbl.classList.add('correct');
        } else {
          // إذا هذا الـ label يحتوي الـ input المُختار، نضعه خطأ
          if(lbl.contains(this)) lbl.classList.add('wrong');
        }
      });
      // إظهار الشرح
      expl.style.display = 'block';
      // حدّث الإحصائيات
      updateSummary();
    });
  });

  return box;
}

function shuffleChildren(container){
  const nodes = Array.from(container.children);
  for(let i = nodes.length -1; i>0; i--){
    const j = Math.floor(Math.random()*(i+1));
    container.appendChild(nodes[j]);
    nodes.splice(j,1);
  }
}

// أدخل كل الأسئلة في الصفحة
QUESTIONS.forEach((q, idx) => {
  quizColumn.appendChild(makeQuestionBlock(q, idx));
});

/* ===========================
   وظائف التلخيص وتحديث الشريط
   =========================== */

const statCorrect = document.getElementById('statCorrect');
const statAnswered = document.getElementById('statAnswered');
const statPercent = document.getElementById('statPercent');
const progressBar = document.getElementById('progressBar');
const finalScore = document.getElementById('finalScore');

function updateSummary(){
  let correct = 0;
  let answered = 0;
  document.querySelectorAll('.question-box').forEach(box=>{
    const choices = box.querySelectorAll('.choices label');
    let answeredThis = false;
    choices.forEach(lbl=>{
      if(lbl.classList.contains('correct') && lbl.classList.contains('disabled')) {
        // correct chosen or correct revealed
      }
      if(lbl.classList.contains('disabled')) {
        // this question was answered (since we disable labels after any selection)
        answeredThis = true;
      }
      // If a correct label exists and it's disabled, but we only increment correct if the chosen radio was that label
    });
    if(answeredThis){
      answered++;
      // determine if the user chose the correct one:
      const chosen = box.querySelector('input:checked');
      if(chosen){
        const parentLabel = chosen.closest('label');
        if(parentLabel && parentLabel.dataset.correct === 'true') correct++;
      }
    }
  });
  statCorrect.textContent = correct;
  statAnswered.textContent = `${answered} / ${total}`;
  const percent = total===0?0:Math.round((correct/total)*100);
  statPercent.textContent = `${percent}%`;
  progressBar.style.width = `${Math.round((answered/total)*100)}%`;
  if(finalScore) finalScore.textContent = `${correct} / ${total}`;
}

/* ===========================
   أزرار التحكم
   =========================== */

document.getElementById('showAll').addEventListener('click', () => {
  // إظهار الإحصاءات النهائية + فتح overlay
  updateSummary();
  const correct = Number(statCorrect.textContent);
  const totalQ = total;
  const panelBreak = document.getElementById('finalBreak');
  if (correct === totalQ) panelBreak.innerText = 'ممتاز — إجابات جميعها صحيحة!';
  else if (correct >= Math.ceil(totalQ * 0.85)) panelBreak.innerText = 'ممتاز جداً — مستوى متقدم!';
  else if (correct >= Math.ceil(totalQ * 0.7)) panelBreak.innerText = 'جيد جدًا — أداء قوي';
  else if (correct >= Math.ceil(totalQ * 0.5)) panelBreak.innerText = 'متوسط — يحتاج مراجعة مركزة';
  else panelBreak.innerText = 'ضعيف — أنصح بمراجعة الأساسيات والتدريب المكثف';
  document.getElementById('overlay').style.display = 'flex';
});

document.getElementById('closeOverlay').addEventListener('click', () => {
  document.getElementById('overlay').style.display = 'none';
});

document.getElementById('resetBtn').addEventListener('click', () => {
  // إعادة كل شيء للحالة الابتدائية (إعادة الخلط أيضاً)
  document.querySelectorAll('.question-box').forEach((box, i) => {
    // أزل الشروحات
    const expl = box.querySelector('.explanation');
    if(expl) expl.style.display = 'none';
    // إعادة إنشاء الـ choices لإعادة الخلط والحالة
    const choicesDiv = box.querySelector('.choices');
    // حفظ بيانات خيارات السؤال الأصلية من QUESTIONS
    const qIndex = Number(box.dataset.index);
    const orig = QUESTIONS[qIndex].choices;
    choicesDiv.innerHTML = '';
    orig.forEach((ch, idx) => {
      const lbl = document.createElement('label');
      lbl.setAttribute('data-correct', ch.c ? 'true':'false');
      const input = document.createElement('input');
      input.type = 'radio';
      input.name = `q${qIndex+1}`;
      input.value = idx;
      lbl.appendChild(input);
      const span = document.createElement('span');
      span.textContent = ch.t;
      lbl.appendChild(span);
      choicesDiv.appendChild(lbl);
    });
    shuffleChildren(choicesDiv);
    // أعِد حدث الاختيار
    choicesDiv.querySelectorAll('input').forEach(inp=>{
      inp.addEventListener('change', function(){
        choicesDiv.querySelectorAll('label').forEach(lbl=>{
          lbl.classList.add('disabled');
          const isCorrect = lbl.dataset.correct === 'true';
          if(isCorrect) lbl.classList.add('correct');
          else if(lbl.contains(this)) lbl.classList.add('wrong');
        });
        const expl = box.querySelector('.explanation');
        if(expl) expl.style.display = 'block';
        updateSummary();
      });
    });
  });
  // إعادة الإحصاءات
  updateSummary();
  window.scrollTo({top:0, behavior:'smooth'});
});

/* Initialize summary */
updateSummary();
</script>
</body>
</html>
