---
title: "Метод ICorDebugController::Terminate"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.Terminate
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::Terminate
helpviewer_keywords:
- Terminate method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Terminate method [.NET Framework debugging]
ms.assetid: 4275af0c-b5a7-4e4c-97c9-7e41f36b2dd8
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fb3831e2640de8ad34299695b571cb4071974bd6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontrollerterminate-method"></a><span data-ttu-id="e942a-102">Метод ICorDebugController::Terminate</span><span class="sxs-lookup"><span data-stu-id="e942a-102">ICorDebugController::Terminate Method</span></span>
<span data-ttu-id="e942a-103">Завершает процесс с помощью указанного кода выхода.</span><span class="sxs-lookup"><span data-stu-id="e942a-103">Terminates the process with the specified exit code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e942a-104">Этот метод является оболочкой для функции Win32 `TerminateProcess` функции.</span><span class="sxs-lookup"><span data-stu-id="e942a-104">This method is a wrapper for the Win32 `TerminateProcess` function.</span></span> <span data-ttu-id="e942a-105">Таким образом `Terminate` использует код выхода так же, как Win32 `TerminateProcess` функция использует его.</span><span class="sxs-lookup"><span data-stu-id="e942a-105">Thus, `Terminate` uses the exit code in the same way that the Win32 `TerminateProcess` function uses it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e942a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e942a-106">Syntax</span></span>  
  
```  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e942a-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="e942a-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="e942a-108">[in] Числовое значение, — это код выхода.</span><span class="sxs-lookup"><span data-stu-id="e942a-108">[in] A numeric value that is the exit code.</span></span> <span data-ttu-id="e942a-109">Допустимые числовые значения задаются в заголовке Winbase.h.</span><span class="sxs-lookup"><span data-stu-id="e942a-109">The valid numeric values are defined in Winbase.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e942a-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="e942a-110">Remarks</span></span>  
 <span data-ttu-id="e942a-111">Если процесс остановлен `Terminate` — вызывается, процесс должен быть продолжен с помощью [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) метод, чтобы отладчик получит подтверждение о завершении через [ ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) или [ICorDebugManagedCallback::ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="e942a-111">If the process is stopped when `Terminate` is called, the process should be continued by using the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method so that the debugger receives confirmation of the termination through the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) or [ICorDebugManagedCallback::ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) callback.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e942a-112">Этот метод не реализуется доменом приложения.</span><span class="sxs-lookup"><span data-stu-id="e942a-112">This method is not implemented by an application domain.</span></span> <span data-ttu-id="e942a-113">То есть оно не реализовано на <xref:System.AppDomain> уровне.</span><span class="sxs-lookup"><span data-stu-id="e942a-113">That is, it is not implemented at the <xref:System.AppDomain> level.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e942a-114">Требования</span><span class="sxs-lookup"><span data-stu-id="e942a-114">Requirements</span></span>  
 <span data-ttu-id="e942a-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e942a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e942a-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e942a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e942a-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e942a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e942a-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e942a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e942a-119">См. также</span><span class="sxs-lookup"><span data-stu-id="e942a-119">See Also</span></span>  
 
