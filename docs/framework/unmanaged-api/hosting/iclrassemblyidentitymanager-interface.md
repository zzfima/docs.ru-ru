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
ms.openlocfilehash: 8d7fe632941c4cf0c20841ece390d2f41f28337d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrassemblyidentitymanager-interface"></a><span data-ttu-id="a7689-102">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="a7689-102">ICLRAssemblyIdentityManager Interface</span></span>
<span data-ttu-id="a7689-103">Предоставляет методы, поддерживающие обмен данными между узлом и среда CLR о сборках.</span><span class="sxs-lookup"><span data-stu-id="a7689-103">Provides methods that support communication between the host and the common language runtime (CLR) about assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a7689-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a7689-104">Methods</span></span>  
  
|<span data-ttu-id="a7689-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a7689-105">Method</span></span>|<span data-ttu-id="a7689-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a7689-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a7689-107">Getbindingidentityfromfile-метод</span><span class="sxs-lookup"><span data-stu-id="a7689-107">GetBindingIdentityFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|<span data-ttu-id="a7689-108">Возвращает удостоверение сборки привязки данных для сборки по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="a7689-108">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="a7689-109">Getbindingidentityfromstream-метод</span><span class="sxs-lookup"><span data-stu-id="a7689-109">GetBindingIdentityFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|<span data-ttu-id="a7689-110">Возвращает данные идентификации канонической сборки для сборки в указанном потоке.</span><span class="sxs-lookup"><span data-stu-id="a7689-110">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="a7689-111">Getclrassemblyreferencelist-метод</span><span class="sxs-lookup"><span data-stu-id="a7689-111">GetCLRAssemblyReferenceList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|<span data-ttu-id="a7689-112">Возвращает [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) экземпляр из предоставленного списка частичных идентификаторов сборки.</span><span class="sxs-lookup"><span data-stu-id="a7689-112">Gets an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>|  
|[<span data-ttu-id="a7689-113">Getprobingassembliesfromreference-метод</span><span class="sxs-lookup"><span data-stu-id="a7689-113">GetProbingAssembliesFromReference Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|<span data-ttu-id="a7689-114">Возвращает [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) перечислителя для идентификаторов сборки ссылается сборка с указанным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="a7689-114">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity.</span></span>|  
|[<span data-ttu-id="a7689-115">Метод GetReferencedAssembliesFromFile</span><span class="sxs-lookup"><span data-stu-id="a7689-115">GetReferencedAssembliesFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|<span data-ttu-id="a7689-116">Возвращает [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) экземпляр, содержащий список сборок, ссылки из данной сборки по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="a7689-116">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="a7689-117">Getreferencedassembliesfromstream-метод</span><span class="sxs-lookup"><span data-stu-id="a7689-117">GetReferencedAssembliesFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|<span data-ttu-id="a7689-118">Возвращает указатель на `ICLRReferenceAssemblyEnum` объект, содержащий данные идентификации сборки для сборки ссылается сборка в указанном потоке.</span><span class="sxs-lookup"><span data-stu-id="a7689-118">Gets a pointer to an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="a7689-119">Isstronglynamed-метод</span><span class="sxs-lookup"><span data-stu-id="a7689-119">IsStronglyNamed Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-isstronglynamed-method.md)|<span data-ttu-id="a7689-120">Возвращает значение, указывающее, является ли указанная сборка имеет строгое имя.</span><span class="sxs-lookup"><span data-stu-id="a7689-120">Gets a value that indicates whether the specified assembly is strongly named.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7689-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="a7689-121">Remarks</span></span>  
 <span data-ttu-id="a7689-122">Используйте `ICLRAssemblyIdentityManager` для получения экземпляров `ICLRAssemblyReferenceList` и перечисления идентификаторов сборок.</span><span class="sxs-lookup"><span data-stu-id="a7689-122">Use `ICLRAssemblyIdentityManager` to get instances of `ICLRAssemblyReferenceList` and to enumerate assembly identities.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7689-123">Требования</span><span class="sxs-lookup"><span data-stu-id="a7689-123">Requirements</span></span>  
 <span data-ttu-id="a7689-124">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7689-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7689-125">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a7689-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a7689-126">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a7689-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a7689-127">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7689-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7689-128">См. также</span><span class="sxs-lookup"><span data-stu-id="a7689-128">See Also</span></span>  
 [<span data-ttu-id="a7689-129">ICLRAssemblyReferenceList-интерфейс</span><span class="sxs-lookup"><span data-stu-id="a7689-129">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="a7689-130">ICLRProbingAssemblyEnum-интерфейс</span><span class="sxs-lookup"><span data-stu-id="a7689-130">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 [<span data-ttu-id="a7689-131">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="a7689-131">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
