---
title: Метод ICorDebugController::Terminate
ms.date: 03/30/2017
api_name:
- ICorDebugController.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Terminate
helpviewer_keywords:
- Terminate method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Terminate method [.NET Framework debugging]
ms.assetid: 4275af0c-b5a7-4e4c-97c9-7e41f36b2dd8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4c8dd8795fc3699176490ea0bb9b2e999038afb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124882"
---
# <a name="icordebugcontrollerterminate-method"></a><span data-ttu-id="eeabe-102">Метод ICorDebugController::Terminate</span><span class="sxs-lookup"><span data-stu-id="eeabe-102">ICorDebugController::Terminate Method</span></span>
<span data-ttu-id="eeabe-103">Завершает процесс с помощью указанного кода выхода.</span><span class="sxs-lookup"><span data-stu-id="eeabe-103">Terminates the process with the specified exit code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eeabe-104">Этот метод является оболочкой для Win32 `TerminateProcess` функции.</span><span class="sxs-lookup"><span data-stu-id="eeabe-104">This method is a wrapper for the Win32 `TerminateProcess` function.</span></span> <span data-ttu-id="eeabe-105">Таким образом `Terminate` использует код выхода в том же образом, как Win32 `TerminateProcess` функция использует его.</span><span class="sxs-lookup"><span data-stu-id="eeabe-105">Thus, `Terminate` uses the exit code in the same way that the Win32 `TerminateProcess` function uses it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eeabe-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eeabe-106">Syntax</span></span>  
  
```  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eeabe-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="eeabe-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="eeabe-108">[in] Числовое значение, — это код выхода.</span><span class="sxs-lookup"><span data-stu-id="eeabe-108">[in] A numeric value that is the exit code.</span></span> <span data-ttu-id="eeabe-109">Допустимые числовые значения определяются в Winbase.h.</span><span class="sxs-lookup"><span data-stu-id="eeabe-109">The valid numeric values are defined in Winbase.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eeabe-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="eeabe-110">Remarks</span></span>  
 <span data-ttu-id="eeabe-111">Если процесс останавливается, когда `Terminate` является именем, процесс должен быть продолжено с помощью [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) метод таким образом, чтобы отладчик получает подтверждение о завершении через [ ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) или [ICorDebugManagedCallback::ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="eeabe-111">If the process is stopped when `Terminate` is called, the process should be continued by using the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method so that the debugger receives confirmation of the termination through the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) or [ICorDebugManagedCallback::ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) callback.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eeabe-112">Этот метод не реализован доменом приложения.</span><span class="sxs-lookup"><span data-stu-id="eeabe-112">This method is not implemented by an application domain.</span></span> <span data-ttu-id="eeabe-113">То есть оно не реализовано на <xref:System.AppDomain> уровень.</span><span class="sxs-lookup"><span data-stu-id="eeabe-113">That is, it is not implemented at the <xref:System.AppDomain> level.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eeabe-114">Требования</span><span class="sxs-lookup"><span data-stu-id="eeabe-114">Requirements</span></span>  
 <span data-ttu-id="eeabe-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eeabe-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eeabe-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eeabe-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eeabe-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eeabe-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="eeabe-118">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="eeabe-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="eeabe-119">См. также</span><span class="sxs-lookup"><span data-stu-id="eeabe-119">See also</span></span>
