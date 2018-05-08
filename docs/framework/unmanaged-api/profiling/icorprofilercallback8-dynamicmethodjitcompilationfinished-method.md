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
ms.openlocfilehash: 49b5ead8b5428d855b7dab81dced1de6325fd07b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a>Метод ICorProfilerCallback8::DynamicMethodJITCompilationFinished
[Поддерживается в .NET Framework 4.7 и более поздних версиях]  
  
Уведомляет профилировщик, каждый раз, когда JIT-компиляции динамического метода завершения.  
  
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
Идентификатор функции в памяти, для которого JIT-компилятора началом компиляции.   

[in] `hrStatus`   
Значение, указывающее, успешно ли JIT-компиляции.

[in] `fIsSafeToBlock`   
`true` Чтобы указать, что блокировка может послужить причиной среды выполнения для ожидания вызывающего потока для возврата из этого обратного вызова; `false` для указания, что блокировка не повлияет на работу среды выполнения.  

## <a name="remarks"></a>Примечания  

Этот обратный вызов будет запускаться при каждом завершении JIT-компиляции динамического метода. Сюда входят различные заглушки IL и LCG методы. Ее целью является предоставление модулей записи профилировщик с достаточно информации для идентификации метода, скомпилированного для пользователей.

> [!NOTE]
> `functionId` значения не может использоваться для разрешения на их лексемы метаданных, поскольку динамические методы имеют без метаданных.

## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>См. также  
 [Метод DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)  
 [Интерфейс ICorProfilerCallback8](icorprofilercallback8-interface.md)
