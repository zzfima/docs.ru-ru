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
ms.openlocfilehash: ee1c30809567097e67b6b1e40f5534429d748abd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964371"
---
# <a name="icordebugcontrollerterminate-method"></a><span data-ttu-id="44e09-102">Метод ICorDebugController::Terminate</span><span class="sxs-lookup"><span data-stu-id="44e09-102">ICorDebugController::Terminate Method</span></span>
<span data-ttu-id="44e09-103">Завершает процесс с указанным кодом выхода.</span><span class="sxs-lookup"><span data-stu-id="44e09-103">Terminates the process with the specified exit code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="44e09-104">Этот метод является оболочкой для функции Win32 `TerminateProcess` .</span><span class="sxs-lookup"><span data-stu-id="44e09-104">This method is a wrapper for the Win32 `TerminateProcess` function.</span></span> <span data-ttu-id="44e09-105">Таким образом `Terminate` , использует код выхода точно так же, как функция Win32 `TerminateProcess` использует ее.</span><span class="sxs-lookup"><span data-stu-id="44e09-105">Thus, `Terminate` uses the exit code in the same way that the Win32 `TerminateProcess` function uses it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44e09-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="44e09-106">Syntax</span></span>  
  
```cpp  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44e09-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="44e09-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="44e09-108">окне Числовое значение, которое является кодом выхода.</span><span class="sxs-lookup"><span data-stu-id="44e09-108">[in] A numeric value that is the exit code.</span></span> <span data-ttu-id="44e09-109">Допустимые числовые значения определяются в Винбасе. h.</span><span class="sxs-lookup"><span data-stu-id="44e09-109">The valid numeric values are defined in Winbase.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44e09-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="44e09-110">Remarks</span></span>  
 <span data-ttu-id="44e09-111">Если процесс останавливается при `Terminate` вызове, процесс должен быть продолжен с помощью метода [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) , чтобы отладчик получал подтверждение завершения с помощью [ICorDebugManagedCallback:: ](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)Обратный вызов ExitProcess или [ICorDebugManagedCallback:: ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) .</span><span class="sxs-lookup"><span data-stu-id="44e09-111">If the process is stopped when `Terminate` is called, the process should be continued by using the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method so that the debugger receives confirmation of the termination through the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) or [ICorDebugManagedCallback::ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) callback.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="44e09-112">Этот метод не реализуется доменом приложения.</span><span class="sxs-lookup"><span data-stu-id="44e09-112">This method is not implemented by an application domain.</span></span> <span data-ttu-id="44e09-113">Это значит, что он не реализован на <xref:System.AppDomain> уровне.</span><span class="sxs-lookup"><span data-stu-id="44e09-113">That is, it is not implemented at the <xref:System.AppDomain> level.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44e09-114">Требования</span><span class="sxs-lookup"><span data-stu-id="44e09-114">Requirements</span></span>  
 <span data-ttu-id="44e09-115">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44e09-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44e09-116">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="44e09-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44e09-117">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="44e09-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44e09-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44e09-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44e09-119">См. также</span><span class="sxs-lookup"><span data-stu-id="44e09-119">See also</span></span>
