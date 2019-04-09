---
title: Метод ICorDebugMDA::GetOSThreadId
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetOSThreadId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetOSThreadId
helpviewer_keywords:
- ICorDebugMDA::GetOSThreadId method [.NET Framework debugging]
- GetOSThreadId method [.NET Framework debugging]
ms.assetid: 7ca7c364-ade4-4219-b434-9f6ae2359be6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51d29fed3d53611daa0042251ce09638399f7ed5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195804"
---
# <a name="icordebugmdagetosthreadid-method"></a><span data-ttu-id="7ae2f-102">Метод ICorDebugMDA::GetOSThreadId</span><span class="sxs-lookup"><span data-stu-id="7ae2f-102">ICorDebugMDA::GetOSThreadId Method</span></span>
<span data-ttu-id="7ae2f-103">Получает идентификатор потока операционной системы (ОС), на котором помощник по отладке управляемого (кода MDA), представленного [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) выполняется.</span><span class="sxs-lookup"><span data-stu-id="7ae2f-103">Gets the operating system (OS) thread identifier upon which the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ae2f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ae2f-104">Syntax</span></span>  
  
```  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ae2f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7ae2f-105">Parameters</span></span>  
 `pOsTid`  
 <span data-ttu-id="7ae2f-106">[out] Указатель на идентификатор потока операционной системы.</span><span class="sxs-lookup"><span data-stu-id="7ae2f-106">[out] A pointer to the OS thread identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ae2f-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="7ae2f-107">Remarks</span></span>  
 <span data-ttu-id="7ae2f-108">Поток операционной системы используется вместо ICorDebugThread, чтобы допускать ситуации, в которых MDA вызывается в собственном потоке или в управляемом потоке, который еще не вошел в управляемый код.</span><span class="sxs-lookup"><span data-stu-id="7ae2f-108">The OS thread is used instead of an ICorDebugThread to allow for situations in which an MDA is fired either on a native thread or on a managed thread that has not yet entered managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ae2f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7ae2f-109">Requirements</span></span>  
 <span data-ttu-id="7ae2f-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ae2f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ae2f-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ae2f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ae2f-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ae2f-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7ae2f-113">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="7ae2f-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7ae2f-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7ae2f-114">See also</span></span>

- [<span data-ttu-id="7ae2f-115">Интерфейс ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="7ae2f-115">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="7ae2f-116">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="7ae2f-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
