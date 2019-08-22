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
ms.openlocfilehash: e6708971909c1035e41786f4d8dad1cf9afdffaf
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69665619"
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

#### <a name="parameters"></a>Параметры

`pNativeCodeStartAddress` \
окне Указатель на начало собственной функции.

`cCodeInfos` \
[in] Размер массива `codeInfos`.

`pcCodeInfos` \
заполняет Указатель на общее число доступных структур [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) .

`codeInfos` \
[out] Буфер, предоставляемый вызывающим объектом. После возврата метода он содержит массив структур `COR_PRF_CODE_INFO`, каждая из которых описывает блок машинного кода.

## <a name="remarks"></a>Примечания

Метод `GetCodeInfo4` аналогичен [GetCodeInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md), за исключением того, что он может искать информацию о коде для различных версий метода.

> [!NOTE]
> `GetCodeInfo4`может запустить сборку мусора.

Расширения сортируются в порядке возрастания смещения общих промежуточного языка (CIL).

После `GetCodeInfo4` возврата необходимо убедиться `codeInfos` , что буфер достаточно велик, чтобы вместить все структуры [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) . Для этого сравните значение параметра `cCodeInfos` со значением параметра `cchName`. При `cCodeInfos` делении на размер `pcCodeInfos`структуры [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) меньше, выделяет буфер большего `codeInfos` размера, обновляет `cCodeInfos` новый, больший размер и вызывается `GetCodeInfo4` снова.

Кроме того, сначала можно вызвать метод `GetCodeInfo4` с буфером `codeInfos` нулевой длины для получения правильного размера буфера. Затем можно `codeInfos` задать размер буфера равным значению, возвращенному `pcCodeInfos`в, умноженному на размер структуры [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) и вызывать `GetCodeInfo4` повторно.

## <a name="requirements"></a>Требования

**Платформ** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).

**Заголовок.** CorProf. idl, CorProf. h

**Библиотечная** Коргуидс. lib

**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/ICorProfilerInfo9-interface.md)
