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
ms.openlocfilehash: 4dc91723f009d46f9c57b1c99aa66ba7a1b127e4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126636"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="c97c8-102">Метод ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="c97c8-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="c97c8-103">Возвращает значение, указывающее, совпадает ли заданное имя с именем сборки в списке.</span><span class="sxs-lookup"><span data-stu-id="c97c8-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c97c8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c97c8-104">Syntax</span></span>  
  
```cpp  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c97c8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c97c8-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="c97c8-106">окне Имя сборки, для которой необходимо выполнить поиск.</span><span class="sxs-lookup"><span data-stu-id="c97c8-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c97c8-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c97c8-107">Return Value</span></span>  
  
|<span data-ttu-id="c97c8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c97c8-108">HRESULT</span></span>|<span data-ttu-id="c97c8-109">Описание</span><span class="sxs-lookup"><span data-stu-id="c97c8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c97c8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c97c8-110">S_OK</span></span>|<span data-ttu-id="c97c8-111">Строка появится в списке.</span><span class="sxs-lookup"><span data-stu-id="c97c8-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="c97c8-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c97c8-112">S_FALSE</span></span>|<span data-ttu-id="c97c8-113">Строка не отображается в списке.</span><span class="sxs-lookup"><span data-stu-id="c97c8-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="c97c8-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c97c8-114">E_FAIL</span></span>|<span data-ttu-id="c97c8-115">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="c97c8-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c97c8-116">После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="c97c8-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="c97c8-117">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c97c8-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c97c8-118">Требования</span><span class="sxs-lookup"><span data-stu-id="c97c8-118">Requirements</span></span>  
 <span data-ttu-id="c97c8-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c97c8-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c97c8-120">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c97c8-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c97c8-121">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c97c8-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c97c8-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c97c8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c97c8-123">См. также</span><span class="sxs-lookup"><span data-stu-id="c97c8-123">See also</span></span>

- [<span data-ttu-id="c97c8-124">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="c97c8-124">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="c97c8-125">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="c97c8-125">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="c97c8-126">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="c97c8-126">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="c97c8-127">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="c97c8-127">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
