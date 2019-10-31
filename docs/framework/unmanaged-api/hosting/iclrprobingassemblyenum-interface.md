---
title: Интерфейс ICLRProbingAssemblyEnum
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum
helpviewer_keywords:
- ICLRProbingAssemblyEnum interface [.NET Framework hosting]
ms.assetid: e7d3ccab-b0f0-4872-8935-0ed72920171b
topic_type:
- apiref
ms.openlocfilehash: e1459c1604f3f8f043fd9b61533235ab7861c910
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120560"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="3e476-102">Интерфейс ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="3e476-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="3e476-103">Предоставляет методы, позволяющие узлу получить идентификаторы проверки сборки с помощью сведений об удостоверении сборки, которые являются внутренними для среды CLR, без необходимости создавать или понимать это удостоверение.</span><span class="sxs-lookup"><span data-stu-id="3e476-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3e476-104">Методы</span><span class="sxs-lookup"><span data-stu-id="3e476-104">Methods</span></span>  
  
|<span data-ttu-id="3e476-105">Метод</span><span class="sxs-lookup"><span data-stu-id="3e476-105">Method</span></span>|<span data-ttu-id="3e476-106">Описание</span><span class="sxs-lookup"><span data-stu-id="3e476-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3e476-107">Метод Get</span><span class="sxs-lookup"><span data-stu-id="3e476-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="3e476-108">Возвращает удостоверение сборки по указанному индексу.</span><span class="sxs-lookup"><span data-stu-id="3e476-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e476-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="3e476-109">Remarks</span></span>  
 <span data-ttu-id="3e476-110">Методы, такие как [ICLRAssemblyIdentityManager:: жетпробингассемблиесфромреференце](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) , возвращают `ICLRProbingAssemblyEnum` экземпляр.</span><span class="sxs-lookup"><span data-stu-id="3e476-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e476-111">Требования</span><span class="sxs-lookup"><span data-stu-id="3e476-111">Requirements</span></span>  
 <span data-ttu-id="3e476-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e476-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e476-113">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3e476-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3e476-114">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3e476-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3e476-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e476-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e476-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3e476-116">See also</span></span>

- [<span data-ttu-id="3e476-117">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="3e476-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="3e476-118">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="3e476-118">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="3e476-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="3e476-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
