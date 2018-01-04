---
title: "Метод ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyReferenceList.IsStringAssemblyReferenceInList
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList method [.NET Framework hosting]
- IsStringAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: e6121cc3-2f11-42c7-bdae-47808581ff71
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 27d81e8b5171ded3301eaafea19d4a09b461078e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="56d24-102">Метод ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="56d24-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="56d24-103">Получает значение, указывающее, соответствует ли указанное имя, имя сборки в списке.</span><span class="sxs-lookup"><span data-stu-id="56d24-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56d24-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56d24-104">Syntax</span></span>  
  
```  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="56d24-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="56d24-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="56d24-106">[in] Имя сборки, который требуется найти.</span><span class="sxs-lookup"><span data-stu-id="56d24-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56d24-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="56d24-107">Return Value</span></span>  
  
|<span data-ttu-id="56d24-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="56d24-108">HRESULT</span></span>|<span data-ttu-id="56d24-109">Описание</span><span class="sxs-lookup"><span data-stu-id="56d24-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="56d24-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="56d24-110">S_OK</span></span>|<span data-ttu-id="56d24-111">Строка отображается в списке.</span><span class="sxs-lookup"><span data-stu-id="56d24-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="56d24-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="56d24-112">S_FALSE</span></span>|<span data-ttu-id="56d24-113">Строка не отображается в списке.</span><span class="sxs-lookup"><span data-stu-id="56d24-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="56d24-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="56d24-114">E_FAIL</span></span>|<span data-ttu-id="56d24-115">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="56d24-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="56d24-116">После метод вернет значение E_FAIL, общеязыковая среда выполнения больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="56d24-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="56d24-117">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="56d24-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="56d24-118">Требования</span><span class="sxs-lookup"><span data-stu-id="56d24-118">Requirements</span></span>  
 <span data-ttu-id="56d24-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56d24-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56d24-120">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="56d24-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="56d24-121">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="56d24-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="56d24-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56d24-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56d24-123">См. также</span><span class="sxs-lookup"><span data-stu-id="56d24-123">See Also</span></span>  
 [<span data-ttu-id="56d24-124">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="56d24-124">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="56d24-125">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="56d24-125">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="56d24-126">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="56d24-126">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="56d24-127">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="56d24-127">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
