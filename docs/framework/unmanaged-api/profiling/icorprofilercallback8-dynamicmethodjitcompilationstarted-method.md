---
title: ICorProfilerCallback8::DynamicMethodJITCompilationМетод
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: e8b1a243b691d8d5eb364fd16821fd9156505c60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177050"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a>ICorProfilerCallback8::DynamicMethodJITCompilationМетод
«Поддерживается в рамках .NET 4.7 и более поздних версиях»  
  
Уведомляет профайлера всякий раз, когда начинается компиляция динамического метода JIT.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,
     [in]  BOOL        fIsSafeToBlock,
     [in]  LPCBYTE     pILHeader,
     [in]  LONG        cbILHeader
);  
```  
  
## <a name="parameters"></a>Параметры  
[in] `functionId`  
Идентификатор функции в памяти, для которой запускается компиляция JIT.

(в) `fIsSafeToBlock` указать, что блокировка может привести к тому, что время выполнения может привести к тому, что поток вызова вернется из этого обратного 
 `true` вызова; `false` указать, что блокировка не повлияет на работу времени выполнения.  

(в) `pILHeader` Указатель на первый байт IL заголовка метода.

(в) `cbILHeader` Количество байтов в заголовке IL.

## <a name="remarks"></a>Remarks  

Этот обратный вызов запускается всякий раз, когда динамический метод jIT-компилируется. Это включает в себя различные заглушки IL и методы LCG. Его цель заключается в предоставлении сценаристам-профилировщикам достаточно информации для идентификации компилированного метода для пользователей.

> [!NOTE]
> `functionId`значения не могут быть использованы для разрешения их токенов метаданных, поскольку динамические методы не имеют метаданных.

Указатель `pILHeader` действителен только во время обратного вызова.

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод DynamicMethodJITCompilationFinished](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [Интерфейс ICorProfilerCallback8](icorprofilercallback8-interface.md)
