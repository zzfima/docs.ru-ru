---
title: "Интерфейс ICLRAssemblyReferenceList"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyReferenceList
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyReferenceList
helpviewer_keywords: ICLRAssemblyReferenceList interface [.NET Framework hosting]
ms.assetid: 5f890fdf-d22a-429e-a35f-135273d1a636
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4249616ca46fe5ef09dce4a3e245794a103298c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="29d07-102">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="29d07-102">ICLRAssemblyReferenceList Interface</span></span>
<span data-ttu-id="29d07-103">Управляет списком сборок, загружаемых средой CLR (CLR), а не приложением.</span><span class="sxs-lookup"><span data-stu-id="29d07-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="29d07-104">Методы</span><span class="sxs-lookup"><span data-stu-id="29d07-104">Methods</span></span>  
  
|<span data-ttu-id="29d07-105">Метод</span><span class="sxs-lookup"><span data-stu-id="29d07-105">Method</span></span>|<span data-ttu-id="29d07-106">Описание</span><span class="sxs-lookup"><span data-stu-id="29d07-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="29d07-107">Isassemblyreferenceinlist-метод</span><span class="sxs-lookup"><span data-stu-id="29d07-107">IsAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="29d07-108">Возвращает значение, указывающее, ссылается ли заданный указатель на сборку в списке.</span><span class="sxs-lookup"><span data-stu-id="29d07-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="29d07-109">Isstringassemblyreferenceinlist-метод</span><span class="sxs-lookup"><span data-stu-id="29d07-109">IsStringAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="29d07-110">Получает значение, указывающее, соответствует ли указанное имя, имя сборки в списке.</span><span class="sxs-lookup"><span data-stu-id="29d07-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29d07-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="29d07-111">Remarks</span></span>  
 <span data-ttu-id="29d07-112">Вызовите [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) метод, чтобы получить указатель на экземпляр `ICLRAssemblyReferenceList`.</span><span class="sxs-lookup"><span data-stu-id="29d07-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29d07-113">Требования</span><span class="sxs-lookup"><span data-stu-id="29d07-113">Requirements</span></span>  
 <span data-ttu-id="29d07-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29d07-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29d07-115">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="29d07-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="29d07-116">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="29d07-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="29d07-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29d07-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29d07-118">См. также</span><span class="sxs-lookup"><span data-stu-id="29d07-118">See Also</span></span>  
 [<span data-ttu-id="29d07-119">Iclrassemblyidentitymanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="29d07-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="29d07-120">IHostAssemblyStore-интерфейс</span><span class="sxs-lookup"><span data-stu-id="29d07-120">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 [<span data-ttu-id="29d07-121">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="29d07-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
