---
title: Метод ICorDebugManagedCallback2::DestroyConnection
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.DestroyConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::DestroyConnection
helpviewer_keywords:
- DestroyConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::DestroyConnection method [.NET Framework debugging]
ms.assetid: cf7940e9-4558-4319-925c-09f6c98c8fcd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 35ae3a9761798ed9ea42b984f2c6c2cad4e42777
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075929"
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a><span data-ttu-id="daf2f-102">Метод ICorDebugManagedCallback2::DestroyConnection</span><span class="sxs-lookup"><span data-stu-id="daf2f-102">ICorDebugManagedCallback2::DestroyConnection Method</span></span>
<span data-ttu-id="daf2f-103">Уведомляет отладчик о том, что указанное соединение было прервано.</span><span class="sxs-lookup"><span data-stu-id="daf2f-103">Notifies the debugger that the specified connection has been terminated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daf2f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="daf2f-104">Syntax</span></span>  
  
```  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="daf2f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="daf2f-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="daf2f-106">[in] Указатель на объект ICorDebugProcess, представляющий процесс, содержащий соединения, в котором был удален.</span><span class="sxs-lookup"><span data-stu-id="daf2f-106">[in] A pointer to an ICorDebugProcess object that represents the process containing the connection that was destroyed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="daf2f-107">[in] Идентификатор соединения, в котором был удален.</span><span class="sxs-lookup"><span data-stu-id="daf2f-107">[in] The ID of the connection that was destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="daf2f-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="daf2f-108">Remarks</span></span>  
 <span data-ttu-id="daf2f-109">Объект `DestroyConnection` запускается обратного вызова, когда узел вызывает [ICLRDebugManager::EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) в [API размещения](../../../../docs/framework/unmanaged-api/hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="daf2f-109">A `DestroyConnection` callback will be fired when a host calls [ICLRDebugManager::EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daf2f-110">Требования</span><span class="sxs-lookup"><span data-stu-id="daf2f-110">Requirements</span></span>  
 <span data-ttu-id="daf2f-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="daf2f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daf2f-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="daf2f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="daf2f-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="daf2f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="daf2f-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="daf2f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daf2f-115">См. также</span><span class="sxs-lookup"><span data-stu-id="daf2f-115">See also</span></span>

- [<span data-ttu-id="daf2f-116">Интерфейс ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="daf2f-116">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="daf2f-117">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="daf2f-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
