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
ms.openlocfilehash: 1c2b383abdc67546749867de154a00fda244b3ad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660025"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="636ec-102">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="636ec-102">ICLRAssemblyReferenceList Interface</span></span>
<span data-ttu-id="636ec-103">Управляет списком сборок, загружаемых средой CLR (CLR), а не приложением.</span><span class="sxs-lookup"><span data-stu-id="636ec-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="636ec-104">Методы</span><span class="sxs-lookup"><span data-stu-id="636ec-104">Methods</span></span>  
  
|<span data-ttu-id="636ec-105">Метод</span><span class="sxs-lookup"><span data-stu-id="636ec-105">Method</span></span>|<span data-ttu-id="636ec-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="636ec-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="636ec-107">Метод IsAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="636ec-107">IsAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="636ec-108">Получает значение, указывающее, ссылается ли заданный указатель на сборку в списке.</span><span class="sxs-lookup"><span data-stu-id="636ec-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="636ec-109">Метод IsStringAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="636ec-109">IsStringAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="636ec-110">Получает значение, указывающее, соответствует ли указанное имя, имя сборки в списке.</span><span class="sxs-lookup"><span data-stu-id="636ec-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="636ec-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="636ec-111">Remarks</span></span>  
 <span data-ttu-id="636ec-112">Вызовите [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) способ получить указатель на экземпляр `ICLRAssemblyReferenceList`.</span><span class="sxs-lookup"><span data-stu-id="636ec-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="636ec-113">Требования</span><span class="sxs-lookup"><span data-stu-id="636ec-113">Requirements</span></span>  
 <span data-ttu-id="636ec-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="636ec-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="636ec-115">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="636ec-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="636ec-116">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="636ec-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="636ec-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="636ec-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="636ec-118">См. также</span><span class="sxs-lookup"><span data-stu-id="636ec-118">See also</span></span>
- [<span data-ttu-id="636ec-119">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="636ec-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="636ec-120">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="636ec-120">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="636ec-121">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="636ec-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
