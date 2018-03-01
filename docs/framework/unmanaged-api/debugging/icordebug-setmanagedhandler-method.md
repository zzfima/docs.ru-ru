---
title: "Метод ICorDebug::SetManagedHandler"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebug.SetManagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetManagedHandler
helpviewer_keywords:
- ICorDebug::SetManagedHandler method [.NET Framework debugging]
- SetManagedHandler method [.NET Framework debugging]
ms.assetid: d079131b-685b-4869-95be-826b88d28bd2
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dde32b6a8251474c4254e35a3a1ba3ba3bafcb8f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="5ce7b-102">Метод ICorDebug::SetManagedHandler</span><span class="sxs-lookup"><span data-stu-id="5ce7b-102">ICorDebug::SetManagedHandler Method</span></span>
<span data-ttu-id="5ce7b-103">Указывает объект обработчика событий для управляемых событий.</span><span class="sxs-lookup"><span data-stu-id="5ce7b-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ce7b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5ce7b-104">Syntax</span></span>  
  
```  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5ce7b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5ce7b-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="5ce7b-106">[in] Указатель на [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) объект, представляющий объект обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="5ce7b-106">[in] A pointer to an [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ce7b-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="5ce7b-107">Remarks</span></span>  
 <span data-ttu-id="5ce7b-108">`SetManagedHandler`должен быть вызван во время создания.</span><span class="sxs-lookup"><span data-stu-id="5ce7b-108">`SetManagedHandler` must be called at creation time.</span></span>  
  
 <span data-ttu-id="5ce7b-109">Если `ICorDebugManagedCallback` реализация не содержит достаточно интерфейсы для обработки событий отладки для приложения, которое выполняется отладка, `SetManagedHandler` возвращает HRESULT E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="5ce7b-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ce7b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="5ce7b-110">Requirements</span></span>  
 <span data-ttu-id="5ce7b-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ce7b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ce7b-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ce7b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ce7b-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ce7b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ce7b-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ce7b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ce7b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="5ce7b-115">See Also</span></span>  
 [<span data-ttu-id="5ce7b-116">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="5ce7b-116">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
