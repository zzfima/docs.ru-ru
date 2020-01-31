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
ms.openlocfilehash: d9efefb26ee175fa60e7cc4516ff3f8444968f31
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793225"
---
# <a name="icordebugmdagetosthreadid-method"></a><span data-ttu-id="853dc-102">Метод ICorDebugMDA::GetOSThreadId</span><span class="sxs-lookup"><span data-stu-id="853dc-102">ICorDebugMDA::GetOSThreadId Method</span></span>
<span data-ttu-id="853dc-103">Возвращает идентификатор потока операционной системы (ОС), по которому выполняется управляемый помощник по отладке (MDA), представленный [ICorDebugMDA](icordebugmda-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="853dc-103">Gets the operating system (OS) thread identifier upon which the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md) is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="853dc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="853dc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="853dc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="853dc-105">Parameters</span></span>  
 `pOsTid`  
 <span data-ttu-id="853dc-106">заполняет Указатель на идентификатор потока операционной системы.</span><span class="sxs-lookup"><span data-stu-id="853dc-106">[out] A pointer to the OS thread identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="853dc-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="853dc-107">Remarks</span></span>  
 <span data-ttu-id="853dc-108">Поток операционной системы используется вместо ICorDebugThread, чтобы разрешить ситуации, в которых MDA срабатывает либо в собственном потоке, либо в управляемом потоке, который еще не вошел в управляемый код.</span><span class="sxs-lookup"><span data-stu-id="853dc-108">The OS thread is used instead of an ICorDebugThread to allow for situations in which an MDA is fired either on a native thread or on a managed thread that has not yet entered managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="853dc-109">Требования</span><span class="sxs-lookup"><span data-stu-id="853dc-109">Requirements</span></span>  
 <span data-ttu-id="853dc-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="853dc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="853dc-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="853dc-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="853dc-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="853dc-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="853dc-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="853dc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="853dc-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="853dc-114">See also</span></span>

- [<span data-ttu-id="853dc-115">Интерфейс ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="853dc-115">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="853dc-116">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="853dc-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
