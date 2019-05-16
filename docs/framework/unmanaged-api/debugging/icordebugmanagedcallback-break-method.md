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
ms.openlocfilehash: 621c5b1e32a1a21c2b0b883249c3b65fadceb5f2
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632350"
---
# <a name="icordebugmanagedcallbackbreak-method"></a><span data-ttu-id="b6e39-102">Метод ICorDebugManagedCallback::Break</span><span class="sxs-lookup"><span data-stu-id="b6e39-102">ICorDebugManagedCallback::Break Method</span></span>

<span data-ttu-id="b6e39-103">Уведомляет отладчик при <xref:System.Reflection.Emit.OpCodes.Break> выполнения инструкции в потоке кода.</span><span class="sxs-lookup"><span data-stu-id="b6e39-103">Notifies the debugger when a <xref:System.Reflection.Emit.OpCodes.Break> instruction in the code stream is executed.</span></span>

## <a name="syntax"></a><span data-ttu-id="b6e39-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6e39-104">Syntax</span></span>

```cpp
HRESULT Break (
    [in] ICorDebugAppDomain *pAppDomain,
    [in] ICorDebugThread    *thread
);
```

## <a name="parameters"></a><span data-ttu-id="b6e39-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b6e39-105">Parameters</span></span>

`pAppDomain`\
<span data-ttu-id="b6e39-106">[in] Указатель на объект ICorDebugAppDomain, представляющий домен приложения, который содержит инструкцию break.</span><span class="sxs-lookup"><span data-stu-id="b6e39-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the break instruction.</span></span>

`thread`\
<span data-ttu-id="b6e39-107">[in] Указатель на объект ICorDebugThread, представляющий поток, который содержит инструкцию break.</span><span class="sxs-lookup"><span data-stu-id="b6e39-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the break instruction.</span></span>

## <a name="requirements"></a><span data-ttu-id="b6e39-108">Требования</span><span class="sxs-lookup"><span data-stu-id="b6e39-108">Requirements</span></span>

<span data-ttu-id="b6e39-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6e39-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="b6e39-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6e39-110">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="b6e39-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6e39-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="b6e39-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6e39-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b6e39-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b6e39-113">See also</span></span>

- [<span data-ttu-id="b6e39-114">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="b6e39-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
