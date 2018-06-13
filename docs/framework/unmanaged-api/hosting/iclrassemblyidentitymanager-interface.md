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
ms.openlocfilehash: f3a58a9ec4ed9514e748ed6c8c21a404feed9560
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435671"
---
# <a name="iclrassemblyidentitymanager-interface"></a><span data-ttu-id="50e18-102">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="50e18-102">ICLRAssemblyIdentityManager Interface</span></span>
<span data-ttu-id="50e18-103">Предоставляет методы, поддерживающие обмен данными между узлом и среда CLR о сборках.</span><span class="sxs-lookup"><span data-stu-id="50e18-103">Provides methods that support communication between the host and the common language runtime (CLR) about assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="50e18-104">Методы</span><span class="sxs-lookup"><span data-stu-id="50e18-104">Methods</span></span>  
  
|<span data-ttu-id="50e18-105">Метод</span><span class="sxs-lookup"><span data-stu-id="50e18-105">Method</span></span>|<span data-ttu-id="50e18-106">Описание</span><span class="sxs-lookup"><span data-stu-id="50e18-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="50e18-107">Метод GetBindingIdentityFromFile</span><span class="sxs-lookup"><span data-stu-id="50e18-107">GetBindingIdentityFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|<span data-ttu-id="50e18-108">Возвращает удостоверение сборки привязки данных для сборки по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="50e18-108">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="50e18-109">Метод GetBindingIdentityFromStream</span><span class="sxs-lookup"><span data-stu-id="50e18-109">GetBindingIdentityFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|<span data-ttu-id="50e18-110">Возвращает данные идентификации канонической сборки для сборки в указанном потоке.</span><span class="sxs-lookup"><span data-stu-id="50e18-110">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="50e18-111">Метод GetCLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="50e18-111">GetCLRAssemblyReferenceList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|<span data-ttu-id="50e18-112">Возвращает [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) экземпляр из предоставленного списка частичных идентификаторов сборки.</span><span class="sxs-lookup"><span data-stu-id="50e18-112">Gets an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>|  
|[<span data-ttu-id="50e18-113">Метод GetProbingAssembliesFromReference</span><span class="sxs-lookup"><span data-stu-id="50e18-113">GetProbingAssembliesFromReference Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|<span data-ttu-id="50e18-114">Возвращает [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) перечислителя для идентификаторов сборки ссылается сборка с указанным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="50e18-114">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity.</span></span>|  
|[<span data-ttu-id="50e18-115">Метод GetReferencedAssembliesFromFile</span><span class="sxs-lookup"><span data-stu-id="50e18-115">GetReferencedAssembliesFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|<span data-ttu-id="50e18-116">Возвращает [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) экземпляр, содержащий список сборок, ссылки из данной сборки по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="50e18-116">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="50e18-117">Метод GetReferencedAssembliesFromStream</span><span class="sxs-lookup"><span data-stu-id="50e18-117">GetReferencedAssembliesFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|<span data-ttu-id="50e18-118">Возвращает указатель на `ICLRReferenceAssemblyEnum` объект, содержащий данные идентификации сборки для сборки ссылается сборка в указанном потоке.</span><span class="sxs-lookup"><span data-stu-id="50e18-118">Gets a pointer to an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="50e18-119">Метод IsStronglyNamed</span><span class="sxs-lookup"><span data-stu-id="50e18-119">IsStronglyNamed Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-isstronglynamed-method.md)|<span data-ttu-id="50e18-120">Возвращает значение, указывающее, является ли указанная сборка имеет строгое имя.</span><span class="sxs-lookup"><span data-stu-id="50e18-120">Gets a value that indicates whether the specified assembly is strongly named.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50e18-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="50e18-121">Remarks</span></span>  
 <span data-ttu-id="50e18-122">Используйте `ICLRAssemblyIdentityManager` для получения экземпляров `ICLRAssemblyReferenceList` и перечисления идентификаторов сборок.</span><span class="sxs-lookup"><span data-stu-id="50e18-122">Use `ICLRAssemblyIdentityManager` to get instances of `ICLRAssemblyReferenceList` and to enumerate assembly identities.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50e18-123">Требования</span><span class="sxs-lookup"><span data-stu-id="50e18-123">Requirements</span></span>  
 <span data-ttu-id="50e18-124">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50e18-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50e18-125">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="50e18-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="50e18-126">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="50e18-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50e18-127">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50e18-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50e18-128">См. также</span><span class="sxs-lookup"><span data-stu-id="50e18-128">See Also</span></span>  
 [<span data-ttu-id="50e18-129">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="50e18-129">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="50e18-130">Интерфейс ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="50e18-130">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 [<span data-ttu-id="50e18-131">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="50e18-131">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
