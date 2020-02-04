---
title: Метод ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.SetEnterLeaveFunctionHooks2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
helpviewer_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
- SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
ms.assetid: 3c26b3e7-f72b-48a5-bf8c-edc122523a4b
topic_type:
- apiref
ms.openlocfilehash: 7eac42e1d8132ca9e6d6c6b43efd43b88c1e5d3d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868589"
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a>Метод ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
Задает реализованные профилировщиком функции, которые должны вызываться в обновленных версиях обработчиков "Enter", "Leave" и "таилкалл" управляемых функций.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
## <a name="parameters"></a>Параметры  
 `pFuncEnter`  
 окне Указатель на реализацию, которая будет использоваться в качестве обратного вызова [FunctionEnter2](functionenter2-function.md) .  
  
 `pFuncLeave`  
 окне Указатель на реализацию, которая будет использоваться в качестве обратного вызова [FunctionLeave2](functionleave2-function.md) .  
  
 `pFuncTailcall`  
 окне Указатель на реализацию, которая будет использоваться в качестве обратного вызова [FunctionTailcall2](functiontailcall2-function.md) .  
  
## <a name="remarks"></a>Заметки  
 Метод `SetEnterLeaveFunctionHooks2` аналогичен методу [ICorProfilerInfo:: сетентерлеавефунктионхукс](icorprofilerinfo-setenterleavefunctionhooks-method.md) . Используйте первое значение для указания функций, которые будут использоваться в качестве новых версий обратных вызовов Enter/Leave/таилкалл, а второй — для указания функций, которые будут использоваться в качестве старых версий обратных вызовов Enter/Leave/таилкалл.  
  
 Одновременно может быть активным только один набор обратных вызовов. Таким же, если профилировщик вызывает и `ICorProfilerInfo::SetEnterLeaveFunctionHooks`, и `SetEnterLeaveFunctionHooks2`, используется `SetEnterLeaveFunctionHooks2`.  
  
 Метод `SetEnterLeaveFunctionHooks2` может быть вызван только из обратного вызова [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) профилировщика.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Интерфейс ICorProfilerInfo2](icorprofilerinfo2-interface.md)
