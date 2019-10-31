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
ms.openlocfilehash: e74d49d71cfee51f8cb99645151aace3d02de0e8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126664"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="3aa4e-102">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="3aa4e-102">ICLRAssemblyReferenceList Interface</span></span>
<span data-ttu-id="3aa4e-103">Управляет списком сборок, загружаемых средой CLR, а не узлом.</span><span class="sxs-lookup"><span data-stu-id="3aa4e-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3aa4e-104">Методы</span><span class="sxs-lookup"><span data-stu-id="3aa4e-104">Methods</span></span>  
  
|<span data-ttu-id="3aa4e-105">Метод</span><span class="sxs-lookup"><span data-stu-id="3aa4e-105">Method</span></span>|<span data-ttu-id="3aa4e-106">Описание</span><span class="sxs-lookup"><span data-stu-id="3aa4e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3aa4e-107">Метод IsAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="3aa4e-107">IsAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="3aa4e-108">Возвращает значение, указывающее, ссылается ли указанный указатель на сборку в списке.</span><span class="sxs-lookup"><span data-stu-id="3aa4e-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="3aa4e-109">Метод IsStringAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="3aa4e-109">IsStringAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="3aa4e-110">Возвращает значение, указывающее, совпадает ли заданное имя с именем сборки в списке.</span><span class="sxs-lookup"><span data-stu-id="3aa4e-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3aa4e-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="3aa4e-111">Remarks</span></span>  
 <span data-ttu-id="3aa4e-112">Вызовите метод [ICLRAssemblyIdentityManager:: getclrassemblyreferencelist-](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) , чтобы получить указатель на экземпляр `ICLRAssemblyReferenceList`.</span><span class="sxs-lookup"><span data-stu-id="3aa4e-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3aa4e-113">Требования</span><span class="sxs-lookup"><span data-stu-id="3aa4e-113">Requirements</span></span>  
 <span data-ttu-id="3aa4e-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3aa4e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3aa4e-115">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3aa4e-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3aa4e-116">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3aa4e-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3aa4e-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3aa4e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aa4e-118">См. также</span><span class="sxs-lookup"><span data-stu-id="3aa4e-118">See also</span></span>

- [<span data-ttu-id="3aa4e-119">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="3aa4e-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="3aa4e-120">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="3aa4e-120">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="3aa4e-121">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="3aa4e-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
