---
title: "Метод ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRAssemblyIdentityManager.GetCLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList
helpviewer_keywords:
- GetClrAssemblyReferenceList method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList method [.NET Framework hosting]
ms.assetid: cb5ffae5-287b-4a87-9ca8-7ce3ae0601b7
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eefe5ff68c7bd428c18729dcbd792b4c3cb64c2e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrassemblyidentitymanagergetclrassemblyreferencelist-method"></a><span data-ttu-id="7e4d6-102">Метод ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="7e4d6-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList Method</span></span>
<span data-ttu-id="7e4d6-103">Возвращает указатель интерфейса [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) экземпляр из предоставленного списка частичных идентификаторов сборки.</span><span class="sxs-lookup"><span data-stu-id="7e4d6-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e4d6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e4d6-104">Syntax</span></span>  
  
```  
HRESULT  GetCLRAssemblyReferenceList (  
    [in] LPCWSTR *ppwzAssemblyReferences,  
    [in] DWORD    dwNumOfReferences,  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7e4d6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7e4d6-105">Parameters</span></span>  
 `ppwzAssemblyReferences`  
 <span data-ttu-id="7e4d6-106">[in] Массив строк, завершающуюся значением null, в форме «свойство name = value...», укажите список частичные идентификаторы сборки.</span><span class="sxs-lookup"><span data-stu-id="7e4d6-106">[in] An array of null-terminated strings in the form "name, property=value..." that specify a list of partial assembly identities.</span></span>  
  
 `dwNumOfReferences`  
 <span data-ttu-id="7e4d6-107">[in] Число элементов в `ppwzAssemblyReferences`.</span><span class="sxs-lookup"><span data-stu-id="7e4d6-107">[in] The number of items in `ppwzAssemblyReferences`.</span></span>  
  
 `ppReferenceList`  
 <span data-ttu-id="7e4d6-108">[out] Указатель интерфейса `ICLRAssemblyReferenceList` объект, содержащий данные идентификации сборки в список сборок, указанных в `ppwzAssemblyReferences`.</span><span class="sxs-lookup"><span data-stu-id="7e4d6-108">[out] An interface pointer to an `ICLRAssemblyReferenceList` object that contains the assembly identity data for the list of assemblies specified in `ppwzAssemblyReferences`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e4d6-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7e4d6-109">Return Value</span></span>  
  
|<span data-ttu-id="7e4d6-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7e4d6-110">HRESULT</span></span>|<span data-ttu-id="7e4d6-111">Описание</span><span class="sxs-lookup"><span data-stu-id="7e4d6-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7e4d6-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="7e4d6-112">S_OK</span></span>|<span data-ttu-id="7e4d6-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="7e4d6-113">The method returned successfully.</span></span>|  
|<span data-ttu-id="7e4d6-114">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7e4d6-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7e4d6-115">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="7e4d6-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7e4d6-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7e4d6-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7e4d6-117">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="7e4d6-117">The call timed out.</span></span>|  
|<span data-ttu-id="7e4d6-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7e4d6-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7e4d6-119">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="7e4d6-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7e4d6-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7e4d6-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7e4d6-121">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="7e4d6-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7e4d6-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7e4d6-122">E_FAIL</span></span>|<span data-ttu-id="7e4d6-123">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="7e4d6-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7e4d6-124">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="7e4d6-124">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7e4d6-125">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7e4d6-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7e4d6-126">Требования</span><span class="sxs-lookup"><span data-stu-id="7e4d6-126">Requirements</span></span>  
 <span data-ttu-id="7e4d6-127">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e4d6-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e4d6-128">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7e4d6-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7e4d6-129">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7e4d6-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e4d6-130">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e4d6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e4d6-131">См. также</span><span class="sxs-lookup"><span data-stu-id="7e4d6-131">See Also</span></span>  
 [<span data-ttu-id="7e4d6-132">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="7e4d6-132">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="7e4d6-133">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="7e4d6-133">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
