LibUE4.so
---
| String | الوظيفة المحتملة |
|--------|------------------|
| AntiCheatRandValue0 إلى AntiCheatRandValue5 | قيم عشوائية تُستخدم في التحقق الديناميكي، غالبًا داخل Tick أو MovementComponent |
| bUseMoveAntiCheatCheck | فلاغ لتفعيل حماية الحركة |
| OwnerMoveAntiCheat | حماية مرتبطة بصاحب الكائن (اللاعب أو المركبة) |
| bEnableAntiCheat | فلاغ عام لتفعيل النظام |
| AntiCheatDetailData / ReportAntiCheatDetailData | بيانات تُرسل للسيرفر أو تُسجل داخليًا عند الكشف |
| AntiCheatMaxOmega | حد السرعة الدورانية، غالبًا مرتبط بالمركبات أو الكاميرا |
| bUseTimeSpeedAntiCheatCheck | حماية ضد التلاعب بالزمن أو السرعة |
| RestartAntiCheat | إعادة تهيئة النظام بعد كشف أو عند respawn |
| AntiCheatComp / InvalidAntiCheatComp | مكون الحماية داخل الكائنات، غالبًا داخل UActorComponent أو USceneComponent |
| ESpectatorException_NoAntiCheatLog | استثناءات للمشاهدين، ممكن نستخدمها لتجاوز الحماية في وضع spectator |

---

🔍 ملفات المصدر المرتبطة

| الملف | الوظيفة |
|-------|---------|
| MoveAntiCheatComponent.cpp | حماية الحركة، ممكن نهوكها لتجاوز teleport أو speedhack |
| Weapon/DefaultAntiCheatComponent.cpp | حماية الأسلحة، غالبًا تتحقق من إطلاق النار أو التبديل |
| Vehicle/AntiCheat/VacConfig.cpp | إعدادات حماية المركبات |
| Security/PlayerAntiCheatManager.cpp | مدير الحماية العام، نقطة مركزية للهووكات |
| Vehicle/Wheeled/STExtraVehicleMovementComponent4W_AntiCheat.cpp | حماية حركة المركبات ذات العجلات |
| Weapons/EntityAntiCheatComponent.cpp | حماية الكيانات المرتبطة بالأسلحة |
| Vehicle/AntiCheat/VacTimeSpeed.cpp | حماية الزمن والسرعة داخل المركبة |
| Vehicle/VehicleAntiCheat.cpp | الحماية العامة للمركبة |

---

libanogs.so

---

🧠 جدول وظائف الدوال المعمارية (من 1 إلى 20 كمجموعة أولى)

| رقم | اسم الدالة | نوع الوظيفة | ملخص العمل |
|-----|------------|--------------|-------------|
| 1 | AnoSDKGetReportData | منطق عام | استرجاع بيانات تقرير بدون مؤشرات حساسة، يستدعي دوال داخلية |
| 2 | AnoSDKDelReportData | منطق عام | حذف بيانات تقرير، غالبًا جزء من دورة حياة البيانات |
| 3 | AnoSDKOnRecvData | منطق عام | استقبال بيانات وتحليلها، يحتوي على تحقق داخلي |
| 4 | AnoSDKGetReportData2 | وظيفة قصيرة | غلاف بسيط أو تهيئة، يستدعي دالة واحدة |
| 5 | AnoSDKGetReportData3 | وظيفة قصيرة | مشابه لـ 4، تهيئة أو تغليف |
| 6 | AnoSDKDelReportData3 | منطق عام | حذف بيانات تقرير، يحتوي على قفزات غير مباشرة |
| 7 | AnoSDKGetReportData4 | منطق عام | استرجاع تقرير بناءً على رقم، يستدعي دالة واحدة |
| 8 | AnoSDKDelReportData4 | منطق عام | حذف تقرير بناءً على رقم، يستدعي دالة واحدة |
| 9 | AnoSDKOnRecvSignature | منطق عام | استقبال توقيع والتحقق منه، يستدعي دالة واحدة |
| 10 | sub_C2DFB48 | منطق عام | تحكم داخلي، يستدعي دوال حماية فرعية |
| 11 | sub_C2F02F0 | منطق عام | تهيئة اتصال عبر socketpair، يستدعي دوال نظام |
| 12 | sub_C2F86D4 | تحقق / تهيئة | يحتوي على malloc و memcmp، نقطة تحقق حساسة |
| 13 | sub_C304EE8 | ملفات / شبكة / خيوط | إدارة مسارات واتصالات وخيوط، مع مزامنة |
| 14 | if(result) | ملفات / شبكة / خيوط | تحكم في النظام عبر دوال متعددة |
| 15 | sub_C306520 | منطق عام | دالة ضخمة بـ 15 باراميتر، تستدعي دوال حماية متعددة |
| 16 | sub_C3066A0 | منطق عام | تحكم داخلي، يستدعي دوال حماية وتحقق |
| 17 | if(a1) | منطق عام | تحقق داخلي بسيط، يستدعي دوال حماية |
| 18 | sub_C30E368 | منطق عام | يستدعي دوال تحقق وتشفير، يحتوي على منطق متشابك |
| 19 | sub_C3107C4 | منطق عام | دالة بدون عودة، تستدعي دوال حماية |
| 20 | sub_C31983C | منطق عام | تحكم داخلي، يستدعي دوال حماية فقط |
