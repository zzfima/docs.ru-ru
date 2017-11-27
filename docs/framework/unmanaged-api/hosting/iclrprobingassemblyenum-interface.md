---
title: "Интерфейс ICLRProbingAssemblyEnum"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRProbingAssemblyEnum
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRProbingAssemblyEnum
helpviewer_keywords: ICLRProbingAssemblyEnum interface [.NET Framework hosting]
ms.assetid: e7d3ccab-b0f0-4872-8935-0ed72920171b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6d810ab6e62c6df1b00305947de552ecdbe82141
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="9e5ad-102">Интерфейс ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="9e5ad-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="9e5ad-103">Предоставляет методы, позволяющие основному приложению получить проверочные идентификаторы сборки с использованием данных удостоверение сборки, является внутренним для общеязыковой среды выполнения (CLR), без необходимости создания или понять их подлинность.</span><span class="sxs-lookup"><span data-stu-id="9e5ad-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9e5ad-104">Методы</span><span class="sxs-lookup"><span data-stu-id="9e5ad-104">Methods</span></span>  
  
|<span data-ttu-id="9e5ad-105">Метод</span><span class="sxs-lookup"><span data-stu-id="9e5ad-105">Method</span></span>|<span data-ttu-id="9e5ad-106">Описание</span><span class="sxs-lookup"><span data-stu-id="9e5ad-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9e5ad-107">GET-метод</span><span class="sxs-lookup"><span data-stu-id="9e5ad-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="9e5ad-108">Возвращает удостоверение сборки по указанному индексу.</span><span class="sxs-lookup"><span data-stu-id="9e5ad-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e5ad-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="9e5ad-109">Remarks</span></span>  
 <span data-ttu-id="9e5ad-110">Такие методы, как [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) возвращают `ICLRProbingAssemblyEnum` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="9e5ad-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e5ad-111">Требования</span><span class="sxs-lookup"><span data-stu-id="9e5ad-111">Requirements</span></span>  
 <span data-ttu-id="9e5ad-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e5ad-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e5ad-113">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9e5ad-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9e5ad-114">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9e5ad-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9e5ad-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e5ad-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e5ad-116">См. также</span><span class="sxs-lookup"><span data-stu-id="9e5ad-116">See Also</span></span>  
 [<span data-ttu-id="9e5ad-117">Iclrassemblyidentitymanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="9e5ad-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="9e5ad-118">ICLRAssemblyReferenceList-интерфейс</span><span class="sxs-lookup"><span data-stu-id="9e5ad-118">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="9e5ad-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="9e5ad-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
