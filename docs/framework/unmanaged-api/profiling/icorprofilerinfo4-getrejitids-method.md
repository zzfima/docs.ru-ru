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
ms.openlocfilehash: 1055366576f45a7ca137b6d8170d1786c2ba4492
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo4getrejitids-method"></a>Метод ICorProfilerInfo4::GetReJITIDs
Возвращает массив идентификаторов, определяющих все JIT-компилятора версии указанной функции, по-прежнему выделяются. Это включает JIT-компилятора версии функций, которые впоследствии восстановить, но еще не освобождены (например, когда домен приложения, содержащей функцию, возвращенного в предыдущее состояние до сих пор используется).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 `functionId`  
 [in] `FunctionID` Экземпляра функции для перечисления версий.  
  
 `cReJitIds`  
 [in] Число идентификаторов JIT-компилятора, выделенных в `reJitIds` массива.  
  
 `pcReJitIds`  
 [out] Фактическое количество идентификаторов с помощью JIT-компилятора.  
  
 `reJitIds`  
 [out] Выделенный вызывающим объектом массив, который будет содержать идентификаторы JIT-компилятора для указанной функции.  
  
## <a name="remarks"></a>Примечания  
 `GetReJITIDs` перечисляет идентификаторы active JIT-компилятора для экземпляра указанной функции. Его после использования шаблона, аналогичного других `ICorProfilerInfo` функций, принимающих буферы, выделенные вызывающим объектом.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Профилирование](../../../../docs/framework/unmanaged-api/profiling/index.md)
