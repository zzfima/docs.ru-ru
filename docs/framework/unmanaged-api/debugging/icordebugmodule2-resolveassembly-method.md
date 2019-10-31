---
title: Метод ICorDebugModule2::ResolveAssembly
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.ResolveAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ResolveAssembly
helpviewer_keywords:
- ICorDebugModule2::ResolveAssembly method [.NET Framework debugging]
- ResolveAssembly method [.NET Framework debugging]
ms.assetid: ddf9085c-7161-44bd-9609-cd2732b9009f
topic_type:
- apiref
ms.openlocfilehash: 0809a149a5a5a5e9adea059140d7b4b456337ef3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125303"
---
# <a name="icordebugmodule2resolveassembly-method"></a>Метод ICorDebugModule2::ResolveAssembly

Разрешает сборку, на которую ссылается указанный токен метаданных.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT ResolveAssembly (
    [in]  mdToken             tkAssemblyRef,
    [out] ICorDebugAssembly   **ppAssembly
);
```

## <a name="parameters"></a>Параметры

`tkAssemblyRef`\
окне Значение `mdToken`, которое ссылается на сборку.

`ppAssembly`\
заполняет Указатель на адрес объекта ICorDebugAssembly, который представляет сборку.

## <a name="remarks"></a>Заметки

Если сборка еще не загружена при вызове `ResolveAssembly`, возвращается значение HRESULT CORDBG_E_CANNOT_RESOLVE_ASSEMBLY.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок:** CorDebug.idl, CorDebug.h

**Библиотека:** CorGuids.lib

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
