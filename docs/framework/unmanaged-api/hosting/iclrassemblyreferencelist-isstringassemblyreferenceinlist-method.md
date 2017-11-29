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
ms.openlocfilehash: ff0e51327e0e66c2a282ebf46e6036f81d3d568b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="d4559-102">Метод ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="d4559-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="d4559-103">Получает значение, указывающее, соответствует ли указанное имя, имя сборки в списке.</span><span class="sxs-lookup"><span data-stu-id="d4559-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4559-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d4559-104">Syntax</span></span>  
  
```  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4559-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d4559-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="d4559-106">[in] Имя сборки, который требуется найти.</span><span class="sxs-lookup"><span data-stu-id="d4559-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4559-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d4559-107">Return Value</span></span>  
  
|<span data-ttu-id="d4559-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d4559-108">HRESULT</span></span>|<span data-ttu-id="d4559-109">Описание</span><span class="sxs-lookup"><span data-stu-id="d4559-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d4559-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d4559-110">S_OK</span></span>|<span data-ttu-id="d4559-111">Строка отображается в списке.</span><span class="sxs-lookup"><span data-stu-id="d4559-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="d4559-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="d4559-112">S_FALSE</span></span>|<span data-ttu-id="d4559-113">Строка не отображается в списке.</span><span class="sxs-lookup"><span data-stu-id="d4559-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="d4559-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d4559-114">E_FAIL</span></span>|<span data-ttu-id="d4559-115">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="d4559-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d4559-116">После метод вернет значение E_FAIL, общеязыковая среда выполнения больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="d4559-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="d4559-117">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d4559-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d4559-118">Требования</span><span class="sxs-lookup"><span data-stu-id="d4559-118">Requirements</span></span>  
 <span data-ttu-id="d4559-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4559-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4559-120">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d4559-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d4559-121">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d4559-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d4559-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4559-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4559-123">См. также</span><span class="sxs-lookup"><span data-stu-id="d4559-123">See Also</span></span>  
 [<span data-ttu-id="d4559-124">Iclrassemblyidentitymanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="d4559-124">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="d4559-125">ICLRAssemblyReferenceList-интерфейс</span><span class="sxs-lookup"><span data-stu-id="d4559-125">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="d4559-126">Ihostassemblymanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="d4559-126">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="d4559-127">IHostAssemblyStore-интерфейс</span><span class="sxs-lookup"><span data-stu-id="d4559-127">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
