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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd899422287d34407778f67e5b4dfd2f33ffd00c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994829"
---
# <a name="icordebugmodule2resolveassembly-method"></a>Метод ICorDebugModule2::ResolveAssembly

Разрешает сборки, упоминаемой в заданным токеном метаданных.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT ResolveAssembly (
    [in]  mdToken             tkAssemblyRef,
    [out] ICorDebugAssembly   **ppAssembly
);
```

## <a name="parameters"></a>Параметры

`tkAssemblyRef`\
[in] `mdToken` Значение, которое ссылается на сборку.

`ppAssembly`\
[out] Указатель на адрес объекта ICorDebugAssembly, представляющий сборку.

## <a name="remarks"></a>Примечания

Если сборка еще не загружен при `ResolveAssembly` вызывается HRESULT возвращается значение CORDBG_E_CANNOT_RESOLVE_ASSEMBLY.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок.** CorDebug.idl, CorDebug.h

**Библиотека:** CorGuids.lib

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
