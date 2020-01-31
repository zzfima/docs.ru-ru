---
title: ICorProfilerInfo9::GetCodeInfo4
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetCodeInfo4
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 3e3e3afc221d153ff3573126ff10014d39af761a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868308"
---
# <a name="icorprofilerinfo9getcodeinfo4-method"></a>Метод ICorProfilerInfo9:: GetCodeInfo4

При наличии начального адреса машинного кода возвращает блоки виртуальной памяти, в которых хранится этот код.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetCodeInfo4( [in]  UINT_PTR pNativeCodeStartAddress,
                      [in]  ULONG32 cCodeInfos,
                      [out] ULONG32* pcCodeInfos,
                      [out] COR_PRF_CODE_INFO codeInfos[]);
```

## <a name="parameters"></a>Параметры

- `pNativeCodeStartAddress`

  \[в] указатель на начало собственной функции.

- `cCodeInfos`

  \[в] размер массива `codeInfos`.

- `pcCodeInfos`

  \[out] указатель на общее число доступных структур [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) .

- `codeInfos`

  \[out] предоставленный вызывающим объектом буфер. После возврата метода он содержит массив структур `COR_PRF_CODE_INFO`, каждая из которых описывает блок машинного кода.

## <a name="remarks"></a>Заметки

Метод `GetCodeInfo4` аналогичен [GetCodeInfo3](icorprofilerinfo4-getcodeinfo3-method.md), за исключением того, что он может искать информацию о коде для различных версий метода.

> [!NOTE]
> `GetCodeInfo4` может активировать сборку мусора.

Расширения сортируются в порядке возрастания смещения общих промежуточного языка (CIL).

После того, как `GetCodeInfo4` возвращает, необходимо убедиться, что буфер `codeInfos` достаточно большой, чтобы вместить все [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) структуры. Для этого сравните значение параметра `cCodeInfos` со значением параметра `cchName`. Если `cCodeInfos` деленная на размер структуры [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) меньше `pcCodeInfos`, выделите больший буфер `codeInfos`, обновите `cCodeInfos` с новым, большим размером и снова вызовите `GetCodeInfo4`.

Кроме того, сначала можно вызвать метод `GetCodeInfo4` с буфером `codeInfos` нулевой длины для получения правильного размера буфера. Затем можно присвоить `codeInfos` размеру буфера значение, возвращаемое в `pcCodeInfos`, умноженное на размер [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) структуры, и снова вызвать `GetCodeInfo4`.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).

**Заголовок:** CorProf.idl, CorProf.h

**Библиотека:** CorGuids.lib

**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]

## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerInfo9](ICorProfilerInfo9-interface.md)
