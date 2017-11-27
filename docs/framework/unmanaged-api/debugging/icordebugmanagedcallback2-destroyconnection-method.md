---
title: "Метод ICorDebugManagedCallback2::DestroyConnection"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.DestroyConnection
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::DestroyConnection
helpviewer_keywords:
- DestroyConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::DestroyConnection method [.NET Framework debugging]
ms.assetid: cf7940e9-4558-4319-925c-09f6c98c8fcd
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c35c39e5ce2b6478d6945d765403c6e4b63eef89
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a><span data-ttu-id="04c80-102">Метод ICorDebugManagedCallback2::DestroyConnection</span><span class="sxs-lookup"><span data-stu-id="04c80-102">ICorDebugManagedCallback2::DestroyConnection Method</span></span>
<span data-ttu-id="04c80-103">Уведомляет отладчик о том, что указанное соединение было прервано.</span><span class="sxs-lookup"><span data-stu-id="04c80-103">Notifies the debugger that the specified connection has been terminated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04c80-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04c80-104">Syntax</span></span>  
  
```  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="04c80-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="04c80-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="04c80-106">[in] Указатель на объект ICorDebugProcess, который представляет собой процесс, содержащий соединение, который был удален.</span><span class="sxs-lookup"><span data-stu-id="04c80-106">[in] A pointer to an ICorDebugProcess object that represents the process containing the connection that was destroyed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="04c80-107">[in] Идентификатор соединения, который был удален.</span><span class="sxs-lookup"><span data-stu-id="04c80-107">[in] The ID of the connection that was destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04c80-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="04c80-108">Remarks</span></span>  
 <span data-ttu-id="04c80-109">Объект `DestroyConnection` запускается обратного вызова, когда основное приложение вызывает [ICLRDebugManager::EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) в [API размещения](../../../../docs/framework/unmanaged-api/hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="04c80-109">A `DestroyConnection` callback will be fired when a host calls [ICLRDebugManager::EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04c80-110">Требования</span><span class="sxs-lookup"><span data-stu-id="04c80-110">Requirements</span></span>  
 <span data-ttu-id="04c80-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04c80-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04c80-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="04c80-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="04c80-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04c80-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04c80-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04c80-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04c80-115">См. также</span><span class="sxs-lookup"><span data-stu-id="04c80-115">See Also</span></span>  
 [<span data-ttu-id="04c80-116">ICorDebugManagedCallback2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="04c80-116">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="04c80-117">ICorDebugManagedCallback-интерфейс</span><span class="sxs-lookup"><span data-stu-id="04c80-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
