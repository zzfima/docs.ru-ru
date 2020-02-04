---
title: Метод ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetEnterLeaveFunctionHooks3WithInfo Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
ms.assetid: ca8ea534-e441-47b8-be85-466410988c0a
topic_type:
- apiref
ms.openlocfilehash: 4fe18b4f07e6f282571b13faff5ce51b66ce416b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868490"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3withinfo-method"></a>Метод ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo
Задает реализованные профилировщиком функции, которые будут вызываться для обработчиков [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)и [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) управляемых функций.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3WithInfo(  
            [in] FunctionEnter3WithInfo    *pFuncEnter3,  
            [in] FunctionLeave3withInfo    *pFuncLeave3,  
            [in] FunctionTailcall3WithInfo *pFuncTailcall3);  
```  
  
## <a name="parameters"></a>Параметры  
 `pFuncEnter3`  
 окне Указатель на реализацию, которая будет использоваться в качестве обратного вызова `FunctionEnter3WithInfo`.  
  
 `pFuncLeave3`  
 окне Указатель на реализацию, которая будет использоваться в качестве обратного вызова `FunctionLeave3WithInfo`.  
  
 `pFuncTailcall3`  
 окне Указатель на реализацию, которая будет использоваться в качестве обратного вызова `FunctionTailcall3WithInfo`.  
  
## <a name="remarks"></a>Заметки  
 Обработчики [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)и [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) предоставляют кадры стека и проверку аргументов. Для доступа к этой информации необходимо задать флаги `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`и/или `COR_PRF_ENABLE_FRAME_INFO`. Профилировщик может использовать метод [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) для установки флагов событий, а затем использовать метод `SetEnterLeaveFunctionHooks3WithInfo` для регистрации реализации этой функции.  
  
 В каждый момент времени активным может быть только один набор обратных вызовов, а последняя версия имеет приоритет. Таким образом, если профилировщик вызывает и [SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) , и `SetEnterLeaveFunctionHooks3WithInfo`, используется `SetEnterLeaveFunctionHooks3WithInfo`.  
  
 Метод `SetEnterLeaveFunctionHooks3WithInfo` может быть вызван только из обратного вызова [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) профилировщика.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [FunctionEnter3](functionenter3-function.md)
- [FunctionLeave3](functionleave3-function.md)
- [FunctionTailcall3](functiontailcall3-function.md)
- [FunctionEnter3WithInfo](functionenter3withinfo-function.md)
- [FunctionLeave3WithInfo](functionleave3withinfo-function.md)
- [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)
- [Глобальные статические функции профилирования](profiling-global-static-functions.md)
- [Интерфейс ICorProfilerInfo3](icorprofilerinfo3-interface.md)
- [Интерфейсы профилирования](profiling-interfaces.md)
- [Профилирование](index.md)
