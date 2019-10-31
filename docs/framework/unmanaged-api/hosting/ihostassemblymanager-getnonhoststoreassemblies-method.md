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
ms.openlocfilehash: eb715e1a4f9a210a1440874a9a8cea2d85345d33
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124579"
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a><span data-ttu-id="62152-102">Метод IHostAssemblyManager::GetNonHostStoreAssemblies</span><span class="sxs-lookup"><span data-stu-id="62152-102">IHostAssemblyManager::GetNonHostStoreAssemblies Method</span></span>
<span data-ttu-id="62152-103">Возвращает указатель интерфейса на объект [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) , представляющий список сборок, которые должны загружаться хостом в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="62152-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the common language runtime (CLR) to load.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62152-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62152-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62152-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="62152-105">Parameters</span></span>  
 `ppReferenceList`  
 <span data-ttu-id="62152-106">заполняет Указатель на адрес `ICLRAssemblyReferenceList`, который содержит список ссылок на сборки, которые обслуживающая система должна загрузить из среды CLR.</span><span class="sxs-lookup"><span data-stu-id="62152-106">[out] A pointer to the address of an `ICLRAssemblyReferenceList` that contains a list of references to assemblies that the host expects the CLR to load.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62152-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="62152-107">Return Value</span></span>  
  
|<span data-ttu-id="62152-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="62152-108">HRESULT</span></span>|<span data-ttu-id="62152-109">Описание</span><span class="sxs-lookup"><span data-stu-id="62152-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="62152-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="62152-110">S_OK</span></span>|<span data-ttu-id="62152-111">`GetNonHostStoreAssemblies` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="62152-111">`GetNonHostStoreAssemblies` returned successfully.</span></span>|  
|<span data-ttu-id="62152-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="62152-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="62152-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="62152-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="62152-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="62152-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="62152-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="62152-115">The call timed out.</span></span>|  
|<span data-ttu-id="62152-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="62152-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="62152-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="62152-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="62152-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="62152-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="62152-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="62152-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="62152-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="62152-120">E_FAIL</span></span>|<span data-ttu-id="62152-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="62152-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="62152-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="62152-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="62152-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="62152-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="62152-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="62152-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="62152-125">Недостаточно свободной памяти для создания списка ссылок для запрошенного `ICLRAssemblyReferenceList`.</span><span class="sxs-lookup"><span data-stu-id="62152-125">Not enough memory was available to create the list of references for the requested `ICLRAssemblyReferenceList`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62152-126">Заметки</span><span class="sxs-lookup"><span data-stu-id="62152-126">Remarks</span></span>  
 <span data-ttu-id="62152-127">Среда CLR разрешает ссылки с помощью следующего набора рекомендаций:</span><span class="sxs-lookup"><span data-stu-id="62152-127">The CLR resolves references using the following set of guidelines:</span></span>  
  
- <span data-ttu-id="62152-128">Во первых, он обращается к списку ссылок на сборки, возвращаемых `GetNonHostStoreAssemblies`.</span><span class="sxs-lookup"><span data-stu-id="62152-128">First, it consults the list of assembly references returned by `GetNonHostStoreAssemblies`.</span></span>  
  
- <span data-ttu-id="62152-129">Если сборка отображается в списке, среда CLR привязывает ее к обычному.</span><span class="sxs-lookup"><span data-stu-id="62152-129">If the assembly appears in the list, the CLR binds to it normally.</span></span>  
  
- <span data-ttu-id="62152-130">Если сборка не отображается в списке и узел предоставил реализацию [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), среда CLR вызывает [IHostAssemblyStore::P ровидеассембли](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) , чтобы разрешить узлу предоставить сборку для привязки.</span><span class="sxs-lookup"><span data-stu-id="62152-130">If the assembly does not appear in the list and the host has provided an implementation of [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), the CLR calls [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) to allow the host to supply the assembly to bind to.</span></span>  
  
- <span data-ttu-id="62152-131">В противном случае среда CLR не сможет выполнить привязку к сборке.</span><span class="sxs-lookup"><span data-stu-id="62152-131">Otherwise, the CLR fails to bind to the assembly.</span></span>  
  
 <span data-ttu-id="62152-132">Если узел задает `ppReferenceList` null, среда CLR сначала проверяет глобальный кэш сборок, вызывает `ProvideAssembly`, а затем проверяет базу приложения для разрешения ссылки на сборку.</span><span class="sxs-lookup"><span data-stu-id="62152-132">If the host sets `ppReferenceList` to null, the CLR first probes the global assembly cache, calls `ProvideAssembly`, and then probes the application base to resolve an assembly reference.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="62152-133">После инициализации среда CLR вызывает `GetNonHostStoreAssemblies` только один раз.</span><span class="sxs-lookup"><span data-stu-id="62152-133">Upon initialization, the CLR calls `GetNonHostStoreAssemblies` only once.</span></span> <span data-ttu-id="62152-134">Метод не вызывается снова.</span><span class="sxs-lookup"><span data-stu-id="62152-134">The method is not called again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62152-135">Требования</span><span class="sxs-lookup"><span data-stu-id="62152-135">Requirements</span></span>  
 <span data-ttu-id="62152-136">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62152-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62152-137">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="62152-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="62152-138">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="62152-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62152-139">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62152-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62152-140">См. также</span><span class="sxs-lookup"><span data-stu-id="62152-140">See also</span></span>

- [<span data-ttu-id="62152-141">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="62152-141">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="62152-142">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="62152-142">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="62152-143">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="62152-143">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
