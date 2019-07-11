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
ms.openlocfilehash: 72bfb896ccff23938a4fc218fb1f95eebcf5bb93
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773503"
---
# <a name="iclrassemblyidentitymanagergetclrassemblyreferencelist-method"></a><span data-ttu-id="26dbd-102">Метод ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="26dbd-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList Method</span></span>
<span data-ttu-id="26dbd-103">Получает указатель интерфейса на [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) экземпляр из предоставленного списка частичных идентификаторов сборки.</span><span class="sxs-lookup"><span data-stu-id="26dbd-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26dbd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="26dbd-104">Syntax</span></span>  
  
```cpp  
HRESULT  GetCLRAssemblyReferenceList (  
    [in] LPCWSTR *ppwzAssemblyReferences,  
    [in] DWORD    dwNumOfReferences,  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26dbd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="26dbd-105">Parameters</span></span>  
 `ppwzAssemblyReferences`  
 <span data-ttu-id="26dbd-106">[in] Массив строк, завершающаяся символом null, в форме «свойство name = value...» Укажите список удостоверений частичной сборки.</span><span class="sxs-lookup"><span data-stu-id="26dbd-106">[in] An array of null-terminated strings in the form "name, property=value..." that specify a list of partial assembly identities.</span></span>  
  
 `dwNumOfReferences`  
 <span data-ttu-id="26dbd-107">[in] Число элементов в `ppwzAssemblyReferences`.</span><span class="sxs-lookup"><span data-stu-id="26dbd-107">[in] The number of items in `ppwzAssemblyReferences`.</span></span>  
  
 `ppReferenceList`  
 <span data-ttu-id="26dbd-108">[out] Указатель интерфейса на `ICLRAssemblyReferenceList` , содержащий данные идентификации сборки для сборки, указанные в списке `ppwzAssemblyReferences`.</span><span class="sxs-lookup"><span data-stu-id="26dbd-108">[out] An interface pointer to an `ICLRAssemblyReferenceList` object that contains the assembly identity data for the list of assemblies specified in `ppwzAssemblyReferences`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26dbd-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="26dbd-109">Return Value</span></span>  
  
|<span data-ttu-id="26dbd-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="26dbd-110">HRESULT</span></span>|<span data-ttu-id="26dbd-111">Описание</span><span class="sxs-lookup"><span data-stu-id="26dbd-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="26dbd-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="26dbd-112">S_OK</span></span>|<span data-ttu-id="26dbd-113">Метод возвратился успешно.</span><span class="sxs-lookup"><span data-stu-id="26dbd-113">The method returned successfully.</span></span>|  
|<span data-ttu-id="26dbd-114">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="26dbd-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="26dbd-115">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="26dbd-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="26dbd-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="26dbd-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="26dbd-117">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="26dbd-117">The call timed out.</span></span>|  
|<span data-ttu-id="26dbd-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="26dbd-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="26dbd-119">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="26dbd-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="26dbd-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="26dbd-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="26dbd-121">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="26dbd-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="26dbd-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="26dbd-122">E_FAIL</span></span>|<span data-ttu-id="26dbd-123">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="26dbd-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="26dbd-124">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="26dbd-124">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="26dbd-125">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="26dbd-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="26dbd-126">Требования</span><span class="sxs-lookup"><span data-stu-id="26dbd-126">Requirements</span></span>  
 <span data-ttu-id="26dbd-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26dbd-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26dbd-128">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="26dbd-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="26dbd-129">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="26dbd-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="26dbd-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26dbd-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26dbd-131">См. также</span><span class="sxs-lookup"><span data-stu-id="26dbd-131">See also</span></span>

- [<span data-ttu-id="26dbd-132">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="26dbd-132">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="26dbd-133">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="26dbd-133">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
