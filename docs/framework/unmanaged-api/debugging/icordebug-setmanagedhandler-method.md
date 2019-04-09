---
title: Метод ICorDebug::SetManagedHandler
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88f30089879f2d023c8fb04b52e75b2942da2a83
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130173"
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="f0cfa-102">Метод ICorDebug::SetManagedHandler</span><span class="sxs-lookup"><span data-stu-id="f0cfa-102">ICorDebug::SetManagedHandler Method</span></span>
<span data-ttu-id="f0cfa-103">Указывает объект обработчика событий для управляемых событий.</span><span class="sxs-lookup"><span data-stu-id="f0cfa-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0cfa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0cfa-104">Syntax</span></span>  
  
```  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0cfa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0cfa-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="f0cfa-106">[in] Указатель на [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) объект, являющийся объект обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="f0cfa-106">[in] A pointer to an [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0cfa-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f0cfa-107">Remarks</span></span>  
 `SetManagedHandler` <span data-ttu-id="f0cfa-108">должен вызываться во время создания.</span><span class="sxs-lookup"><span data-stu-id="f0cfa-108">must be called at creation time.</span></span>  
  
 <span data-ttu-id="f0cfa-109">Если `ICorDebugManagedCallback` реализация не содержит достаточно интерфейсы для обработки событий отладки для приложения, которое выполняется отладка, `SetManagedHandler` возвращает HRESULT E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="f0cfa-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0cfa-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f0cfa-110">Requirements</span></span>  
 <span data-ttu-id="f0cfa-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0cfa-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0cfa-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0cfa-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0cfa-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0cfa-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f0cfa-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f0cfa-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f0cfa-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f0cfa-115">See also</span></span>

- [<span data-ttu-id="f0cfa-116">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="f0cfa-116">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
