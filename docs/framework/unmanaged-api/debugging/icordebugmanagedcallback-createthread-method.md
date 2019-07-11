---
title: Метод ICorDebugManagedCallback::CreateThread
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateThread method
helpviewer_keywords:
- ICorDebugManagedCallback::CreateThread method [.NET Framework debugging]
- CreateThread method [.NET Framework debugging]
ms.assetid: 6b961728-21c4-4e8d-ae81-197458be62f4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2192b5d3b240211c8982eab7539896ea3626a072
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759680"
---
# <a name="icordebugmanagedcallbackcreatethread-method"></a><span data-ttu-id="185f4-102">Метод ICorDebugManagedCallback::CreateThread</span><span class="sxs-lookup"><span data-stu-id="185f4-102">ICorDebugManagedCallback::CreateThread Method</span></span>
<span data-ttu-id="185f4-103">Уведомляет отладчик о том, что поток начал выполнение управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="185f4-103">Notifies the debugger that a thread has started executing managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="185f4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="185f4-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="185f4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="185f4-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="185f4-106">[in] Указатель на объект ICorDebugAppDomain, представляющий домен приложения, который содержит поток.</span><span class="sxs-lookup"><span data-stu-id="185f4-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="185f4-107">[in] Указатель на объект ICorDebugThread, представляющий поток.</span><span class="sxs-lookup"><span data-stu-id="185f4-107">[in] A pointer to an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="185f4-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="185f4-108">Remarks</span></span>  
 <span data-ttu-id="185f4-109">Поток будет расположен в первой инструкции для выполнения управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="185f4-109">The thread will be positioned at the first managed code instruction to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="185f4-110">Требования</span><span class="sxs-lookup"><span data-stu-id="185f4-110">Requirements</span></span>  
 <span data-ttu-id="185f4-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="185f4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="185f4-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="185f4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="185f4-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="185f4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="185f4-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="185f4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="185f4-115">См. также</span><span class="sxs-lookup"><span data-stu-id="185f4-115">See also</span></span>

- [<span data-ttu-id="185f4-116">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="185f4-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
