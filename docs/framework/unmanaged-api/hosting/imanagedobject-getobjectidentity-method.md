---
title: Метод IManagedObject::GetObjectIdentity
ms.date: 03/30/2017
api_name:
- IManagedObject.GetObjectIdentity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetObjectIdentity
helpviewer_keywords:
- GetObjectIdentity method [.NET Framework hosting]
- IManagedObject::GetObjectIdentity method [.NET Framework hosting]
ms.assetid: b862ff3e-e480-4cdf-84e2-e1013334a467
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3fbc4abe55d59c3140c5c180d5844404e357e3a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586316"
---
# <a name="imanagedobjectgetobjectidentity-method"></a><span data-ttu-id="98a86-102">Метод IManagedObject::GetObjectIdentity</span><span class="sxs-lookup"><span data-stu-id="98a86-102">IManagedObject::GetObjectIdentity Method</span></span>
<span data-ttu-id="98a86-103">Получает идентификатор данного управляемого объекта.</span><span class="sxs-lookup"><span data-stu-id="98a86-103">Gets the identity of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98a86-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="98a86-104">Syntax</span></span>  
  
```  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="98a86-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="98a86-105">Parameters</span></span>  
 `pBSTRGUID`  
 <span data-ttu-id="98a86-106">[out] Указатель на идентификатор GUID процесса, в котором размещен объект.</span><span class="sxs-lookup"><span data-stu-id="98a86-106">[out] A pointer to the GUID of the process in which the object resides.</span></span>  
  
 `AppDomainID`  
 <span data-ttu-id="98a86-107">[out] Указатель на идентификатор объекта домена приложения.</span><span class="sxs-lookup"><span data-stu-id="98a86-107">[out] A pointer to the ID of the object's application domain.</span></span>  
  
 `pCCW`  
 <span data-ttu-id="98a86-108">[out] Указатель на индекс объекта в классической виртуальной таблице COM.</span><span class="sxs-lookup"><span data-stu-id="98a86-108">[out] A pointer to object's index in the COM classic v-table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98a86-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="98a86-109">Remarks</span></span>  
 <span data-ttu-id="98a86-110">Идентификатор управляемого объекта включает GUID процесса, идентификатор домена приложения и индексу объекта в классической виртуальной таблице COM.</span><span class="sxs-lookup"><span data-stu-id="98a86-110">The identity of a managed object includes process GUID, application domain ID, and the object's index in the COM classic v-table.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98a86-111">Требования</span><span class="sxs-lookup"><span data-stu-id="98a86-111">Requirements</span></span>  
 <span data-ttu-id="98a86-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98a86-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98a86-113">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="98a86-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="98a86-114">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="98a86-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="98a86-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98a86-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98a86-116">См. также</span><span class="sxs-lookup"><span data-stu-id="98a86-116">See also</span></span>
- [<span data-ttu-id="98a86-117">Интерфейс IManagedObject</span><span class="sxs-lookup"><span data-stu-id="98a86-117">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
