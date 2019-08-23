---
title: Метод IHostAssemblyManager::GetAssemblyStore
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager.GetAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetAssemblyStore
helpviewer_keywords:
- IHostAssemblyManager::GetAssemblyStore method [.NET Framework hosting]
- GetAssemblyStore method [.NET Framework hosting]
ms.assetid: d0f74593-9bb1-4a11-8096-e29734b20698
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62965fa928522052b6885769e02c0211ca8d3fe0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937935"
---
# <a name="ihostassemblymanagergetassemblystore-method"></a><span data-ttu-id="fd3a6-102">Метод IHostAssemblyManager::GetAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="fd3a6-102">IHostAssemblyManager::GetAssemblyStore Method</span></span>
<span data-ttu-id="fd3a6-103">Возвращает указатель интерфейса на объект [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) , представляющий список сборок, загруженных узлом.</span><span class="sxs-lookup"><span data-stu-id="fd3a6-103">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd3a6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd3a6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd3a6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fd3a6-105">Parameters</span></span>  
 `ppAssemblyStore`  
 <span data-ttu-id="fd3a6-106">заполняет Указатель функции на `IHostAssemblyStore` экземпляр или значение null, если узел не реализует `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="fd3a6-106">[out] A function pointer to an `IHostAssemblyStore` instance, or null, if the host does not implement `IHostAssemblyStore`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd3a6-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fd3a6-107">Return Value</span></span>  
  
|<span data-ttu-id="fd3a6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fd3a6-108">HRESULT</span></span>|<span data-ttu-id="fd3a6-109">Описание</span><span class="sxs-lookup"><span data-stu-id="fd3a6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fd3a6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fd3a6-110">S_OK</span></span>|<span data-ttu-id="fd3a6-111">`GetAssemblyStore`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="fd3a6-111">`GetAssemblyStore` returned successfully.</span></span>|  
|<span data-ttu-id="fd3a6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fd3a6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fd3a6-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="fd3a6-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fd3a6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fd3a6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fd3a6-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="fd3a6-115">The call timed out.</span></span>|  
|<span data-ttu-id="fd3a6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fd3a6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fd3a6-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="fd3a6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fd3a6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fd3a6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fd3a6-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="fd3a6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fd3a6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fd3a6-120">E_FAIL</span></span>|<span data-ttu-id="fd3a6-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="fd3a6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fd3a6-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="fd3a6-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fd3a6-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fd3a6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fd3a6-124">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="fd3a6-124">E_NOINTERFACE</span></span>|<span data-ttu-id="fd3a6-125">Узел не предоставляет реализацию `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="fd3a6-125">The host does not provide an implementation of `IHostAssemblyStore`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd3a6-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="fd3a6-126">Remarks</span></span>  
 <span data-ttu-id="fd3a6-127">`IHostAssemblyStore`предоставляет методы, позволяющие узлу выполнять привязку к сборкам и модулям независимо от среды CLR.</span><span class="sxs-lookup"><span data-stu-id="fd3a6-127">`IHostAssemblyStore` provides methods that allow a host to bind to assemblies and modules independently of the CLR.</span></span> <span data-ttu-id="fd3a6-128">Узлы обычно предоставляют хранилища сборок, позволяющие загружать сборки из форматов, отличных от файловой системы.</span><span class="sxs-lookup"><span data-stu-id="fd3a6-128">Hosts typically provide assembly stores to allow assemblies to be loaded from formats other than the file system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fd3a6-129">Если узел не реализует `IHostAssemblyStore`, `GetAssemblyStore` должен возвращать значение HRESULT E_NOINTERFACE и устанавливать `ppAssemblyStore` его в NULL.</span><span class="sxs-lookup"><span data-stu-id="fd3a6-129">If the host does not implement `IHostAssemblyStore`, `GetAssemblyStore` should return an HRESULT value of E_NOINTERFACE, and should set `ppAssemblyStore` to null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd3a6-130">Требования</span><span class="sxs-lookup"><span data-stu-id="fd3a6-130">Requirements</span></span>  
 <span data-ttu-id="fd3a6-131">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd3a6-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd3a6-132">**Заголовок.** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fd3a6-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fd3a6-133">**Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fd3a6-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd3a6-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd3a6-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd3a6-135">См. также</span><span class="sxs-lookup"><span data-stu-id="fd3a6-135">See also</span></span>

- [<span data-ttu-id="fd3a6-136">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="fd3a6-136">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="fd3a6-137">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="fd3a6-137">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
