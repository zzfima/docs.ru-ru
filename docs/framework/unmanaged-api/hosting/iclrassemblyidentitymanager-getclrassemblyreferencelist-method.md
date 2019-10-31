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
ms.openlocfilehash: 54c11e78438ae97e1fc0c715c9161361784b3be6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126721"
---
# <a name="iclrassemblyidentitymanagergetclrassemblyreferencelist-method"></a><span data-ttu-id="4554f-102">Метод ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="4554f-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList Method</span></span>
<span data-ttu-id="4554f-103">Возвращает указатель интерфейса на экземпляр [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) из заданного списка частичных идентификаторов сборки.</span><span class="sxs-lookup"><span data-stu-id="4554f-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4554f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4554f-104">Syntax</span></span>  
  
```cpp  
HRESULT  GetCLRAssemblyReferenceList (  
    [in] LPCWSTR *ppwzAssemblyReferences,  
    [in] DWORD    dwNumOfReferences,  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4554f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4554f-105">Parameters</span></span>  
 `ppwzAssemblyReferences`  
 <span data-ttu-id="4554f-106">окне Массив строк с завершающим нулем в форме "имя, свойство = значение..." , задающих список частичных идентификаторов сборки.</span><span class="sxs-lookup"><span data-stu-id="4554f-106">[in] An array of null-terminated strings in the form "name, property=value..." that specify a list of partial assembly identities.</span></span>  
  
 `dwNumOfReferences`  
 <span data-ttu-id="4554f-107">окне Число элементов в `ppwzAssemblyReferences`.</span><span class="sxs-lookup"><span data-stu-id="4554f-107">[in] The number of items in `ppwzAssemblyReferences`.</span></span>  
  
 `ppReferenceList`  
 <span data-ttu-id="4554f-108">заполняет Указатель интерфейса на объект `ICLRAssemblyReferenceList`, содержащий данные удостоверения сборки для списка сборок, указанных в `ppwzAssemblyReferences`.</span><span class="sxs-lookup"><span data-stu-id="4554f-108">[out] An interface pointer to an `ICLRAssemblyReferenceList` object that contains the assembly identity data for the list of assemblies specified in `ppwzAssemblyReferences`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4554f-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4554f-109">Return Value</span></span>  
  
|<span data-ttu-id="4554f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4554f-110">HRESULT</span></span>|<span data-ttu-id="4554f-111">Описание</span><span class="sxs-lookup"><span data-stu-id="4554f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4554f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4554f-112">S_OK</span></span>|<span data-ttu-id="4554f-113">Метод успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="4554f-113">The method returned successfully.</span></span>|  
|<span data-ttu-id="4554f-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4554f-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4554f-115">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="4554f-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4554f-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4554f-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4554f-117">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="4554f-117">The call timed out.</span></span>|  
|<span data-ttu-id="4554f-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4554f-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4554f-119">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="4554f-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4554f-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4554f-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4554f-121">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="4554f-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4554f-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4554f-122">E_FAIL</span></span>|<span data-ttu-id="4554f-123">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="4554f-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4554f-124">Если метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="4554f-124">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4554f-125">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4554f-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4554f-126">Требования</span><span class="sxs-lookup"><span data-stu-id="4554f-126">Requirements</span></span>  
 <span data-ttu-id="4554f-127">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4554f-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4554f-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4554f-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4554f-129">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4554f-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4554f-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4554f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4554f-131">См. также</span><span class="sxs-lookup"><span data-stu-id="4554f-131">See also</span></span>

- [<span data-ttu-id="4554f-132">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="4554f-132">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="4554f-133">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="4554f-133">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
