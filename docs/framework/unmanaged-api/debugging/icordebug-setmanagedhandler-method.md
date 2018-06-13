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
ms.openlocfilehash: bcf97f9fffabb9ae9579016517cfc335e6f783a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404577"
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="a30f3-102">Метод ICorDebug::SetManagedHandler</span><span class="sxs-lookup"><span data-stu-id="a30f3-102">ICorDebug::SetManagedHandler Method</span></span>
<span data-ttu-id="a30f3-103">Указывает объект обработчика событий для управляемых событий.</span><span class="sxs-lookup"><span data-stu-id="a30f3-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a30f3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a30f3-104">Syntax</span></span>  
  
```  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a30f3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a30f3-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="a30f3-106">[in] Указатель на [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) объект, представляющий объект обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="a30f3-106">[in] A pointer to an [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a30f3-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="a30f3-107">Remarks</span></span>  
 <span data-ttu-id="a30f3-108">`SetManagedHandler` должен быть вызван во время создания.</span><span class="sxs-lookup"><span data-stu-id="a30f3-108">`SetManagedHandler` must be called at creation time.</span></span>  
  
 <span data-ttu-id="a30f3-109">Если `ICorDebugManagedCallback` реализация не содержит достаточно интерфейсы для обработки событий отладки для приложения, которое выполняется отладка, `SetManagedHandler` возвращает HRESULT E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="a30f3-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a30f3-110">Требования</span><span class="sxs-lookup"><span data-stu-id="a30f3-110">Requirements</span></span>  
 <span data-ttu-id="a30f3-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a30f3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a30f3-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a30f3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a30f3-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a30f3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a30f3-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a30f3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a30f3-115">См. также</span><span class="sxs-lookup"><span data-stu-id="a30f3-115">See Also</span></span>  
 [<span data-ttu-id="a30f3-116">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="a30f3-116">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
