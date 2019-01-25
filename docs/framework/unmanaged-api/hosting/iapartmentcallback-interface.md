---
title: Интерфейс IApartmentCallback
ms.date: 03/30/2017
api_name:
- IApartmentCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IApartmentCallback
helpviewer_keywords:
- IApartmentCallback interface [.NET Framework hosting]
ms.assetid: 57c33c58-bf0b-4533-b569-e6a682d02cba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc3f9e8c581bc95bea8cfeb549177966eae22a43
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584497"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="b90af-102">Интерфейс IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="b90af-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="b90af-103">Предоставляет методы для осуществления обратных вызовов в подразделении.</span><span class="sxs-lookup"><span data-stu-id="b90af-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="b90af-104">*Подразделения* — это логический контейнер, в рамках процесса для объектов, которые совместно используют те же требования доступа потоке.</span><span class="sxs-lookup"><span data-stu-id="b90af-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b90af-105">Методы</span><span class="sxs-lookup"><span data-stu-id="b90af-105">Methods</span></span>  
  
|<span data-ttu-id="b90af-106">Метод</span><span class="sxs-lookup"><span data-stu-id="b90af-106">Method</span></span>|<span data-ttu-id="b90af-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b90af-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b90af-108">Метод DoCallback</span><span class="sxs-lookup"><span data-stu-id="b90af-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="b90af-109">Выполняет указанную функцию в подразделении.</span><span class="sxs-lookup"><span data-stu-id="b90af-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b90af-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b90af-110">Requirements</span></span>  
 <span data-ttu-id="b90af-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b90af-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b90af-112">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b90af-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b90af-113">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b90af-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b90af-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b90af-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b90af-115">См. также</span><span class="sxs-lookup"><span data-stu-id="b90af-115">See also</span></span>
- [<span data-ttu-id="b90af-116">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="b90af-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
