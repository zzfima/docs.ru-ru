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
ms.openlocfilehash: 41b39597a5a438592d2ae07a16510f5406a91a43
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422836"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="773ef-102">Метод ICorPublishAppDomain::GetID</span><span class="sxs-lookup"><span data-stu-id="773ef-102">ICorPublishAppDomain::GetID Method</span></span>
<span data-ttu-id="773ef-103">Возвращает уникальный идентификатор для этого [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="773ef-103">Gets the unique identifier for this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="773ef-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="773ef-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="773ef-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="773ef-105">Parameters</span></span>  
 `puId`  
 <span data-ttu-id="773ef-106">[out] Указатель на идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="773ef-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="773ef-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="773ef-107">Remarks</span></span>  
 <span data-ttu-id="773ef-108">Этот идентификатор уникален только в области содержащего его процесса.</span><span class="sxs-lookup"><span data-stu-id="773ef-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="773ef-109">Требования</span><span class="sxs-lookup"><span data-stu-id="773ef-109">Requirements</span></span>  
 <span data-ttu-id="773ef-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="773ef-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="773ef-111">**Заголовок:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="773ef-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="773ef-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="773ef-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="773ef-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="773ef-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="773ef-114">См. также</span><span class="sxs-lookup"><span data-stu-id="773ef-114">See Also</span></span>  
 [<span data-ttu-id="773ef-115">Интерфейс ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="773ef-115">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
