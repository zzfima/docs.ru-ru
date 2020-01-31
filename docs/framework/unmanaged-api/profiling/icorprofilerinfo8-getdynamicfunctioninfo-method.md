---
title: 'ICorProfilerInfo8:: Жетдинамикфунктионинфо'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetDynamicFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 9b5059d9e4bf9b79dc67664c7a7971041d1cf35b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861688"
---
# <a name="icorprofilerinfo8getdynamicfunctioninfo-method"></a>Метод ICorProfilerInfo8:: Жетдинамикфунктионинфо

Извлекает сведения о динамических методах.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetDynamicFunctionInfo( [in]  FunctionID              functionId,
                                [out] ModuleID                *moduleId,
                                [out] PCCOR_SIGNATURE         *ppvSig,
                                [out] ULONG                   *pbSig,
                                [in]  ULONG                   cchName,
                                [out] ULONG                   *pcchName,
                                [out] WCHAR                   wszName[]);
```

## <a name="parameters"></a>Параметры

- `functionId`

  \[в] идентификатор функции, для которой требуется получить сведения.

- `moduleId`

  \[в] указатель на модуль, в котором определен родительский класс функции.

- `ppvSig`

  \[out] указатель на сигнатуру для функции.

- `pbSig`

  \[out] указатель на число байтов для сигнатуры функции.

- `cchName`

  \[в] максимальный размер массива `wszName`.

- `pcchName`

  \[out] число символов в массиве `wszName`.

- `wszName`

  \[out] массив `WCHAR`, который является именем функции, если таковая существует.

## <a name="remarks"></a>Заметки

Некоторые методы, такие как заглушки IL или LCG, не имеют связанных метаданных, которые можно извлечь с помощью интерфейсов API [IMetaDataImport](../metadata/imetadataimport-interface.md) и [IMetaDataImport2](../metadata/imetadataimport2-interface.md) . Такие методы могут быть обнаружены профилировщиками с помощью указателей инструкций или путем прослушивания [ICorProfilerCallback8::D инамикмесоджиткомпилатионстартед](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).

Этот API можно использовать для получения сведений о динамических методах, включая понятное имя, если оно доступно.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок:** CorProf.idl, CorProf.h

**Библиотека:** CorGuids.lib

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerInfo8](icorprofilerinfo8-interface.md)
