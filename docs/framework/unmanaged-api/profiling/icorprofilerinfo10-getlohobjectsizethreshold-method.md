---
title: 'ICorProfilerInfo10:: Жетлохобжектсизесрешолд'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.GetLOHObjectSizeThreshold
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 95473a8ce8d5fd7540228ecd9767448e51b5b326
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868988"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a>Метод ICorProfilerInfo10:: Жетлохобжектсизесрешолд

Возвращает значение заданного порога кучи больших объектов (LOH).

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

## <a name="parameters"></a>Параметры

- `pThreshold`

  \[out] пороговое значение кучи больших объектов в байтах.

## <a name="remarks"></a>Заметки

Объекты, превышающие пороговое значение кучи больших объектов, будут выделены в куче больших объектов. Начиная с .NET Core 3,0, порог кучи больших объектов можно настроить, `pThreshold` будет содержать пороговое значение активной кучи больших объектов в байтах.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).

**Заголовок:** CorProf.idl, CorProf.h

**Библиотека:** CorGuids.lib

**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerInfo10](icorprofilerinfo10-interface.md)
