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
ms.openlocfilehash: b0da548d5d5cc22eb6754859a802afa4d82fac89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a><span data-ttu-id="0b6bc-102">Метод IHostAssemblyManager::GetNonHostStoreAssemblies</span><span class="sxs-lookup"><span data-stu-id="0b6bc-102">IHostAssemblyManager::GetNonHostStoreAssemblies Method</span></span>
<span data-ttu-id="0b6bc-103">Возвращает указатель интерфейса [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) , представляющий список сборок, которые, по общеязыковой среды выполнения (CLR) для загрузки.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the common language runtime (CLR) to load.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b6bc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b6bc-104">Syntax</span></span>  
  
```  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0b6bc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0b6bc-105">Parameters</span></span>  
 `ppReferenceList`  
 <span data-ttu-id="0b6bc-106">[out] Указатель на адрес `ICLRAssemblyReferenceList` , содержащий список ссылок на сборки, которые, среда CLR для загрузки.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-106">[out] A pointer to the address of an `ICLRAssemblyReferenceList` that contains a list of references to assemblies that the host expects the CLR to load.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b6bc-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0b6bc-107">Return Value</span></span>  
  
|<span data-ttu-id="0b6bc-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0b6bc-108">HRESULT</span></span>|<span data-ttu-id="0b6bc-109">Описание</span><span class="sxs-lookup"><span data-stu-id="0b6bc-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0b6bc-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0b6bc-110">S_OK</span></span>|<span data-ttu-id="0b6bc-111">`GetNonHostStoreAssemblies` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-111">`GetNonHostStoreAssemblies` returned successfully.</span></span>|  
|<span data-ttu-id="0b6bc-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0b6bc-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0b6bc-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0b6bc-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0b6bc-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0b6bc-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-115">The call timed out.</span></span>|  
|<span data-ttu-id="0b6bc-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0b6bc-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0b6bc-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0b6bc-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0b6bc-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0b6bc-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0b6bc-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0b6bc-120">E_FAIL</span></span>|<span data-ttu-id="0b6bc-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0b6bc-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0b6bc-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0b6bc-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="0b6bc-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="0b6bc-125">Не хватает памяти была доступна для создания списка ссылок для запрошенного `ICLRAssemblyReferenceList`.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-125">Not enough memory was available to create the list of references for the requested `ICLRAssemblyReferenceList`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b6bc-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="0b6bc-126">Remarks</span></span>  
 <span data-ttu-id="0b6bc-127">Среда CLR разрешает ссылки, используя следующий набор правил:</span><span class="sxs-lookup"><span data-stu-id="0b6bc-127">The CLR resolves references using the following set of guidelines:</span></span>  
  
-   <span data-ttu-id="0b6bc-128">Во-первых, он просматривает список ссылок на сборки, возвращенные `GetNonHostStoreAssemblies`.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-128">First, it consults the list of assembly references returned by `GetNonHostStoreAssemblies`.</span></span>  
  
-   <span data-ttu-id="0b6bc-129">Если сборка присутствует в списке, среда CLR привязывает ее обычным образом.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-129">If the assembly appears in the list, the CLR binds to it normally.</span></span>  
  
-   <span data-ttu-id="0b6bc-130">Если сборка не отображается в списке и узла была предоставлена реализация [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), среда CLR вызывает [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) чтобы разрешить основному приложению предоставить сборка для привязки.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-130">If the assembly does not appear in the list and the host has provided an implementation of [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), the CLR calls [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) to allow the host to supply the assembly to bind to.</span></span>  
  
-   <span data-ttu-id="0b6bc-131">В противном случае среда CLR не удается выполнить привязку сборки.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-131">Otherwise, the CLR fails to bind to the assembly.</span></span>  
  
 <span data-ttu-id="0b6bc-132">Если узел задает `ppReferenceList` значение null, среда CLR сначала проверяет глобальный кэш сборок, вызывает `ProvideAssembly`, а затем проверяет базу приложения для разрешения ссылки на сборку.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-132">If the host sets `ppReferenceList` to null, the CLR first probes the global assembly cache, calls `ProvideAssembly`, and then probes the application base to resolve an assembly reference.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b6bc-133">При инициализации, среда CLR вызывает `GetNonHostStoreAssemblies` только один раз.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-133">Upon initialization, the CLR calls `GetNonHostStoreAssemblies` only once.</span></span> <span data-ttu-id="0b6bc-134">Метод не вызывается повторно.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-134">The method is not called again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b6bc-135">Требования</span><span class="sxs-lookup"><span data-stu-id="0b6bc-135">Requirements</span></span>  
 <span data-ttu-id="0b6bc-136">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b6bc-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b6bc-137">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0b6bc-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0b6bc-138">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0b6bc-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0b6bc-139">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b6bc-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b6bc-140">См. также</span><span class="sxs-lookup"><span data-stu-id="0b6bc-140">See Also</span></span>  
 [<span data-ttu-id="0b6bc-141">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="0b6bc-141">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="0b6bc-142">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="0b6bc-142">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="0b6bc-143">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="0b6bc-143">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
