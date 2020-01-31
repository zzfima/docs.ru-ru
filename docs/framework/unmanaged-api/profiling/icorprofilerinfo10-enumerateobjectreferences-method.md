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
ms.openlocfilehash: 7fd62e0d3d9173f3b75882131e57126075c0677f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863313"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a>Метод ICorProfilerInfo10:: Енумератеобжектреференцес

При наличии ObjectID, callback и Клиентдата перечисляет ссылки на все объекты (если таковые имеются).

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

## <a name="parameters"></a>Параметры

- `objectId`

  \[в] объект для перечисления ссылок.

- `callback`

  \[в] функция, которая будет вызываться со ссылками для объекта.

- `clientData`

  \[in] данные, предоставленные профилировщиком, передаются в функцию `callback`.

## <a name="remarks"></a>Заметки

Метод `EnumerateObjectReferences` аналогичен [ObjectReferences](icorprofilercallback-objectreferences-method.md), за исключением того, что он просматривает ссылки по запросу для профилировщика вместо предварительного выделения массива для хранения ссылок.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).

**Заголовок:** CorProf.idl, CorProf.h

**Библиотека:** CorGuids.lib

**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerInfo10](icorprofilerinfo10-interface.md)
