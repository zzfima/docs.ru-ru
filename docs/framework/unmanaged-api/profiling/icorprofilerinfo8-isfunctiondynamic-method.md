---
title: 'ICorProfilerInfo8:: Исфунктиондинамик'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.IsFunctionDynamic
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 50b4de2de3e74a5835ee5706999892735269d4c2
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861740"
---
# <a name="icorprofilerinfo8isfunctiondynamic-method"></a>Метод ICorProfilerInfo8:: Исфунктиондинамик

Определяет, имеет ли функция связанные метаданные.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT IsFunctionDynamic( [in]  FunctionID  functionId,
                           [out] BOOL        *isDynamic);
```

## <a name="parameters"></a>Параметры

- `functionId`

  \[в] `FunctionID`, определяющий рассматриваемую функцию.

- `isDynamic`

  \[out] указатель на `BOOL`, который будет содержать значение, указывающее, имеет ли функция метаданные.

## <a name="remarks"></a>Заметки

Функция считается динамической, если она не имеет метаданных. Некоторые методы, такие как заглушки IL или методы LCG, не имеют связанных метаданных, которые можно получить с помощью API-интерфейсов интерфейса IMetaDataImport. Эти методы могут быть обнаружены профилировщиками с помощью указателей инструкций или путем прослушивания в [ICorProfilerCallback::D инамикмесоджиткомпилатионстартед](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок:** CorProf.idl, CorProf.h

**Библиотека:** CorGuids.lib

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerInfo8](icorprofilerinfo8-interface.md)
