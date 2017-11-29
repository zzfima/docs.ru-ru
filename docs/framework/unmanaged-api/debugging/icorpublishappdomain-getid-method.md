---
title: "Метод ICorPublishAppDomain::GetID"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishAppDomain.GetID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishAppDomain::GetID
helpviewer_keywords:
- GetID method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetID method [.NET Framework debugging]
ms.assetid: 229437e3-1465-4bd8-8846-9804b2488133
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bfbde806f409f2639b2468e0ba962b1659d1ffc3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="2a37c-102">Метод ICorPublishAppDomain::GetID</span><span class="sxs-lookup"><span data-stu-id="2a37c-102">ICorPublishAppDomain::GetID Method</span></span>
<span data-ttu-id="2a37c-103">Возвращает уникальный идентификатор для этого [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="2a37c-103">Gets the unique identifier for this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a37c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a37c-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2a37c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2a37c-105">Parameters</span></span>  
 `puId`  
 <span data-ttu-id="2a37c-106">[out] Указатель на идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="2a37c-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a37c-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="2a37c-107">Remarks</span></span>  
 <span data-ttu-id="2a37c-108">Этот идентификатор уникален только в области содержащего его процесса.</span><span class="sxs-lookup"><span data-stu-id="2a37c-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a37c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="2a37c-109">Requirements</span></span>  
 <span data-ttu-id="2a37c-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a37c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a37c-111">**Заголовок:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="2a37c-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="2a37c-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a37c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a37c-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a37c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a37c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="2a37c-114">See Also</span></span>  
 [<span data-ttu-id="2a37c-115">ICorPublishAppDomain-интерфейс</span><span class="sxs-lookup"><span data-stu-id="2a37c-115">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
