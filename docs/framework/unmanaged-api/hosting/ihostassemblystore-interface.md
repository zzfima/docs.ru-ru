---
title: Интерфейс IHostAssemblyStore
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore
helpviewer_keywords:
- IHostAssemblyStore interface [.NET Framework hosting]
ms.assetid: cccb650f-abe0-41e2-9fd1-b383788eb1f6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f881440b2e93745723bd090cfbab0286dcd0a4e5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937874"
---
# <a name="ihostassemblystore-interface"></a><span data-ttu-id="48068-102">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="48068-102">IHostAssemblyStore Interface</span></span>
<span data-ttu-id="48068-103">Предоставляет методы, позволяющие узлу загружать сборки и модули независимо от общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="48068-103">Provides methods that allow a host to load assemblies and modules independently of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="48068-104">Методы</span><span class="sxs-lookup"><span data-stu-id="48068-104">Methods</span></span>  
  
|<span data-ttu-id="48068-105">Метод</span><span class="sxs-lookup"><span data-stu-id="48068-105">Method</span></span>|<span data-ttu-id="48068-106">Описание</span><span class="sxs-lookup"><span data-stu-id="48068-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="48068-107">Метод ProvideAssembly</span><span class="sxs-lookup"><span data-stu-id="48068-107">ProvideAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|<span data-ttu-id="48068-108">Возвращает ссылку на сборку, на которую не ссылается [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) , возвращенную из вызова [IHostAssemblyManager:: GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span><span class="sxs-lookup"><span data-stu-id="48068-108">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) returned from a call to [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span>|  
|[<span data-ttu-id="48068-109">Метод ProvideModule</span><span class="sxs-lookup"><span data-stu-id="48068-109">ProvideModule Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|<span data-ttu-id="48068-110">Разрешает модуль в сборке или в связанном (не внедренном) файле ресурсов.</span><span class="sxs-lookup"><span data-stu-id="48068-110">Resolves a module within an assembly or a linked (not embedded) resource file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48068-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="48068-111">Remarks</span></span>  
 <span data-ttu-id="48068-112">`IHostAssemblyStore`Предоставляет узлу способ эффективного загрузки сборок на основе удостоверения сборки.</span><span class="sxs-lookup"><span data-stu-id="48068-112">`IHostAssemblyStore` provides a way for a host to load assemblies efficiently based on assembly identity.</span></span> <span data-ttu-id="48068-113">Узел загружает сборки, возвращая `IStream` экземпляры, которые указывают непосредственно в байтах.</span><span class="sxs-lookup"><span data-stu-id="48068-113">The host loads assemblies by returning `IStream` instances that point directly at the bytes.</span></span>  
  
 <span data-ttu-id="48068-114">Среда CLR определяет, реализован `IHostAssemblyStore` ли узел путем вызова `IHostAssemblyManager::GetNonHostAssemblyStores` после инициализации.</span><span class="sxs-lookup"><span data-stu-id="48068-114">The CLR determines whether a host has implemented `IHostAssemblyStore` by calling `IHostAssemblyManager::GetNonHostAssemblyStores` upon initialization.</span></span> <span data-ttu-id="48068-115">Это позволяет узлу, например, управлять привязкой к пользовательским сборкам, а также использовать среду выполнения для привязки к .NET Framework сборкам.</span><span class="sxs-lookup"><span data-stu-id="48068-115">This allows the host, for example, to control binding to user assemblies, but to rely on the runtime to bind to .NET Framework assemblies.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="48068-116">При предоставлении реализации `IHostAssemblyStore`узел определяет его цель для разрешения всех сборок, на которые не ссылается объект `ICLRAssemblyReferenceList` , возвращенный из `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span><span class="sxs-lookup"><span data-stu-id="48068-116">In providing an implementation of `IHostAssemblyStore`, the host specifies its intent to resolve all assemblies that are not referenced by the `ICLRAssemblyReferenceList` returned from `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="48068-117">.NET Framework версии 2,0 не позволяет узлу загружать машинный образ сборки, как это предоставляется служебной программой [генератора образов в машинном код (Ngen. exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) .</span><span class="sxs-lookup"><span data-stu-id="48068-117">The .NET Framework version 2.0 does not provide a way for the host to load the native image of an assembly, as provided by the [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48068-118">Требования</span><span class="sxs-lookup"><span data-stu-id="48068-118">Requirements</span></span>  
 <span data-ttu-id="48068-119">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48068-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48068-120">**Заголовок.** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="48068-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="48068-121">**Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="48068-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48068-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48068-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48068-123">См. также</span><span class="sxs-lookup"><span data-stu-id="48068-123">See also</span></span>

- [<span data-ttu-id="48068-124">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="48068-124">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="48068-125">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="48068-125">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="48068-126">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="48068-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
