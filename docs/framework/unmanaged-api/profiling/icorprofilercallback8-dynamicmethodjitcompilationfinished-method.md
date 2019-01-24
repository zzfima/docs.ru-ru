---
title: Метод ICorProfilerCallback8::DynamicMethodJITCompilationFinished
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: addaf6333914c9f0ea36d67e3eb96577fef79e1e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54497922"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a>Метод ICorProfilerCallback8::DynamicMethodJITCompilationFinished
[Поддерживается в .NET Framework 4.7 и более поздних версиях]  
  
Уведомляет профилировщик, каждый раз, когда JIT-компиляция динамического метода завершения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        hrStatus,   
     [in]  BOOL        fIsSafeToBlock   
);  
```  
  
#### <a name="parameters"></a>Параметры  
[in] `functionId`  
Идентификатор функции в памяти, для которого JIT-компиляции запускается.   

[in] `hrStatus`   
Значение, указывающее, успешно ли JIT-компиляции.

[in] `fIsSafeToBlock`   
`true` Чтобы указать, что блокировок может вызвать среды выполнения для вызывающего потока для возврата из этого обратного вызова; `false` для указания, что блокировка не повлияет на работу среды выполнения.  

## <a name="remarks"></a>Примечания  

Этот обратный вызов активируется каждый раз, когда JIT-компиляция динамического метода завершения. Сюда входят различные заглушки IL и LCG методы. Его целью является предоставление модулей записи профилировщика достаточно информации для идентификации метода, скомпилированного для пользователей.

> [!NOTE]
> `functionId` значения не может использоваться для разрешения на их токены метаданных, так как динамические методы имеют без метаданных.

## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>См. также
- [Метод DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [Интерфейс ICorProfilerCallback8](icorprofilercallback8-interface.md)
