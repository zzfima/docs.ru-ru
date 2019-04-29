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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 118345f246de3d7ee68d51cf37e8cdea9de1fdba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638532"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="0d4a3-102">Интерфейс ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="0d4a3-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="0d4a3-103">Предоставляет методы, позволяющие основному приложению получить проверочные идентификаторы сборки с помощью сборки удостоверяющие сведения, является внутренним для общеязыковой среды выполнения (CLR), без необходимости создания или понять этот идентификатор.</span><span class="sxs-lookup"><span data-stu-id="0d4a3-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0d4a3-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0d4a3-104">Methods</span></span>  
  
|<span data-ttu-id="0d4a3-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0d4a3-105">Method</span></span>|<span data-ttu-id="0d4a3-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0d4a3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0d4a3-107">Метод Get</span><span class="sxs-lookup"><span data-stu-id="0d4a3-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="0d4a3-108">Получает идентификатор сборки по указанному индексу.</span><span class="sxs-lookup"><span data-stu-id="0d4a3-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d4a3-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="0d4a3-109">Remarks</span></span>  
 <span data-ttu-id="0d4a3-110">Методы, такие как [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) возвращают `ICLRProbingAssemblyEnum` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="0d4a3-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d4a3-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0d4a3-111">Requirements</span></span>  
 <span data-ttu-id="0d4a3-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d4a3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d4a3-113">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0d4a3-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0d4a3-114">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0d4a3-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d4a3-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d4a3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d4a3-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0d4a3-116">See also</span></span>

- [<span data-ttu-id="0d4a3-117">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="0d4a3-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="0d4a3-118">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="0d4a3-118">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="0d4a3-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="0d4a3-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
