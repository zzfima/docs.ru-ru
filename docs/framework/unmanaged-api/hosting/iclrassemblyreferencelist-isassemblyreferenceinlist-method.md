---
title: Метод ICLRAssemblyReferenceList::IsAssemblyReferenceInList
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList.IsAssemblyReferenceInList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList::IsAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsAssemblyReferenceInList method [.NET Framework hosting]
- IsAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: 8a570813-21be-407e-92a6-7ae8de3bc728
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 557b15fe2bd04a3362532f190a88ee2ad52ed366
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499840"
---
# <a name="iclrassemblyreferencelistisassemblyreferenceinlist-method"></a><span data-ttu-id="a21cf-102">Метод ICLRAssemblyReferenceList::IsAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="a21cf-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList Method</span></span>
<span data-ttu-id="a21cf-103">Получает значение, указывающее, ссылается ли заданный указатель на сборку в списке.</span><span class="sxs-lookup"><span data-stu-id="a21cf-103">Gets a value that indicates whether the supplied pointer refers to an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a21cf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a21cf-104">Syntax</span></span>  
  
```  
HRESULT IsAssemblyReferenceInList (  
    [in] IUnknown *pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a21cf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a21cf-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="a21cf-106">[in] Указатель интерфейса на сборку, который требуется найти.</span><span class="sxs-lookup"><span data-stu-id="a21cf-106">[in] An interface pointer to the assembly for which to search.</span></span> <span data-ttu-id="a21cf-107">Допустимые значения имеют тип `IAssemblyName` или `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="a21cf-107">Valid values are of type `IAssemblyName` or `IReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a21cf-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a21cf-108">Return Value</span></span>  
  
|<span data-ttu-id="a21cf-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a21cf-109">HRESULT</span></span>|<span data-ttu-id="a21cf-110">Описание</span><span class="sxs-lookup"><span data-stu-id="a21cf-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a21cf-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a21cf-111">S_OK</span></span>|<span data-ttu-id="a21cf-112">Строка отображается в списке.</span><span class="sxs-lookup"><span data-stu-id="a21cf-112">The string appears in the list.</span></span>|  
|<span data-ttu-id="a21cf-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a21cf-113">S_FALSE</span></span>|<span data-ttu-id="a21cf-114">Строка не отображается в списке.</span><span class="sxs-lookup"><span data-stu-id="a21cf-114">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="a21cf-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a21cf-115">E_FAIL</span></span>|<span data-ttu-id="a21cf-116">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="a21cf-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a21cf-117">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="a21cf-117">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="a21cf-118">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a21cf-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a21cf-119">Требования</span><span class="sxs-lookup"><span data-stu-id="a21cf-119">Requirements</span></span>  
 <span data-ttu-id="a21cf-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a21cf-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a21cf-121">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a21cf-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a21cf-122">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a21cf-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a21cf-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a21cf-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a21cf-124">См. также</span><span class="sxs-lookup"><span data-stu-id="a21cf-124">See also</span></span>
- [<span data-ttu-id="a21cf-125">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="a21cf-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="a21cf-126">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="a21cf-126">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="a21cf-127">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="a21cf-127">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="a21cf-128">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="a21cf-128">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
