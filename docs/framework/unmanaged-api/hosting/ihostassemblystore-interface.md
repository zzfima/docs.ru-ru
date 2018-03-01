---
title: "Интерфейс IHostAssemblyStore"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c795d4baa3030817299f23c3dadf4caf7a5edc5a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihostassemblystore-interface"></a><span data-ttu-id="69559-102">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="69559-102">IHostAssemblyStore Interface</span></span>
<span data-ttu-id="69559-103">Предоставляет методы, позволяющие основному приложению загружать сборки и модули независимо от общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="69559-103">Provides methods that allow a host to load assemblies and modules independently of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="69559-104">Методы</span><span class="sxs-lookup"><span data-stu-id="69559-104">Methods</span></span>  
  
|<span data-ttu-id="69559-105">Метод</span><span class="sxs-lookup"><span data-stu-id="69559-105">Method</span></span>|<span data-ttu-id="69559-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="69559-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="69559-107">Метод ProvideAssembly</span><span class="sxs-lookup"><span data-stu-id="69559-107">ProvideAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|<span data-ttu-id="69559-108">Возвращает ссылку на сборку, которая не ссылается [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) возвращается из вызова [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span><span class="sxs-lookup"><span data-stu-id="69559-108">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) returned from a call to [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span>|  
|[<span data-ttu-id="69559-109">Метод ProvideModule</span><span class="sxs-lookup"><span data-stu-id="69559-109">ProvideModule Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|<span data-ttu-id="69559-110">Разрешает модуль в сборку или связанный файл ресурсов (а не внедренные).</span><span class="sxs-lookup"><span data-stu-id="69559-110">Resolves a module within an assembly or a linked (not embedded) resource file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69559-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="69559-111">Remarks</span></span>  
 <span data-ttu-id="69559-112">`IHostAssemblyStore`предоставляет способ для узла для загрузки сборок, эффективно исходя из удостоверения сборки.</span><span class="sxs-lookup"><span data-stu-id="69559-112">`IHostAssemblyStore` provides a way for a host to load assemblies efficiently based on assembly identity.</span></span> <span data-ttu-id="69559-113">Основное приложение загружает сборки, возвращая `IStream` экземпляры, которые указывают непосредственно на байты.</span><span class="sxs-lookup"><span data-stu-id="69559-113">The host loads assemblies by returning `IStream` instances that point directly at the bytes.</span></span>  
  
 <span data-ttu-id="69559-114">Среда CLR определяет реализовал ли узел `IHostAssemblyStore` путем вызова `IHostAssemblyManager::GetNonHostAssemblyStores` при инициализации.</span><span class="sxs-lookup"><span data-stu-id="69559-114">The CLR determines whether a host has implemented `IHostAssemblyStore` by calling `IHostAssemblyManager::GetNonHostAssemblyStores` upon initialization.</span></span> <span data-ttu-id="69559-115">Это позволяет узлу, например, для управления с привязкой к пользовательским сборкам, но полагаются на среду выполнения для привязки к сборкам .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="69559-115">This allows the host, for example, to control binding to user assemblies, but to rely on the runtime to bind to .NET Framework assemblies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69559-116">В реализации, предоставляя `IHostAssemblyStore`, узел указывает, ее планируется устранить все сборки, на которые не ссылается `ICLRAssemblyReferenceList` , возвращенные `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span><span class="sxs-lookup"><span data-stu-id="69559-116">In providing an implementation of `IHostAssemblyStore`, the host specifies its intent to resolve all assemblies that are not referenced by the `ICLRAssemblyReferenceList` returned from `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69559-117">.NET Framework версии 2.0 не предоставляет способ для узла для загрузки образа в машинном коде для сборки, в соответствии со [генератором машинных образов (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) программы.</span><span class="sxs-lookup"><span data-stu-id="69559-117">The .NET Framework version 2.0 does not provide a way for the host to load the native image of an assembly, as provided by the [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69559-118">Требования</span><span class="sxs-lookup"><span data-stu-id="69559-118">Requirements</span></span>  
 <span data-ttu-id="69559-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69559-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69559-120">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="69559-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="69559-121">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="69559-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="69559-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69559-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69559-123">См. также</span><span class="sxs-lookup"><span data-stu-id="69559-123">See Also</span></span>  
 [<span data-ttu-id="69559-124">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="69559-124">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="69559-125">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="69559-125">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="69559-126">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="69559-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
