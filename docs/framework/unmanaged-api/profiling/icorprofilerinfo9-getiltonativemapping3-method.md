---
title: ICorProfilerInfo9::GetILToNativeMapping3
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetILToNativeMapping3
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 5c49d75432980d2f3af77ee040bc6eb20886b027
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861675"
---
# <a name="icorprofilerinfo9getiltonativemapping3-method"></a>Метод ICorProfilerInfo9:: GetILToNativeMapping3

С учетом начального адреса машинного кода возвращает сведения о сопоставлении IL для этой откомпилированной версии кода.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetILToNativeMapping3( [in]  UINT_PTR pNativeCodeStartAddress,
                               [in]  ULONG32 cMap,
                               [out] ULONG32 *pcMap,
                               [out] COR_DEBUG_IL_TO_NATIVE_MAP map[]);
```

## <a name="parameters"></a>Параметры

- `pNativeCodeStartAddress`

  \[в] указатель на начало собственной функции.

- `cMap`

  \[в] максимальный размер массива `map`.

- `pcMap`

  \[out] общее число доступных структур COR_DEBUG_IL_TO_NATIVE_MAP.

- `map`

  \[out] массив структур [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) , каждый из которых задает смещения. После возврата метода `GetILToNativeMapping3` параметр `map` будет содержать все или некоторые из структур `COR_DEBUG_IL_TO_NATIVE_MAP`.

## <a name="remarks"></a>Заметки

Если включена многоуровневая компиляция, метод может иметь более одного тела машинного кода. [ICorProfilerInfo9:: жетнативекодестартаддрессес](icorprofilerinfo9-getnativecodestartaddresses-method.md) будет возвращать начальные адреса для всех частей машинного кода.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).

**Заголовок:** CorProf.idl, CorProf.h

**Библиотека:** CorGuids.lib

**Версии платформы .NET Framework:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]

## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerInfo9](icorprofilerinfo9-interface.md)
