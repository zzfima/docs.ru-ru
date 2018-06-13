---
title: Метод ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49962e632ced9aac376791ead672e6910117ee10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434743"
---
# <a name="iclrassemblyidentitymanagergetclrassemblyreferencelist-method"></a><span data-ttu-id="d9e51-102">Метод ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="d9e51-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList Method</span></span>
<span data-ttu-id="d9e51-103">Возвращает указатель интерфейса [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) экземпляр из предоставленного списка частичных идентификаторов сборки.</span><span class="sxs-lookup"><span data-stu-id="d9e51-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9e51-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d9e51-104">Syntax</span></span>  
  
```  
HRESULT  GetCLRAssemblyReferenceList (  
    [in] LPCWSTR *ppwzAssemblyReferences,  
    [in] DWORD    dwNumOfReferences,  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d9e51-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d9e51-105">Parameters</span></span>  
 `ppwzAssemblyReferences`  
 <span data-ttu-id="d9e51-106">[in] Массив строк, завершающуюся значением null, в форме «свойство name = value...», укажите список частичные идентификаторы сборки.</span><span class="sxs-lookup"><span data-stu-id="d9e51-106">[in] An array of null-terminated strings in the form "name, property=value..." that specify a list of partial assembly identities.</span></span>  
  
 `dwNumOfReferences`  
 <span data-ttu-id="d9e51-107">[in] Число элементов в `ppwzAssemblyReferences`.</span><span class="sxs-lookup"><span data-stu-id="d9e51-107">[in] The number of items in `ppwzAssemblyReferences`.</span></span>  
  
 `ppReferenceList`  
 <span data-ttu-id="d9e51-108">[out] Указатель интерфейса `ICLRAssemblyReferenceList` объект, содержащий данные идентификации сборки в список сборок, указанных в `ppwzAssemblyReferences`.</span><span class="sxs-lookup"><span data-stu-id="d9e51-108">[out] An interface pointer to an `ICLRAssemblyReferenceList` object that contains the assembly identity data for the list of assemblies specified in `ppwzAssemblyReferences`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9e51-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d9e51-109">Return Value</span></span>  
  
|<span data-ttu-id="d9e51-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d9e51-110">HRESULT</span></span>|<span data-ttu-id="d9e51-111">Описание</span><span class="sxs-lookup"><span data-stu-id="d9e51-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d9e51-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="d9e51-112">S_OK</span></span>|<span data-ttu-id="d9e51-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="d9e51-113">The method returned successfully.</span></span>|  
|<span data-ttu-id="d9e51-114">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d9e51-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d9e51-115">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="d9e51-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d9e51-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d9e51-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d9e51-117">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="d9e51-117">The call timed out.</span></span>|  
|<span data-ttu-id="d9e51-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d9e51-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d9e51-119">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="d9e51-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d9e51-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d9e51-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d9e51-121">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="d9e51-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d9e51-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d9e51-122">E_FAIL</span></span>|<span data-ttu-id="d9e51-123">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="d9e51-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d9e51-124">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="d9e51-124">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d9e51-125">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d9e51-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d9e51-126">Требования</span><span class="sxs-lookup"><span data-stu-id="d9e51-126">Requirements</span></span>  
 <span data-ttu-id="d9e51-127">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9e51-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9e51-128">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d9e51-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d9e51-129">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d9e51-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d9e51-130">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9e51-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9e51-131">См. также</span><span class="sxs-lookup"><span data-stu-id="d9e51-131">See Also</span></span>  
 [<span data-ttu-id="d9e51-132">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="d9e51-132">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="d9e51-133">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="d9e51-133">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
