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
ms.openlocfilehash: 7a38ee4ae74ca5b96dd082e752fc733eb85fca3f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427024"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a>Метод ICorProfilerInfo10:: Жетлохобжектсизесрешолд

Возвращает значение заданного порога кучи больших объектов (LOH).

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

#### <a name="parameters"></a>Параметры

`pThreshold` \
заполняет Пороговое значение кучи больших объектов в байтах.

## <a name="remarks"></a>Заметки

Объекты, превышающие пороговое значение кучи больших объектов, будут выделены в куче больших объектов. Начиная с .NET Core 3,0, порог кучи больших объектов можно настроить, `pThreshold` будет содержать пороговое значение активной кучи больших объектов в байтах.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).

**Заголовок:** CorProf.idl, CorProf.h

**Библиотека:** CorGuids.lib

**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo10](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
