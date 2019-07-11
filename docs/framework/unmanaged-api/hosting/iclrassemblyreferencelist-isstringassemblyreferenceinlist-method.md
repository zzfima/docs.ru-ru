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
ms.openlocfilehash: 4b2860e811a16406a71d7ab8df123f2b32aaf13e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773296"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="ffc63-102">Метод ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="ffc63-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="ffc63-103">Получает значение, указывающее, соответствует ли указанное имя, имя сборки в списке.</span><span class="sxs-lookup"><span data-stu-id="ffc63-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffc63-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ffc63-104">Syntax</span></span>  
  
```cpp  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ffc63-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ffc63-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="ffc63-106">[in] Имя сборки, который требуется найти.</span><span class="sxs-lookup"><span data-stu-id="ffc63-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ffc63-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ffc63-107">Return Value</span></span>  
  
|<span data-ttu-id="ffc63-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ffc63-108">HRESULT</span></span>|<span data-ttu-id="ffc63-109">Описание</span><span class="sxs-lookup"><span data-stu-id="ffc63-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ffc63-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ffc63-110">S_OK</span></span>|<span data-ttu-id="ffc63-111">Строка отображается в списке.</span><span class="sxs-lookup"><span data-stu-id="ffc63-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="ffc63-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ffc63-112">S_FALSE</span></span>|<span data-ttu-id="ffc63-113">Строка не отображается в списке.</span><span class="sxs-lookup"><span data-stu-id="ffc63-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="ffc63-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ffc63-114">E_FAIL</span></span>|<span data-ttu-id="ffc63-115">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="ffc63-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ffc63-116">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="ffc63-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="ffc63-117">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ffc63-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ffc63-118">Требования</span><span class="sxs-lookup"><span data-stu-id="ffc63-118">Requirements</span></span>  
 <span data-ttu-id="ffc63-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffc63-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffc63-120">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ffc63-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ffc63-121">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ffc63-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ffc63-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffc63-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffc63-123">См. также</span><span class="sxs-lookup"><span data-stu-id="ffc63-123">See also</span></span>

- [<span data-ttu-id="ffc63-124">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="ffc63-124">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="ffc63-125">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="ffc63-125">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="ffc63-126">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="ffc63-126">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="ffc63-127">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="ffc63-127">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
