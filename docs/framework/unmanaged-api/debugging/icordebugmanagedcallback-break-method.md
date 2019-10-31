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
ms.openlocfilehash: efc9de050e34867c14f8e85e091e2b959c30f213
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122581"
---
# <a name="icordebugmanagedcallbackbreak-method"></a><span data-ttu-id="3ed8e-102">Метод ICorDebugManagedCallback::Break</span><span class="sxs-lookup"><span data-stu-id="3ed8e-102">ICorDebugManagedCallback::Break Method</span></span>

<span data-ttu-id="3ed8e-103">Уведомляет отладчик о выполнении инструкции <xref:System.Reflection.Emit.OpCodes.Break> в потоке кода.</span><span class="sxs-lookup"><span data-stu-id="3ed8e-103">Notifies the debugger when a <xref:System.Reflection.Emit.OpCodes.Break> instruction in the code stream is executed.</span></span>

## <a name="syntax"></a><span data-ttu-id="3ed8e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3ed8e-104">Syntax</span></span>

```cpp
HRESULT Break (
    [in] ICorDebugAppDomain *pAppDomain,
    [in] ICorDebugThread    *thread
);
```

## <a name="parameters"></a><span data-ttu-id="3ed8e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3ed8e-105">Parameters</span></span>

`pAppDomain`\
<span data-ttu-id="3ed8e-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий инструкцию Break.</span><span class="sxs-lookup"><span data-stu-id="3ed8e-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the break instruction.</span></span>

`thread`\
<span data-ttu-id="3ed8e-107">окне Указатель на объект ICorDebugThread, представляющий поток, содержащий инструкцию Break.</span><span class="sxs-lookup"><span data-stu-id="3ed8e-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the break instruction.</span></span>

## <a name="requirements"></a><span data-ttu-id="3ed8e-108">Требования</span><span class="sxs-lookup"><span data-stu-id="3ed8e-108">Requirements</span></span>

<span data-ttu-id="3ed8e-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ed8e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="3ed8e-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3ed8e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="3ed8e-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ed8e-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="3ed8e-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ed8e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3ed8e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="3ed8e-113">See also</span></span>

- [<span data-ttu-id="3ed8e-114">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="3ed8e-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
