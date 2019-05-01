---
title: Метод ICorDebugManagedCallback::Break
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Break
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Break
helpviewer_keywords:
- Break method [.NET Framework debugging]
- ICorDebugManagedCallback::Break method [.NET Framework debugging]
ms.assetid: 7d78a301-82b3-43b2-9d65-3cda3285ae97
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bab20301c5413f8bbe95d44b87e06d3b3870c9e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988370"
---
# <a name="icordebugmanagedcallbackbreak-method"></a>Метод ICorDebugManagedCallback::Break

Уведомляет отладчик при <xref:System.Reflection.Emit.OpCodes.Break> выполнения инструкции в потоке кода.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT Break (
    [in] ICorDebugAppDomain *pAppDomain,
    [in] ICorDebugThread    *thread
);
```

## <a name="parameters"></a>Параметры

`pAppDomain`\
[in] Указатель на объект ICorDebugAppDomain, представляющий домен приложения, который содержит инструкцию break.

`thread`\
[in] Указатель на объект ICorDebugThread, представляющий поток, который содержит инструкцию break.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок.** CorDebug.idl, CorDebug.h

**Библиотека:** CorGuids.lib

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)