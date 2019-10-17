---
title: Метод ICorDebugCode2::GetCodeChunks
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCodeChunks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d64773aa0d35f2e97232576d145dfcba624812ec
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395528"
---
# <a name="icordebugcode2getcodechunks-method"></a>Метод ICorDebugCode2::GetCodeChunks

Возвращает фрагменты кода, из которого состоит этот объект кода.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetCodeChunks (
    [in]  ULONG32     cbufSize,
    [out] ULONG32     *pcnumChunks,
    [out, size_is(cbufSize), length_is(*pcnumChunks)]
        CodeChunkInfo chunks[]
);
```

## <a name="parameters"></a>Параметры

`cbufSize`  
окне Размер массива `chunks`.

`pcnumChunks`  
заполняет Число блоков, возвращаемых в массиве `chunks`.

`chunks`  
заполняет Массив структур "Кодечункинфо", каждый из которых представляет отдельный фрагмент кода. Если значение `cbufSize` равно 0, то этот параметр может иметь значение null.

## <a name="remarks"></a>Заметки

Фрагменты кода никогда не перекрываются, и они будут следовать порядку, в котором они были сцеплены с помощью [ICorDebugCode:: Code](icordebugcode-getcode-method.md). Объект кода на языке MSIL в .NET Framework версии 2,0 будет состоять из одного фрагмента кода.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** CorDebug.idl, CorDebug.h

**Библиотека:** CorGuids.lib

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
