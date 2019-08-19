---
title: 'ICorProfilerInfo10:: Енумератеобжектреференцес'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.EnumerateObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 4b13659f7c9909e9795caee1eace8da8092c5b9a
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974034"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a>Метод ICorProfilerInfo10:: Енумератеобжектреференцес
  
 При наличии ObjectID, callback и Клиентдата перечисляет ссылки на все объекты (если таковые имеются).   
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```  
  
#### <a name="parameters"></a>Параметры  

 `objectId` \
 окне Объект для перечисления ссылок.

 `callback` \
 окне Функция, которая будет вызываться со ссылками для объекта.

 `clientData` \
 окне Данные, предоставленные профилировщиком, передаются `callback` в функцию.
  
## <a name="remarks"></a>Примечания  
 Метод `EnumerateObjectReferences` аналогичен [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), за исключением того, что он просматривает ссылки по запросу для профилировщика вместо предварительного выделения массива для хранения ссылок.  

## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).  
  
 **Заголовок.** CorProf. idl, CorProf. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorProfilerInfo10](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

