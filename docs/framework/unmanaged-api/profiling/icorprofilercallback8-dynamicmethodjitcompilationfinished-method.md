---
title: ICorProfilerCallback8::DynamicMethodJITCompilationГотовый метод
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: c2e9489654a0fe5fa65ec638ed0f991a6c01415a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175113"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a>ICorProfilerCallback8::DynamicMethodJITCompilationГотовый метод
«Поддерживается в рамках .NET 4.7 и более поздних версиях»  
  
Уведомляет профайлера всякий раз, когда компиляция динамического метода JIT завершена.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,
     [in]  BOOL        hrStatus,
     [in]  BOOL        fIsSafeToBlock
);  
```  
  
## <a name="parameters"></a>Параметры  
[in] `functionId`  
Идентификатор функции в памяти, для которой запускается компиляция JIT.

(в) `hrStatus` Значение, указывавое, была ли компиляция JIT успешным.

(в) `fIsSafeToBlock` указать, что блокировка может привести к тому, что время выполнения может привести к тому, что поток вызова вернется из этого обратного 
 `true` вызова; `false` указать, что блокировка не повлияет на работу времени выполнения.  

## <a name="remarks"></a>Remarks  

Этот обратный вызов запускается всякий раз, когда компиляция динамического метода JIT закончена. Это включает в себя различные заглушки IL и методы LCG. Его цель заключается в предоставлении сценаристам-профилировщикам достаточно информации для идентификации компилированного метода для пользователей.

> [!NOTE]
> `functionId`значения не могут быть использованы для разрешения их токенов метаданных, поскольку динамические методы не имеют метаданных.

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [Интерфейс ICorProfilerCallback8](icorprofilercallback8-interface.md)
