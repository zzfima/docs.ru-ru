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
ms.openlocfilehash: fb8cfb2d1c5902ecd0d5858ef21ba48b65b12506
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125335"
---
# <a name="icordebugcontrollerterminate-method"></a><span data-ttu-id="9155b-102">Метод ICorDebugController::Terminate</span><span class="sxs-lookup"><span data-stu-id="9155b-102">ICorDebugController::Terminate Method</span></span>
<span data-ttu-id="9155b-103">Завершает процесс с указанным кодом выхода.</span><span class="sxs-lookup"><span data-stu-id="9155b-103">Terminates the process with the specified exit code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9155b-104">Этот метод является оболочкой для функции Win32 `TerminateProcess`.</span><span class="sxs-lookup"><span data-stu-id="9155b-104">This method is a wrapper for the Win32 `TerminateProcess` function.</span></span> <span data-ttu-id="9155b-105">Таким образом, `Terminate` использует код выхода так же, как функция `TerminateProcess` Win32 использует ее.</span><span class="sxs-lookup"><span data-stu-id="9155b-105">Thus, `Terminate` uses the exit code in the same way that the Win32 `TerminateProcess` function uses it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9155b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9155b-106">Syntax</span></span>  
  
```cpp  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9155b-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="9155b-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="9155b-108">окне Числовое значение, которое является кодом выхода.</span><span class="sxs-lookup"><span data-stu-id="9155b-108">[in] A numeric value that is the exit code.</span></span> <span data-ttu-id="9155b-109">Допустимые числовые значения определяются в Винбасе. h.</span><span class="sxs-lookup"><span data-stu-id="9155b-109">The valid numeric values are defined in Winbase.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9155b-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="9155b-110">Remarks</span></span>  
 <span data-ttu-id="9155b-111">Если процесс останавливается при вызове `Terminate`, процесс должен быть продолжен с помощью метода [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) , чтобы отладчик получал подтверждение завершения работы через [ICorDebugManagedCallback:: ](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)Обратный вызов ExitProcess или [ICorDebugManagedCallback:: ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9155b-111">If the process is stopped when `Terminate` is called, the process should be continued by using the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method so that the debugger receives confirmation of the termination through the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) or [ICorDebugManagedCallback::ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) callback.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9155b-112">Этот метод не реализуется доменом приложения.</span><span class="sxs-lookup"><span data-stu-id="9155b-112">This method is not implemented by an application domain.</span></span> <span data-ttu-id="9155b-113">Это значит, что он не реализован на уровне <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="9155b-113">That is, it is not implemented at the <xref:System.AppDomain> level.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9155b-114">Требования</span><span class="sxs-lookup"><span data-stu-id="9155b-114">Requirements</span></span>  
 <span data-ttu-id="9155b-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9155b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9155b-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9155b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9155b-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9155b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9155b-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9155b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9155b-119">См. также</span><span class="sxs-lookup"><span data-stu-id="9155b-119">See also</span></span>
