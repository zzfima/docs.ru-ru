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
ms.openlocfilehash: 0b7eeadd532e5a53c693cc1cde59150777d7edc2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iclrassemblyreferencelistisassemblyreferenceinlist-method"></a><span data-ttu-id="80179-102">Метод ICLRAssemblyReferenceList::IsAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="80179-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList Method</span></span>
<span data-ttu-id="80179-103">Возвращает значение, указывающее, является ли заданный указатель ссылается на сборку в списке.</span><span class="sxs-lookup"><span data-stu-id="80179-103">Gets a value that indicates whether the supplied pointer refers to an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80179-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="80179-104">Syntax</span></span>  
  
```  
HRESULT IsAssemblyReferenceInList (  
    [in] IUnknown *pName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="80179-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="80179-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="80179-106">[in] Указатель интерфейса на сборку.</span><span class="sxs-lookup"><span data-stu-id="80179-106">[in] An interface pointer to the assembly for which to search.</span></span> <span data-ttu-id="80179-107">Допустимые значения: типа `IAssemblyName` или `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="80179-107">Valid values are of type `IAssemblyName` or `IReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80179-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="80179-108">Return Value</span></span>  
  
|<span data-ttu-id="80179-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="80179-109">HRESULT</span></span>|<span data-ttu-id="80179-110">Описание</span><span class="sxs-lookup"><span data-stu-id="80179-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="80179-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="80179-111">S_OK</span></span>|<span data-ttu-id="80179-112">Строка отображается в списке.</span><span class="sxs-lookup"><span data-stu-id="80179-112">The string appears in the list.</span></span>|  
|<span data-ttu-id="80179-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="80179-113">S_FALSE</span></span>|<span data-ttu-id="80179-114">Строка не отображается в списке.</span><span class="sxs-lookup"><span data-stu-id="80179-114">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="80179-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="80179-115">E_FAIL</span></span>|<span data-ttu-id="80179-116">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="80179-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="80179-117">После метод вернет значение E_FAIL, общеязыковая среда выполнения больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="80179-117">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="80179-118">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="80179-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="80179-119">Требования</span><span class="sxs-lookup"><span data-stu-id="80179-119">Requirements</span></span>  
 <span data-ttu-id="80179-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80179-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80179-121">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="80179-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="80179-122">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="80179-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="80179-123">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80179-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80179-124">См. также</span><span class="sxs-lookup"><span data-stu-id="80179-124">See Also</span></span>  
 [<span data-ttu-id="80179-125">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="80179-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="80179-126">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="80179-126">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="80179-127">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="80179-127">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="80179-128">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="80179-128">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
