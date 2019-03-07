---
title: Метод ICorPublishAppDomain::GetID
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetID
helpviewer_keywords:
- GetID method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetID method [.NET Framework debugging]
ms.assetid: 229437e3-1465-4bd8-8846-9804b2488133
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a7541a2093fe877fb84a8a05237f18c4da43c44
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465989"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="bad0c-102">Метод ICorPublishAppDomain::GetID</span><span class="sxs-lookup"><span data-stu-id="bad0c-102">ICorPublishAppDomain::GetID Method</span></span>
<span data-ttu-id="bad0c-103">Возвращает уникальный идентификатор для данного [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="bad0c-103">Gets the unique identifier for this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bad0c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bad0c-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bad0c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bad0c-105">Parameters</span></span>  
 `puId`  
 <span data-ttu-id="bad0c-106">[out] Указатель на идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="bad0c-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bad0c-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="bad0c-107">Remarks</span></span>  
 <span data-ttu-id="bad0c-108">Этот идентификатор уникален только в рамках содержащего его процесса.</span><span class="sxs-lookup"><span data-stu-id="bad0c-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bad0c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="bad0c-109">Requirements</span></span>  
 <span data-ttu-id="bad0c-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bad0c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bad0c-111">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="bad0c-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="bad0c-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bad0c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bad0c-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bad0c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bad0c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="bad0c-114">See also</span></span>
- [<span data-ttu-id="bad0c-115">Интерфейс ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="bad0c-115">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
