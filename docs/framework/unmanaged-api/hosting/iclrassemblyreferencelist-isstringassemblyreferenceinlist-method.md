---
title: Метод ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList.IsStringAssemblyReferenceInList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList method [.NET Framework hosting]
- IsStringAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: e6121cc3-2f11-42c7-bdae-47808581ff71
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de17a91b5093372579a4d9435532a95406addd0a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216903"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="070cf-102">Метод ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="070cf-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="070cf-103">Получает значение, указывающее, соответствует ли указанное имя, имя сборки в списке.</span><span class="sxs-lookup"><span data-stu-id="070cf-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="070cf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="070cf-104">Syntax</span></span>  
  
```  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="070cf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="070cf-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="070cf-106">[in] Имя сборки, который требуется найти.</span><span class="sxs-lookup"><span data-stu-id="070cf-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="070cf-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="070cf-107">Return Value</span></span>  
  
|<span data-ttu-id="070cf-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="070cf-108">HRESULT</span></span>|<span data-ttu-id="070cf-109">Описание</span><span class="sxs-lookup"><span data-stu-id="070cf-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="070cf-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="070cf-110">S_OK</span></span>|<span data-ttu-id="070cf-111">Строка отображается в списке.</span><span class="sxs-lookup"><span data-stu-id="070cf-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="070cf-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="070cf-112">S_FALSE</span></span>|<span data-ttu-id="070cf-113">Строка не отображается в списке.</span><span class="sxs-lookup"><span data-stu-id="070cf-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="070cf-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="070cf-114">E_FAIL</span></span>|<span data-ttu-id="070cf-115">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="070cf-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="070cf-116">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="070cf-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="070cf-117">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="070cf-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="070cf-118">Требования</span><span class="sxs-lookup"><span data-stu-id="070cf-118">Requirements</span></span>  
 <span data-ttu-id="070cf-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="070cf-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="070cf-120">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="070cf-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="070cf-121">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="070cf-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="070cf-122">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="070cf-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="070cf-123">См. также</span><span class="sxs-lookup"><span data-stu-id="070cf-123">See also</span></span>

- [<span data-ttu-id="070cf-124">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="070cf-124">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="070cf-125">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="070cf-125">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="070cf-126">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="070cf-126">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="070cf-127">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="070cf-127">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
