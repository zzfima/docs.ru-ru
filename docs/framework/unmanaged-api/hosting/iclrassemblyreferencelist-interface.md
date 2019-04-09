---
title: Интерфейс ICLRAssemblyReferenceList
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList
helpviewer_keywords:
- ICLRAssemblyReferenceList interface [.NET Framework hosting]
ms.assetid: 5f890fdf-d22a-429e-a35f-135273d1a636
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 43c40e833e3a250239e9e90667196a2a74a96e0b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187659"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="b6b10-102">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="b6b10-102">ICLRAssemblyReferenceList Interface</span></span>
<span data-ttu-id="b6b10-103">Управляет списком сборок, загружаемых средой CLR (CLR), а не приложением.</span><span class="sxs-lookup"><span data-stu-id="b6b10-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b6b10-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b6b10-104">Methods</span></span>  
  
|<span data-ttu-id="b6b10-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b6b10-105">Method</span></span>|<span data-ttu-id="b6b10-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b6b10-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b6b10-107">Метод IsAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="b6b10-107">IsAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="b6b10-108">Получает значение, указывающее, ссылается ли заданный указатель на сборку в списке.</span><span class="sxs-lookup"><span data-stu-id="b6b10-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="b6b10-109">Метод IsStringAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="b6b10-109">IsStringAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="b6b10-110">Получает значение, указывающее, соответствует ли указанное имя, имя сборки в списке.</span><span class="sxs-lookup"><span data-stu-id="b6b10-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6b10-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="b6b10-111">Remarks</span></span>  
 <span data-ttu-id="b6b10-112">Вызовите [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) способ получить указатель на экземпляр `ICLRAssemblyReferenceList`.</span><span class="sxs-lookup"><span data-stu-id="b6b10-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6b10-113">Требования</span><span class="sxs-lookup"><span data-stu-id="b6b10-113">Requirements</span></span>  
 <span data-ttu-id="b6b10-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6b10-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6b10-115">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b6b10-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b6b10-116">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b6b10-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="b6b10-117">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b6b10-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b6b10-118">См. также</span><span class="sxs-lookup"><span data-stu-id="b6b10-118">See also</span></span>

- [<span data-ttu-id="b6b10-119">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="b6b10-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="b6b10-120">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="b6b10-120">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="b6b10-121">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="b6b10-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
