---
title: 'ICorProfilerInfo10:: Суспендрунтиме'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.SuspendRuntime
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 74300a12d000565a63cd7ea862c759d47b87bbe1
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69665700"
---
# <a name="icorprofilerinfo10suspendruntime-method"></a>Метод ICorProfilerInfo10:: Суспендрунтиме

Приостанавливает выполнение среды выполнения без выполнения сборки мусора.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT SuspendRuntime();
```

## <a name="requirements"></a>Требования

**Платформ** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).

**Заголовок.** CorProf. idl, CorProf. h

**Библиотечная** Коргуидс. lib

**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo10](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
