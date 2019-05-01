---
title: Интерфейс ICLRAssemblyIdentityManager
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager
helpviewer_keywords:
- ICLRAssemblyIdentityManager interface [.NET Framework hosting]
ms.assetid: 6a81c6fe-cc22-4062-ae27-d6eeee03a7b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b209e568b1e65ed785155d045cd48d1248672da
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985040"
---
# <a name="iclrassemblyidentitymanager-interface"></a><span data-ttu-id="dc747-102">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="dc747-102">ICLRAssemblyIdentityManager Interface</span></span>
<span data-ttu-id="dc747-103">Предоставляет методы, поддерживающие обмен данными между узлом и среда CLR (CLR) о сборках.</span><span class="sxs-lookup"><span data-stu-id="dc747-103">Provides methods that support communication between the host and the common language runtime (CLR) about assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dc747-104">Методы</span><span class="sxs-lookup"><span data-stu-id="dc747-104">Methods</span></span>  
  
|<span data-ttu-id="dc747-105">Метод</span><span class="sxs-lookup"><span data-stu-id="dc747-105">Method</span></span>|<span data-ttu-id="dc747-106">Описание</span><span class="sxs-lookup"><span data-stu-id="dc747-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dc747-107">Метод GetBindingIdentityFromFile</span><span class="sxs-lookup"><span data-stu-id="dc747-107">GetBindingIdentityFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|<span data-ttu-id="dc747-108">Получает идентификатор сборки привязка данных для сборки по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="dc747-108">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="dc747-109">Метод GetBindingIdentityFromStream</span><span class="sxs-lookup"><span data-stu-id="dc747-109">GetBindingIdentityFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|<span data-ttu-id="dc747-110">Получает данные идентификации канонической сборки для сборки в заданном потоке.</span><span class="sxs-lookup"><span data-stu-id="dc747-110">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="dc747-111">Метод GetCLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="dc747-111">GetCLRAssemblyReferenceList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|<span data-ttu-id="dc747-112">Получает [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) экземпляр из предоставленного списка частичных идентификаторов сборки.</span><span class="sxs-lookup"><span data-stu-id="dc747-112">Gets an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>|  
|[<span data-ttu-id="dc747-113">Метод GetProbingAssembliesFromReference</span><span class="sxs-lookup"><span data-stu-id="dc747-113">GetProbingAssembliesFromReference Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|<span data-ttu-id="dc747-114">Получает [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) перечислителя для идентификаторов сборки ссылается сборка с указанным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="dc747-114">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity.</span></span>|  
|[<span data-ttu-id="dc747-115">Метод GetReferencedAssembliesFromFile</span><span class="sxs-lookup"><span data-stu-id="dc747-115">GetReferencedAssembliesFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|<span data-ttu-id="dc747-116">Получает [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) экземпляр, содержащий список сборок, указанных с помощью сборки по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="dc747-116">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="dc747-117">Метод GetReferencedAssembliesFromStream</span><span class="sxs-lookup"><span data-stu-id="dc747-117">GetReferencedAssembliesFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|<span data-ttu-id="dc747-118">Возвращает указатель на `ICLRReferenceAssemblyEnum` объект, содержащий данные идентификации сборки для сборки ссылается сборка в указанном потоке.</span><span class="sxs-lookup"><span data-stu-id="dc747-118">Gets a pointer to an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="dc747-119">Метод IsStronglyNamed</span><span class="sxs-lookup"><span data-stu-id="dc747-119">IsStronglyNamed Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-isstronglynamed-method.md)|<span data-ttu-id="dc747-120">Получает значение, указывающее, является ли указанная сборка имеет строгое имя.</span><span class="sxs-lookup"><span data-stu-id="dc747-120">Gets a value that indicates whether the specified assembly is strongly named.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc747-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="dc747-121">Remarks</span></span>  
 <span data-ttu-id="dc747-122">Используйте `ICLRAssemblyIdentityManager` получать экземпляры `ICLRAssemblyReferenceList` и перечислить идентификаторы сборок.</span><span class="sxs-lookup"><span data-stu-id="dc747-122">Use `ICLRAssemblyIdentityManager` to get instances of `ICLRAssemblyReferenceList` and to enumerate assembly identities.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc747-123">Требования</span><span class="sxs-lookup"><span data-stu-id="dc747-123">Requirements</span></span>  
 <span data-ttu-id="dc747-124">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc747-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc747-125">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dc747-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dc747-126">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dc747-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dc747-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc747-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc747-128">См. также</span><span class="sxs-lookup"><span data-stu-id="dc747-128">See also</span></span>

- [<span data-ttu-id="dc747-129">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="dc747-129">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="dc747-130">Интерфейс ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="dc747-130">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="dc747-131">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="dc747-131">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
