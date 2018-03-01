---
title: "Метод ICorPublish::GetProcess"
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
- ICorPublish.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e613b9101e842a584eef4bcbac1bf3de1dba5cd3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="035d7-102">Метод ICorPublish::GetProcess</span><span class="sxs-lookup"><span data-stu-id="035d7-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="035d7-103">Возвращает [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) экземпляр, представляющий процесс с указанным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="035d7-103">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="035d7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="035d7-104">Syntax</span></span>  
  
```  
HRESULT GetProcess(  
    [in] unsigned              pid,   
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="035d7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="035d7-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="035d7-106">[in] Идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="035d7-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="035d7-107">[out] Указатель на адрес `ICorPublishProcess` экземпляр, представляющий процесс.</span><span class="sxs-lookup"><span data-stu-id="035d7-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="035d7-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="035d7-108">Remarks</span></span>  
 <span data-ttu-id="035d7-109">`GetProcess`завершается неудачей, если процесс не существует или не является управляемым процессом, который можно отлаживать текущим пользователем.</span><span class="sxs-lookup"><span data-stu-id="035d7-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="035d7-110">Требования</span><span class="sxs-lookup"><span data-stu-id="035d7-110">Requirements</span></span>  
 <span data-ttu-id="035d7-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="035d7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="035d7-112">**Заголовок:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="035d7-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="035d7-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="035d7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="035d7-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="035d7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="035d7-115">См. также</span><span class="sxs-lookup"><span data-stu-id="035d7-115">See Also</span></span>  
 [<span data-ttu-id="035d7-116">Интерфейс ICorPublish</span><span class="sxs-lookup"><span data-stu-id="035d7-116">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
