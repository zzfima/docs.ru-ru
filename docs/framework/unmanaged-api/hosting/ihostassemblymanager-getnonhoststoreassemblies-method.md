---
title: Метод IHostAssemblyManager::GetNonHostStoreAssemblies
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager.GetNonHostStoreAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies
helpviewer_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies method [.NET Framework hosting]
- GetNonHostStoreAssemblies method [.NET Framework hosting]
ms.assetid: d2250b38-c76a-40ce-80c8-ba45149886e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ae9a8e9e26f05675611ac4c6acd8ecfe5704b0c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104459"
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a><span data-ttu-id="ccf6e-102">Метод IHostAssemblyManager::GetNonHostStoreAssemblies</span><span class="sxs-lookup"><span data-stu-id="ccf6e-102">IHostAssemblyManager::GetNonHostStoreAssemblies Method</span></span>
<span data-ttu-id="ccf6e-103">Получает указатель интерфейса на [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) , представляющий список сборок, на которые оно ожидает общеязыковой среды выполнения (CLR) для загрузки.</span><span class="sxs-lookup"><span data-stu-id="ccf6e-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the common language runtime (CLR) to load.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccf6e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ccf6e-104">Syntax</span></span>  
  
```  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccf6e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ccf6e-105">Parameters</span></span>  
 `ppReferenceList`  
 <span data-ttu-id="ccf6e-106">[out] Указатель на адрес `ICLRAssemblyReferenceList` , содержащий список ссылок на сборки, которые, среда CLR для загрузки.</span><span class="sxs-lookup"><span data-stu-id="ccf6e-106">[out] A pointer to the address of an `ICLRAssemblyReferenceList` that contains a list of references to assemblies that the host expects the CLR to load.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ccf6e-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ccf6e-107">Return Value</span></span>  
  
|<span data-ttu-id="ccf6e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ccf6e-108">HRESULT</span></span>|<span data-ttu-id="ccf6e-109">Описание</span><span class="sxs-lookup"><span data-stu-id="ccf6e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ccf6e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ccf6e-110">S_OK</span></span>|<span data-ttu-id="ccf6e-111">`GetNonHostStoreAssemblies` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="ccf6e-111">`GetNonHostStoreAssemblies` returned successfully.</span></span>|  
|<span data-ttu-id="ccf6e-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ccf6e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ccf6e-113">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="ccf6e-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ccf6e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ccf6e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ccf6e-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="ccf6e-115">The call timed out.</span></span>|  
|<span data-ttu-id="ccf6e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ccf6e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ccf6e-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="ccf6e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ccf6e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ccf6e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ccf6e-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="ccf6e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ccf6e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ccf6e-120">E_FAIL</span></span>|<span data-ttu-id="ccf6e-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="ccf6e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ccf6e-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="ccf6e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ccf6e-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ccf6e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ccf6e-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ccf6e-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ccf6e-125">Не хватает памяти была доступна для создания списка ссылок для запрошенного `ICLRAssemblyReferenceList`.</span><span class="sxs-lookup"><span data-stu-id="ccf6e-125">Not enough memory was available to create the list of references for the requested `ICLRAssemblyReferenceList`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ccf6e-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="ccf6e-126">Remarks</span></span>  
 <span data-ttu-id="ccf6e-127">Среда CLR разрешает ссылки, используя следующий набор правил:</span><span class="sxs-lookup"><span data-stu-id="ccf6e-127">The CLR resolves references using the following set of guidelines:</span></span>  
  
-   <span data-ttu-id="ccf6e-128">Во-первых, она учитывает список ссылок на сборки, возвращенный `GetNonHostStoreAssemblies`.</span><span class="sxs-lookup"><span data-stu-id="ccf6e-128">First, it consults the list of assembly references returned by `GetNonHostStoreAssemblies`.</span></span>  
  
-   <span data-ttu-id="ccf6e-129">Если сборка присутствует в списке, среда CLR привязывает к нему обычным образом.</span><span class="sxs-lookup"><span data-stu-id="ccf6e-129">If the assembly appears in the list, the CLR binds to it normally.</span></span>  
  
-   <span data-ttu-id="ccf6e-130">Если сборка не отображается в списке, а узел предоставил реализацию [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), среда CLR вызывает [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) чтобы разрешить основному приложению предоставить сборка для привязки.</span><span class="sxs-lookup"><span data-stu-id="ccf6e-130">If the assembly does not appear in the list and the host has provided an implementation of [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), the CLR calls [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) to allow the host to supply the assembly to bind to.</span></span>  
  
-   <span data-ttu-id="ccf6e-131">В противном случае среде CLR не удается выполнить привязку к сборке.</span><span class="sxs-lookup"><span data-stu-id="ccf6e-131">Otherwise, the CLR fails to bind to the assembly.</span></span>  
  
 <span data-ttu-id="ccf6e-132">Если основное приложение задает `ppReferenceList` значение NULL, среда CLR сначала проверяет глобальный кэш сборок, вызывает `ProvideAssembly`, а затем проверяет базу приложения для разрешения ссылки на сборку.</span><span class="sxs-lookup"><span data-stu-id="ccf6e-132">If the host sets `ppReferenceList` to null, the CLR first probes the global assembly cache, calls `ProvideAssembly`, and then probes the application base to resolve an assembly reference.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ccf6e-133">При инициализации, среда CLR вызывает `GetNonHostStoreAssemblies` только один раз.</span><span class="sxs-lookup"><span data-stu-id="ccf6e-133">Upon initialization, the CLR calls `GetNonHostStoreAssemblies` only once.</span></span> <span data-ttu-id="ccf6e-134">Метод не вызывается снова.</span><span class="sxs-lookup"><span data-stu-id="ccf6e-134">The method is not called again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccf6e-135">Требования</span><span class="sxs-lookup"><span data-stu-id="ccf6e-135">Requirements</span></span>  
 <span data-ttu-id="ccf6e-136">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccf6e-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccf6e-137">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ccf6e-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ccf6e-138">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ccf6e-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ccf6e-139">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccf6e-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccf6e-140">См. также</span><span class="sxs-lookup"><span data-stu-id="ccf6e-140">See also</span></span>

- [<span data-ttu-id="ccf6e-141">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="ccf6e-141">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="ccf6e-142">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="ccf6e-142">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="ccf6e-143">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="ccf6e-143">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
