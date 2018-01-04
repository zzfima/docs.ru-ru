---
title: "Метод IHostAssemblyManager::GetAssemblyStore"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyManager.GetAssemblyStore
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyManager::GetAssemblyStore
helpviewer_keywords:
- IHostAssemblyManager::GetAssemblyStore method [.NET Framework hosting]
- GetAssemblyStore method [.NET Framework hosting]
ms.assetid: d0f74593-9bb1-4a11-8096-e29734b20698
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 347947622601475147663b8838bef5f36a1f7e32
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihostassemblymanagergetassemblystore-method"></a><span data-ttu-id="296fb-102">Метод IHostAssemblyManager::GetAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="296fb-102">IHostAssemblyManager::GetAssemblyStore Method</span></span>
<span data-ttu-id="296fb-103">Возвращает указатель интерфейса [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) , представляющий список сборок, загруженных приложением.</span><span class="sxs-lookup"><span data-stu-id="296fb-103">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="296fb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="296fb-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="296fb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="296fb-105">Parameters</span></span>  
 `ppAssemblyStore`  
 <span data-ttu-id="296fb-106">[out] Указатель на функцию, чтобы `IHostAssemblyStore` экземпляра, или значение null, если узел не реализует `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="296fb-106">[out] A function pointer to an `IHostAssemblyStore` instance, or null, if the host does not implement `IHostAssemblyStore`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="296fb-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="296fb-107">Return Value</span></span>  
  
|<span data-ttu-id="296fb-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="296fb-108">HRESULT</span></span>|<span data-ttu-id="296fb-109">Описание</span><span class="sxs-lookup"><span data-stu-id="296fb-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="296fb-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="296fb-110">S_OK</span></span>|<span data-ttu-id="296fb-111">`GetAssemblyStore`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="296fb-111">`GetAssemblyStore` returned successfully.</span></span>|  
|<span data-ttu-id="296fb-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="296fb-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="296fb-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="296fb-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="296fb-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="296fb-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="296fb-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="296fb-115">The call timed out.</span></span>|  
|<span data-ttu-id="296fb-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="296fb-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="296fb-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="296fb-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="296fb-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="296fb-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="296fb-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="296fb-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="296fb-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="296fb-120">E_FAIL</span></span>|<span data-ttu-id="296fb-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="296fb-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="296fb-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="296fb-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="296fb-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="296fb-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="296fb-124">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="296fb-124">E_NOINTERFACE</span></span>|<span data-ttu-id="296fb-125">Узел не предоставляет реализацию `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="296fb-125">The host does not provide an implementation of `IHostAssemblyStore`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="296fb-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="296fb-126">Remarks</span></span>  
 <span data-ttu-id="296fb-127">`IHostAssemblyStore`Предоставляет методы, позволяющие основному приложению привязывать сборки и модули независимо от среды CLR.</span><span class="sxs-lookup"><span data-stu-id="296fb-127">`IHostAssemblyStore` provides methods that allow a host to bind to assemblies and modules independently of the CLR.</span></span> <span data-ttu-id="296fb-128">Узлы обычно предоставляют хранилища сборок для загрузки из форматов, отличных от файловой системы, позволяющие.</span><span class="sxs-lookup"><span data-stu-id="296fb-128">Hosts typically provide assembly stores to allow assemblies to be loaded from formats other than the file system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="296fb-129">Если узел не реализует `IHostAssemblyStore`, `GetAssemblyStore` должен возвращать значение HRESULT E_NOINTERFACE и устанавливайте `ppAssemblyStore` значение null.</span><span class="sxs-lookup"><span data-stu-id="296fb-129">If the host does not implement `IHostAssemblyStore`, `GetAssemblyStore` should return an HRESULT value of E_NOINTERFACE, and should set `ppAssemblyStore` to null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="296fb-130">Требования</span><span class="sxs-lookup"><span data-stu-id="296fb-130">Requirements</span></span>  
 <span data-ttu-id="296fb-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="296fb-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="296fb-132">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="296fb-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="296fb-133">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="296fb-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="296fb-134">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="296fb-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="296fb-135">См. также</span><span class="sxs-lookup"><span data-stu-id="296fb-135">See Also</span></span>  
 [<span data-ttu-id="296fb-136">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="296fb-136">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="296fb-137">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="296fb-137">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
