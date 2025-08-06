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
