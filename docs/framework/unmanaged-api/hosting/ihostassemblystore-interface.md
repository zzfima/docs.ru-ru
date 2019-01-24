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
ms.openlocfilehash: d3714f31d0ab58584a8671055cf4c607f04a832c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611063"
---
# <a name="ihostassemblystore-interface"></a><span data-ttu-id="19db1-102">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="19db1-102">IHostAssemblyStore Interface</span></span>
<span data-ttu-id="19db1-103">Предоставляет методы, позволяющие основному приложению загружать сборки и модули независимо от общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="19db1-103">Provides methods that allow a host to load assemblies and modules independently of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="19db1-104">Методы</span><span class="sxs-lookup"><span data-stu-id="19db1-104">Methods</span></span>  
  
|<span data-ttu-id="19db1-105">Метод</span><span class="sxs-lookup"><span data-stu-id="19db1-105">Method</span></span>|<span data-ttu-id="19db1-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="19db1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="19db1-107">Метод ProvideAssembly</span><span class="sxs-lookup"><span data-stu-id="19db1-107">ProvideAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|<span data-ttu-id="19db1-108">Возвращает ссылку на сборку, которая не ссылается на [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) возвращается из вызова [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span><span class="sxs-lookup"><span data-stu-id="19db1-108">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) returned from a call to [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span>|  
|[<span data-ttu-id="19db1-109">Метод ProvideModule</span><span class="sxs-lookup"><span data-stu-id="19db1-109">ProvideModule Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|<span data-ttu-id="19db1-110">Разрешает модуль в сборку или связанного файла ресурсов (не embedded).</span><span class="sxs-lookup"><span data-stu-id="19db1-110">Resolves a module within an assembly or a linked (not embedded) resource file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19db1-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="19db1-111">Remarks</span></span>  
 <span data-ttu-id="19db1-112">`IHostAssemblyStore` предоставляет способ для узла для загрузки сборок, эффективно исходя из удостоверения сборки.</span><span class="sxs-lookup"><span data-stu-id="19db1-112">`IHostAssemblyStore` provides a way for a host to load assemblies efficiently based on assembly identity.</span></span> <span data-ttu-id="19db1-113">Сервер загружает сборки, возвращая `IStream` экземпляров, которые указывают непосредственно на байты.</span><span class="sxs-lookup"><span data-stu-id="19db1-113">The host loads assemblies by returning `IStream` instances that point directly at the bytes.</span></span>  
  
 <span data-ttu-id="19db1-114">Среда CLR определяет, реализован ли узел `IHostAssemblyStore` путем вызова `IHostAssemblyManager::GetNonHostAssemblyStores` при инициализации.</span><span class="sxs-lookup"><span data-stu-id="19db1-114">The CLR determines whether a host has implemented `IHostAssemblyStore` by calling `IHostAssemblyManager::GetNonHostAssemblyStores` upon initialization.</span></span> <span data-ttu-id="19db1-115">Это позволяет узлу, например, для управления привязкой к пользовательским сборкам, но полагаются на среду выполнения для привязки к сборкам .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="19db1-115">This allows the host, for example, to control binding to user assemblies, but to rely on the runtime to bind to .NET Framework assemblies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19db1-116">В реализацию, предоставляя `IHostAssemblyStore`, узел указывает его намерения разрешить все сборки, на которые не ссылается `ICLRAssemblyReferenceList` возвращаемые `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span><span class="sxs-lookup"><span data-stu-id="19db1-116">In providing an implementation of `IHostAssemblyStore`, the host specifies its intent to resolve all assemblies that are not referenced by the `ICLRAssemblyReferenceList` returned from `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19db1-117">В .NET Framework версии 2.0, не позволяют для узла для загрузки образа в машинном коде сборки, предоставленное [генератором машинных образов (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) служебной программы.</span><span class="sxs-lookup"><span data-stu-id="19db1-117">The .NET Framework version 2.0 does not provide a way for the host to load the native image of an assembly, as provided by the [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19db1-118">Требования</span><span class="sxs-lookup"><span data-stu-id="19db1-118">Requirements</span></span>  
 <span data-ttu-id="19db1-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19db1-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19db1-120">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="19db1-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="19db1-121">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="19db1-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19db1-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19db1-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19db1-123">См. также</span><span class="sxs-lookup"><span data-stu-id="19db1-123">See also</span></span>
- [<span data-ttu-id="19db1-124">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="19db1-124">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="19db1-125">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="19db1-125">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="19db1-126">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="19db1-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
