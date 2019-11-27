---
title: Метод ICorProfilerCallback4::GetReJITParameters
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.GetReJITParameters
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::GetReJITParameters
helpviewer_keywords:
- ICorProfilerCallback4::GetReJITParameters method [.NET Framework profiling]
- GetReJITParameters method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 0e9bfe07-9f20-498c-b568-9017c8f6056c
topic_type:
- apiref
ms.openlocfilehash: d81d7275d197de1dfc99b135377459f509c2651f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439435"
---
# <a name="icorprofilercallback4getrejitparameters-method"></a>Метод ICorProfilerCallback4::GetReJITParameters
Позволяет профилировщику кода устанавливать альтернативные флаги создания кода для нового текста перекомпилированного метода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
## <a name="parameters"></a>Параметры  
 `moduleID`  
 окне Модуль, содержащий метод, для которого среда CLR требует параметры JIT-компиляции.  
  
 `methodId`  
 окне `MethodDef` метода, для которого среда CLR требует параметры JIT-компиляции.  
  
 `pFunctionControl`  
 окне Указатель на интерфейс [икорпрофилерфунктионконтрол](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) , который профилировщик может использовать для предоставления сведений о JIT-компиляции для метода, для которого выполняется повторная компиляция.  
  
## <a name="remarks"></a>Заметки  
 Среда CLR выдает ответный вызов `GetReJITParameters`, чтобы профилировщик мог указать параметры для перекомпиляции данного метода. Обратный вызов `GetReJITParameters` выдается только один раз для каждой функции; параметры, предоставляемые профилировщиком, применяются ко всем экземплярам этой функции.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Интерфейс ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [Метод JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
- [Метод ReJITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
