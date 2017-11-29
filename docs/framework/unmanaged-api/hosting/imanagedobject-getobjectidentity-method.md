---
title: "Метод IManagedObject::GetObjectIdentity"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IManagedObject.GetObjectIdentity
api_location: mscoree.dll
api_type: COM
f1_keywords: GetObjectIdentity
helpviewer_keywords:
- GetObjectIdentity method [.NET Framework hosting]
- IManagedObject::GetObjectIdentity method [.NET Framework hosting]
ms.assetid: b862ff3e-e480-4cdf-84e2-e1013334a467
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7c0dabfca147b203c3bcf93a362e6670ae295338
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="imanagedobjectgetobjectidentity-method"></a><span data-ttu-id="f3dd5-102">Метод IManagedObject::GetObjectIdentity</span><span class="sxs-lookup"><span data-stu-id="f3dd5-102">IManagedObject::GetObjectIdentity Method</span></span>
<span data-ttu-id="f3dd5-103">Возвращает идентификатор этого управляемого объекта.</span><span class="sxs-lookup"><span data-stu-id="f3dd5-103">Gets the identity of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3dd5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3dd5-104">Syntax</span></span>  
  
```  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f3dd5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f3dd5-105">Parameters</span></span>  
 `pBSTRGUID`  
 <span data-ttu-id="f3dd5-106">[out] Указатель на идентификатор GUID процесса, в которой находится объект.</span><span class="sxs-lookup"><span data-stu-id="f3dd5-106">[out] A pointer to the GUID of the process in which the object resides.</span></span>  
  
 `AppDomainID`  
 <span data-ttu-id="f3dd5-107">[out] Указатель на идентификатор объекта в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="f3dd5-107">[out] A pointer to the ID of the object's application domain.</span></span>  
  
 `pCCW`  
 <span data-ttu-id="f3dd5-108">[out] Указатель на индекс объекта в классической виртуальной таблице COM.</span><span class="sxs-lookup"><span data-stu-id="f3dd5-108">[out] A pointer to object's index in the COM classic v-table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3dd5-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="f3dd5-109">Remarks</span></span>  
 <span data-ttu-id="f3dd5-110">Идентификация управляемого объекта включает GUID процесса, идентификатор домена приложения и индексу объекта в классической виртуальной таблице COM.</span><span class="sxs-lookup"><span data-stu-id="f3dd5-110">The identity of a managed object includes process GUID, application domain ID, and the object's index in the COM classic v-table.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3dd5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f3dd5-111">Requirements</span></span>  
 <span data-ttu-id="f3dd5-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3dd5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3dd5-113">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f3dd5-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f3dd5-114">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f3dd5-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f3dd5-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3dd5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3dd5-116">См. также</span><span class="sxs-lookup"><span data-stu-id="f3dd5-116">See Also</span></span>  
 [<span data-ttu-id="f3dd5-117">IManagedObject-интерфейс</span><span class="sxs-lookup"><span data-stu-id="f3dd5-117">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
