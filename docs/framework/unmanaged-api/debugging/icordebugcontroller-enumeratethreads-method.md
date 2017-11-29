---
title: "Метод ICorDebugController::EnumerateThreads"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.EnumerateThreads
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::EnumerateThreads
helpviewer_keywords:
- ICorDebugController::EnumerateThreads method [.NET Framework debugging]
- EnumerateThreads method [.NET Framework debugging]
ms.assetid: 73f536f6-4668-4a4a-b3e4-ac7df862d5be
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b7575bf2b50f11fab1c14f8fb28dc65e079c21de
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="471f3-102">Метод ICorDebugController::EnumerateThreads</span><span class="sxs-lookup"><span data-stu-id="471f3-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="471f3-103">Возвращает перечислитель для активных управляемых потоков в процессе.</span><span class="sxs-lookup"><span data-stu-id="471f3-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="471f3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="471f3-104">Syntax</span></span>  
  
```  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="471f3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="471f3-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="471f3-106">[out] Указатель на адрес объекта «ICorDebugThreadEnum», который представляет перечислитель для всех управляемых потоков, которые активны в процессе.</span><span class="sxs-lookup"><span data-stu-id="471f3-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="471f3-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="471f3-107">Remarks</span></span>  
 <span data-ttu-id="471f3-108">Поток считается активным после [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) было отправлено обратного вызова и перед [ICorDebugManagedCallback::ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) было отправлено обратного вызова .</span><span class="sxs-lookup"><span data-stu-id="471f3-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="471f3-109">Управляемый поток может не обязательно управляемые фреймы в стеке.</span><span class="sxs-lookup"><span data-stu-id="471f3-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="471f3-110">Потоки могут быть перечислены до [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="471f3-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="471f3-111">Перечисление естественным образом будет пустым.</span><span class="sxs-lookup"><span data-stu-id="471f3-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="471f3-112">Требования</span><span class="sxs-lookup"><span data-stu-id="471f3-112">Requirements</span></span>  
 <span data-ttu-id="471f3-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="471f3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="471f3-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="471f3-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="471f3-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="471f3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="471f3-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="471f3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="471f3-117">См. также</span><span class="sxs-lookup"><span data-stu-id="471f3-117">See Also</span></span>  
 
