---
title: Метод ICorPublishProcess::GetProcessID
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetProcessID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetProcessID
helpviewer_keywords:
- ICorPublishProcess::GetProcessID method [.NET Framework debugging]
- GetProcessID method [.NET Framework debugging]
ms.assetid: f31185e0-f01d-463a-b392-42163e39bfe9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91e1697366bd3ee95fd040ee261d68417a8125e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="59874-102">Метод ICorPublishProcess::GetProcessID</span><span class="sxs-lookup"><span data-stu-id="59874-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="59874-103">Возвращает идентификатор операционной системы для данного процесса.</span><span class="sxs-lookup"><span data-stu-id="59874-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59874-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59874-104">Syntax</span></span>  
  
```  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="59874-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="59874-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="59874-106">[out] Указатель на идентификатор процесса, представленный этим [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="59874-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59874-107">Требования</span><span class="sxs-lookup"><span data-stu-id="59874-107">Requirements</span></span>  
 <span data-ttu-id="59874-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59874-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59874-109">**Заголовок:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="59874-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="59874-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59874-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59874-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59874-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59874-112">См. также</span><span class="sxs-lookup"><span data-stu-id="59874-112">See Also</span></span>  
 [<span data-ttu-id="59874-113">Интерфейс ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="59874-113">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
