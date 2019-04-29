---
title: Функция FunctionTailcall3WithInfo
ms.date: 03/30/2017
api_name:
- FunctionTailcall3WithInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall3WithInfo
helpviewer_keywords:
- FunctionTailcall3WithInfo function [.NET Framework profiling]
ms.assetid: 46380fcc-0198-43ae-a1f5-2d4939425886
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4352d006c95a5b85341625220e6c7e62a86b482a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598770"
---
# <a name="functiontailcall3withinfo-function"></a>Функция FunctionTailcall3WithInfo
Уведомляет профилировщик, текущей выполняемой функции собирается выполнить вызов с префиксом tail в другую функцию и предоставляет маркер, который может быть передан [метод ICorProfilerInfo3::GetFunctionTailcall3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) для извлечения кадр стека.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __stdcall FunctionTailcall3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a>Параметры  
 `functionIDOrClientID`  
 [in] Идентификатор текущей выполняемой функции, который собираетесь сделать с префиксом tail.  
  
 `eltInfo`  
 [in] Непрозрачный дескриптор, представляющий сведения об указанном кадре стека. Этот дескриптор допустим только во время обратного вызова, к которому он передается.  
  
## <a name="remarks"></a>Примечания  
 `FunctionTailcall3WithInfo` Метод обратного вызова Уведомляет профилировщик, как функции, называются, а также позволяет профилировщику использовать [метод ICorProfilerInfo3::GetFunctionTailcall3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) для проверки кадров стека. Чтобы получить доступ к сведения о кадре стека, `COR_PRF_ENABLE_FRAME_INFO` флаг должно иметь значение. Можно использовать профилировщик [метод ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) установить флаги событий, а затем использовать [метод ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) для регистрации вашей Реализация этой функции.  
  
 `FunctionTailcall3WithInfo` Функция является обратным вызовом; это необходимо реализовать. В реализации должен использоваться `__declspec(naked)` атрибут класса хранения.  
  
 Ядро выполнения не сохраняет значения регистров перед вызовом этой функции.  
  
- При входе необходимо сохранить все регистры, которые вы используете, включая те, в единицах с плавающей запятой (FPU).  
  
- При выходе необходимо восстановить стек путем выталкивания из всех параметров, которые были отправлены вызывающим кодом.  
  
 Реализация `FunctionTailcall3WithInfo` не должен блокироваться, поскольку это приведет к задержке сборки мусора. Реализация не должны в сбор мусора, так как стек может находиться в состоянии коллекции с поддержкой сборки мусора. При попытке сбора мусора, среда выполнения будет блокироваться до `FunctionTailcall3WithInfo` возвращает.  
  
 Кроме того функция FunctionTailcall3WithInfo не должен вызов управляемого кода или инициировать распределение управляемой памяти любым способом.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [SetFunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [Глобальные статические функции профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
