---
title: "Метод ICorDebugManagedCallback::ControlCTrap"
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
- ICorDebugManagedCallback.ControlCTrap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ControlCTrap
helpviewer_keywords:
- ICorDebugManagedCallback::ControlCTrap method [.NET Framework debugging]
- ControlCTrap method [.NET Framework debugging]
ms.assetid: 0500854e-2121-43d9-a028-64312da35258
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6c5de52b810efeaf7b5c103dcd39a37a37ab3272
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a><span data-ttu-id="387b8-102">Метод ICorDebugManagedCallback::ControlCTrap</span><span class="sxs-lookup"><span data-stu-id="387b8-102">ICorDebugManagedCallback::ControlCTrap Method</span></span>
<span data-ttu-id="387b8-103">Уведомляет отладчик о том, что сочетание клавиш CTRL + C, представленные в отлаживаемом процессе.</span><span class="sxs-lookup"><span data-stu-id="387b8-103">Notifies the debugger that a CTRL+C is trapped in the process that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="387b8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="387b8-104">Syntax</span></span>  
  
```  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="387b8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="387b8-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="387b8-106">[in] Указатель на объект ICorDebugProcess, представляет собой процесс, в котором производится перехват CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="387b8-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the CTRL+C is trapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="387b8-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="387b8-107">Return Value</span></span>  
  
|<span data-ttu-id="387b8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="387b8-108">HRESULT</span></span>|<span data-ttu-id="387b8-109">Описание</span><span class="sxs-lookup"><span data-stu-id="387b8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="387b8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="387b8-110">S_OK</span></span>|<span data-ttu-id="387b8-111">Отладчик будет обрабатывать нажатие клавиши CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="387b8-111">The debugger will handle the CTRL+C trap.</span></span>|  
|<span data-ttu-id="387b8-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="387b8-112">S_FALSE</span></span>|<span data-ttu-id="387b8-113">Отладчик не будет обрабатывать нажатие клавиши CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="387b8-113">The debugger will not handle the CTRL+C trap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="387b8-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="387b8-114">Remarks</span></span>  
 <span data-ttu-id="387b8-115">Для этого обратного вызова, останавливаются все домены приложений в процессе.</span><span class="sxs-lookup"><span data-stu-id="387b8-115">All application domains within the process are stopped for this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="387b8-116">Требования</span><span class="sxs-lookup"><span data-stu-id="387b8-116">Requirements</span></span>  
 <span data-ttu-id="387b8-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="387b8-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="387b8-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="387b8-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="387b8-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="387b8-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="387b8-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="387b8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="387b8-121">См. также</span><span class="sxs-lookup"><span data-stu-id="387b8-121">See Also</span></span>  
 [<span data-ttu-id="387b8-122">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="387b8-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
