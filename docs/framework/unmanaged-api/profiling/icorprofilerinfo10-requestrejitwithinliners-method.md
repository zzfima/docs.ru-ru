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
ms.openlocfilehash: 00bfc9fc21ed39226fd21c4096305c254d73ee11
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69665723"
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

#### <a name="parameters"></a>Параметры

`dwRejitFlags` \
окне Битовая маска [COR_PRF_REJIT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-rejit-flags-enumeration.md).

`cFunctions` \
[in] Число функций для перекомпиляции.

`moduleIds` \
[in] Указывает часть `moduleId` пар (`module`, `methodDef`), которые идентифицируют перекомпилируемые функции.

`methodIds` \
[in] Указывает часть `methodId` пар (`module`, `methodDef`), которые идентифицируют перекомпилируемые функции.

## <a name="remarks"></a>Примечания

[Рекуестрежит](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md) не выполняет отслеживание встроенных методов. Профилировщик ожидал блокировать встраивание или отслеживание встраивания, а также вызов `RequestReJIT` всех строк, чтобы гарантировать, что каждый экземпляр встроенного метода был режиттед. Это создает проблему с ReJIT при присоединении, так как профилировщик отсутствует для мониторинга встраивания. Этот метод может быть вызван, чтобы гарантировать, что полный набор Режиттед также будет недоступен.

## <a name="requirements"></a>Требования

**Платформ** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).

**Заголовок.** CorProf. idl, CorProf. h

**Библиотечная** Коргуидс. lib

**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo10](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
