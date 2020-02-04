---
title: 'ICorProfilerInfo10:: Рекуестрежитвисинлинерс'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.RequestReJITWithInliners
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 5822136eb1a7f582bcfae901a99775950e586198
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863183"
---
# <a name="icorprofilerinfo10requestrejitwithinliners-method"></a>Метод ICorProfilerInfo10:: Рекуестрежитвисинлинерс

Режитс запрошенные методы, а также любые запрашиваются методы.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT RequestReJITWithInliners( [in]                       DWORD       dwRejitFlags,
                                  [in]                       ULONG       cFunctions,
                                  [in, size_is(cFunctions)]  ModuleID    moduleIds[],
                                  [in, size_is(cFunctions)]  mdMethodDef methodIds[]);
```

## <a name="parameters"></a>Параметры

- `dwRejitFlags`

  \[in] битовая маска [COR_PRF_REJIT_FLAGS](cor-prf-rejit-flags-enumeration.md).

- `cFunctions`

  \[в] число функций для повторной компиляции.

- `moduleIds`

  \[в] указывает `moduleId` часть пар (`module`, `methodDef`), определяющих функции для повторной компиляции.

- `methodIds`

  \[в] указывает `methodId` часть пар (`module`, `methodDef`), определяющих функции для повторной компиляции.

## <a name="remarks"></a>Заметки

[Рекуестрежит](icorprofilerinfo4-requestrejit-method.md) не выполняет отслеживание встроенных методов. Профилировщик ожидал блокировать встраивание или отслеживание встраивания и вызов `RequestReJIT` для всех переходов, чтобы гарантировать, что каждый экземпляр встроенного метода был Режиттед. Это создает проблему с ReJIT при присоединении, так как профилировщик отсутствует для мониторинга встраивания. Этот метод может быть вызван, чтобы гарантировать, что полный набор Режиттед также будет недоступен.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).

**Заголовок:** CorProf.idl, CorProf.h

**Библиотека:** CorGuids.lib

**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerInfo10](icorprofilerinfo10-interface.md)
