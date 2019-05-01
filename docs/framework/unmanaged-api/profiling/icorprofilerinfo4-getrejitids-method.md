---
title: Метод ICorProfilerInfo4::GetReJITIDs
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetReJITIDs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetReJITIDs
helpviewer_keywords:
- GetReJITIDs method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetReJITIDs method [.NET Framework profiling]
ms.assetid: 634ac28c-a5b7-4fc3-af84-256c24ca8177
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d2d48e5fb070ec0334de579d2e28146177a87b1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049483"
---
# <a name="icorprofilerinfo4getrejitids-method"></a>Метод ICorProfilerInfo4::GetReJITIDs
Возвращает массив идентификаторов, определяющих все перекомпиляции JIT версии указанной функции, по-прежнему выделяются. Сюда входят перекомпиляции JIT версии функций, которые впоследствии отменены, но еще не освобождены (например, когда домен приложения, содержащей функцию, возвращенного в предыдущее состояние по-прежнему используется).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a>Параметры  
 `functionId`  
 [in] `FunctionID` Экземпляра функции для перечисления версий.  
  
 `cReJitIds`  
 [in] Количество идентификаторов перекомпиляции JIT, выделенных в `reJitIds` массива.  
  
 `pcReJitIds`  
 [out] Фактическое число идентификаторов перекомпиляции JIT.  
  
 `reJitIds`  
 [out] Выделенный вызывающим объектом массив, который будет содержать идентификаторы перекомпиляции JIT для указанной функции.  
  
## <a name="remarks"></a>Примечания  
 `GetReJITIDs` перечисляет идентификаторы active перекомпиляции JIT для заданной функции экземпляра. Он используется та же схема использования как другой `ICorProfilerInfo` функции, принимающие буферы, выделенные вызывающим объектом.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Профилирование](../../../../docs/framework/unmanaged-api/profiling/index.md)
