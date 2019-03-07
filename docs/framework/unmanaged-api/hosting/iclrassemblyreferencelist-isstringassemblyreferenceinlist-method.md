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
ms.openlocfilehash: 9ed527aadce68e82bee5809aab7c4229a95b5d3f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478873"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="d2435-102">Метод ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="d2435-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="d2435-103">Получает значение, указывающее, соответствует ли указанное имя, имя сборки в списке.</span><span class="sxs-lookup"><span data-stu-id="d2435-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2435-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d2435-104">Syntax</span></span>  
  
```  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2435-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d2435-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="d2435-106">[in] Имя сборки, который требуется найти.</span><span class="sxs-lookup"><span data-stu-id="d2435-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2435-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d2435-107">Return Value</span></span>  
  
|<span data-ttu-id="d2435-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d2435-108">HRESULT</span></span>|<span data-ttu-id="d2435-109">Описание</span><span class="sxs-lookup"><span data-stu-id="d2435-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d2435-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d2435-110">S_OK</span></span>|<span data-ttu-id="d2435-111">Строка отображается в списке.</span><span class="sxs-lookup"><span data-stu-id="d2435-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="d2435-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="d2435-112">S_FALSE</span></span>|<span data-ttu-id="d2435-113">Строка не отображается в списке.</span><span class="sxs-lookup"><span data-stu-id="d2435-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="d2435-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d2435-114">E_FAIL</span></span>|<span data-ttu-id="d2435-115">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="d2435-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d2435-116">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="d2435-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="d2435-117">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d2435-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d2435-118">Требования</span><span class="sxs-lookup"><span data-stu-id="d2435-118">Requirements</span></span>  
 <span data-ttu-id="d2435-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2435-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2435-120">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d2435-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d2435-121">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d2435-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2435-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2435-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2435-123">См. также</span><span class="sxs-lookup"><span data-stu-id="d2435-123">See also</span></span>
- [<span data-ttu-id="d2435-124">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="d2435-124">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="d2435-125">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="d2435-125">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="d2435-126">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="d2435-126">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="d2435-127">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="d2435-127">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
