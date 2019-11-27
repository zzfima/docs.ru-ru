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
ms.openlocfilehash: f6d26abba649b608858fde8beaac750600493869
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442865"
---
# <a name="icorprofilerinfo4getrejitids-method"></a>Метод ICorProfilerInfo4::GetReJITIDs
Возвращает массив идентификаторов, которые определяют все все повторно скомпилированные версии указанной функции, которые все еще выделены. Сюда входят JIT-повторно скомпилированные версии функций, которые впоследствии были отменены, но еще не освобождены (например, если домен приложения, содержащий функцию, которая содержит возвращенные функции, все еще используется).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a>Параметры  
 `functionId`  
 окне `FunctionID` экземпляра функции, для которой перечисляются версии.  
  
 `cReJitIds`  
 окне Число идентификаторов с JIT-рекомпиляцией, выделенных в массиве `reJitIds`.  
  
 `pcReJitIds`  
 заполняет Фактическое число повторно скомпилированных идентификаторов с JIT-рекомпиляцией.  
  
 `reJitIds`  
 заполняет Выделенный вызывающим объектом массив, который будет содержать JIT-перекомпилированные идентификаторы для указанной функции.  
  
## <a name="remarks"></a>Примечания  
 `GetReJITIDs` перечисляет активные JIT-повторно скомпилированные идентификаторы для данного экземпляра функции. Она соответствует той же схеме использования, что и другие функции `ICorProfilerInfo`, принимающие буферы, выделенные вызывающим объектом.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Профилирование](../../../../docs/framework/unmanaged-api/profiling/index.md)
