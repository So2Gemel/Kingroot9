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

---
ثغرات libanogs.so
---
[line 82]
// int isalpha(int);
// __pid_t getppid(void);
// int pthread_mutexattr_settype(pthread_mutexattr_t *attr, int kind);
---
[line 141]
// int gettimeofday(struct timeval *tv, __timezone_ptr_t tz);
// __int64 ptrace(enum __ptrace_request request, ...);
// __int64 __fastcall __assert2(_QWORD, _QWORD, _QWORD, _QWORD); weak
---
[line 173]
// FILE *popen(const char *command, const char *modes);
// int prctl(int option, ...);
// int fcntl(int fd, int cmd, ...);
---
[line 202]
// int tolower(int c);
// __int64 syscall(__int64 sysno, ...);
// __int64 __fastcall __fgets_chk(_QWORD, _QWORD, _QWORD, _QWORD); weak
---
[line 23995]
// int gettimeofday(struct timeval *tv, __timezone_ptr_t tz);
// __int64 ptrace(enum __ptrace_request request, ...);
// ssize_t sendmsg(int fd, const struct msghdr *message, int flags);
---
[line 24005]
// void *memcpy(void *dest, const void *src, size_t n);
// __int64 syscall(__int64 sysno, ...);
// int connect(int fd, const struct sockaddr *addr, socklen_t len);
---
[line 85060]

  result = prctl(
             *(_DWORD *)a1,
---
[line 93539]

  prctl(4, 1LL, 0LL, 0LL, 0LL);
  sub_C330978();
---
[line 93927]

  if ( ptrace(PTRACE_ATTACH, a2, 0LL, 0LL) )
    v2 = 1;
---
[line 94070]
LABEL_20:
      ptrace(PTRACE_CONT, (unsigned int)v4, 0LL, v5);
    }
---
[line 94093]
    v2 = a2;
    ptrace(PTRACE_DETACH, a2, 0LL, 0LL);
    if ( v2 >= 1 )
---
[line 94175]
      sub_C2EE508(v3, &stat_loc, 0x40000000);
      ptrace(PTRACE_DETACH, (unsigned int)v3, 0LL, 0LL);
      result = kill(v3, 18);
---
[line 94876]
  }
  *(_DWORD *)(a1 + 20) = prctl(3, 0LL, 0LL, 0LL, 0LL);
  v8 = prctl(4, 1LL, 0LL, 0LL, 0LL);
---
[line 94877]
  *(_DWORD *)(a1 + 20) = prctl(3, 0LL, 0LL, 0LL, 0LL);
  v8 = prctl(4, 1LL, 0LL, 0LL, 0LL);
  if ( (_DWORD)v8 )
---
[line 99033]
  *a2 = a2[(int)v3];
  if ( (unsigned int)ptrace(PTRACE_SETREGSET, *(unsigned int *)(a1 + 104), 1LL, v5) )
    return 0xFFFFFFFFLL;
---
[line 99192]

  v3 = ptrace(PTRACE_ATTACH, a2, 0LL, 0LL);
  if ( v3 )
---
[line 99280]
{
  ptrace(PTRACE_DETACH, a1, 0LL, 0LL);
  return 0xFFFFFFFFLL;
---
[line 99304]
{
  return ptrace(PTRACE_DETACH, a2, 0LL, 0LL);
}
---
[line 99428]
  if ( !*(_BYTE *)(a1 + 104) )
    return syscall(sysno, a3, a4, a5, a6, a7, a8, a9);
  if ( !qword_C842018 )
---
[line 99430]
  if ( !qword_C842018 )
    qword_C842018 = getppid();
  result = syscall(173LL, a3, a4, a5, a6, a7, (unsigned __int16)sysno | 0xBEEF0000LL);
---
[line 99431]
    qword_C842018 = getppid();
  result = syscall(173LL, a3, a4, a5, a6, a7, (unsigned __int16)sysno | 0xBEEF0000LL);
  if ( result == qword_C842018 && sysno != 48879 )
---
[line 100283]
  v4 = atoi(nptr);
  if ( ptrace(PTRACE_ATTACH, v4, 0LL, 0LL) )
  {
---
[line 100307]
    }
    ptrace(PTRACE_DETACH, v4, 0LL, 0LL);
    v12 = sub_C65FBA8(25380);
---
[line 100663]
    sub_C61FB5C(v6, 512, v2, s, v3, v4);
    prctl(4, 1LL, 0LL, 0LL, 0LL);
    sub_C330978();
---
[line 109770]
  v121 = "/libc.so";
  v119 = &ptrace;
  v122 = sub_C65E120(30657);
---
[line 110075]
                                              {
                                                return (__pid_t (**)(void))&ptrace;
                                              }
---
[line 235543]

  v18 = syscall(113LL, 4LL, &a12);
  if ( (_DWORD)v18 )
---
[line 283659]
  }
  else if ( a5 && (prctl(1398164801, 0LL, a2, 4096LL, a5) & 0x80000000) != 0 )
  {
---
[line 326362]
    && *(_QWORD *)(v30 + 104)
    && prctl(1398164801, 0LL, *(_QWORD *)(v30 + 104), *(unsigned int *)(v30 + 92), *(_QWORD *)(v30 + 72)) == -1 )
  {
---
[line 344087]
  sub_C3C17A0();
  if ( prctl(1398164801, 0LL, v5, v7, v3) )
  {
---
[line 367744]
          {
            v15 = prctl(1398164801, 0LL, addr, lena, a1[14]);
            a1[14] = 0LL;
---
[line 367749]
          {
            v15 = prctl(1398164801, 0LL, addr, lena, "objects_external_alloc");
          }
---
[line 410207]

  LODWORD(result) = prctl(a1);
  *(_DWORD *)(v1 - 4) = 3;
---
[line 556439]
    case 0:
      v25 = syscall(v22);
      *(_DWORD *)(v24 - 168) = 5;
---
[line 556448]
    case 1:
      v25 = syscall(v22, *(_QWORD *)(*(_QWORD *)v21 + 72LL));
      *(_DWORD *)(v24 - 164) = -367105137;
---
[line 556457]
    case 2:
      v25 = syscall(v22, *(_QWORD *)(*(_QWORD *)v21 + 72LL), *(_QWORD *)(*(_QWORD *)v21 + 80LL));
      *(_DWORD *)(v24 - 168) = 92;
---
[line 574868]
                  sub_C3C17A0();
                  if ( prctl(1398164801, 0LL, v282, v355, v248) )
                    *(_QWORD *)v595 = 0LL;
---
[line 602024]
            v188 = v137;
            *v137 = &ptrace;
            *v168 = 25795;
---
[line 602100]
              result = sub_C5CF09C(a2, v136);
              *v137 = &ptrace;
              return result;
---
[line 651223]
    {
      prctl(15, a1 + 16);
      memset(v12, 0, sizeof(v12));
---
[line 651225]
      memset(v12, 0, sizeof(v12));
      if ( prctl(16, v12) )
        LOBYTE(v12[0]) = 0;
---
[line 651249]
    }
    else if ( prctl(16, v13) )
    {
---
[line 651292]
  if ( a1 && *a1 )
    return prctl(15, a1);
  else
---
[line 651301]
  if ( a1 && a2 )
    return prctl(16, a1);
  else
---