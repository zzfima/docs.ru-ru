---
title: "Интерфейс ICLRAssemblyIdentityManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyIdentityManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyIdentityManager
helpviewer_keywords: ICLRAssemblyIdentityManager interface [.NET Framework hosting]
ms.assetid: 6a81c6fe-cc22-4062-ae27-d6eeee03a7b9
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 168c67eb701d7dfc461553cfe32ed43dcea5e844
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrassemblyidentitymanager-interface"></a><span data-ttu-id="905d4-102">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="905d4-102">ICLRAssemblyIdentityManager Interface</span></span>
<span data-ttu-id="905d4-103">Предоставляет методы, поддерживающие обмен данными между узлом и среда CLR о сборках.</span><span class="sxs-lookup"><span data-stu-id="905d4-103">Provides methods that support communication between the host and the common language runtime (CLR) about assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="905d4-104">Методы</span><span class="sxs-lookup"><span data-stu-id="905d4-104">Methods</span></span>  
  
|<span data-ttu-id="905d4-105">Метод</span><span class="sxs-lookup"><span data-stu-id="905d4-105">Method</span></span>|<span data-ttu-id="905d4-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="905d4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="905d4-107">Метод GetBindingIdentityFromFile</span><span class="sxs-lookup"><span data-stu-id="905d4-107">GetBindingIdentityFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|<span data-ttu-id="905d4-108">Возвращает удостоверение сборки привязки данных для сборки по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="905d4-108">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="905d4-109">Метод GetBindingIdentityFromStream</span><span class="sxs-lookup"><span data-stu-id="905d4-109">GetBindingIdentityFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|<span data-ttu-id="905d4-110">Возвращает данные идентификации канонической сборки для сборки в указанном потоке.</span><span class="sxs-lookup"><span data-stu-id="905d4-110">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="905d4-111">Метод GetCLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="905d4-111">GetCLRAssemblyReferenceList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|<span data-ttu-id="905d4-112">Возвращает [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) экземпляр из предоставленного списка частичных идентификаторов сборки.</span><span class="sxs-lookup"><span data-stu-id="905d4-112">Gets an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>|  
|[<span data-ttu-id="905d4-113">Метод GetProbingAssembliesFromReference</span><span class="sxs-lookup"><span data-stu-id="905d4-113">GetProbingAssembliesFromReference Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|<span data-ttu-id="905d4-114">Возвращает [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) перечислителя для идентификаторов сборки ссылается сборка с указанным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="905d4-114">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity.</span></span>|  
|[<span data-ttu-id="905d4-115">Метод GetReferencedAssembliesFromFile</span><span class="sxs-lookup"><span data-stu-id="905d4-115">GetReferencedAssembliesFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|<span data-ttu-id="905d4-116">Возвращает [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) экземпляр, содержащий список сборок, ссылки из данной сборки по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="905d4-116">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="905d4-117">Метод GetReferencedAssembliesFromStream</span><span class="sxs-lookup"><span data-stu-id="905d4-117">GetReferencedAssembliesFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|<span data-ttu-id="905d4-118">Возвращает указатель на `ICLRReferenceAssemblyEnum` объект, содержащий данные идентификации сборки для сборки ссылается сборка в указанном потоке.</span><span class="sxs-lookup"><span data-stu-id="905d4-118">Gets a pointer to an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="905d4-119">Метод IsStronglyNamed</span><span class="sxs-lookup"><span data-stu-id="905d4-119">IsStronglyNamed Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-isstronglynamed-method.md)|<span data-ttu-id="905d4-120">Возвращает значение, указывающее, является ли указанная сборка имеет строгое имя.</span><span class="sxs-lookup"><span data-stu-id="905d4-120">Gets a value that indicates whether the specified assembly is strongly named.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="905d4-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="905d4-121">Remarks</span></span>  
 <span data-ttu-id="905d4-122">Используйте `ICLRAssemblyIdentityManager` для получения экземпляров `ICLRAssemblyReferenceList` и перечисления идентификаторов сборок.</span><span class="sxs-lookup"><span data-stu-id="905d4-122">Use `ICLRAssemblyIdentityManager` to get instances of `ICLRAssemblyReferenceList` and to enumerate assembly identities.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="905d4-123">Требования</span><span class="sxs-lookup"><span data-stu-id="905d4-123">Requirements</span></span>  
 <span data-ttu-id="905d4-124">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="905d4-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="905d4-125">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="905d4-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="905d4-126">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="905d4-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="905d4-127">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="905d4-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="905d4-128">См. также</span><span class="sxs-lookup"><span data-stu-id="905d4-128">See Also</span></span>  
 [<span data-ttu-id="905d4-129">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="905d4-129">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="905d4-130">Интерфейс ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="905d4-130">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 [<span data-ttu-id="905d4-131">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="905d4-131">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
