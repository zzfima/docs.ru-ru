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
ms.openlocfilehash: db933716cc0602ecda5da8a72726408ae4910179
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129809"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="c2a60-102">Интерфейс IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="c2a60-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="c2a60-103">Предоставляет методы для осуществления обратных вызовов в подразделении.</span><span class="sxs-lookup"><span data-stu-id="c2a60-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="c2a60-104">*Подразделения* — это логический контейнер, в рамках процесса для объектов, которые совместно используют те же требования доступа потоке.</span><span class="sxs-lookup"><span data-stu-id="c2a60-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c2a60-105">Методы</span><span class="sxs-lookup"><span data-stu-id="c2a60-105">Methods</span></span>  
  
|<span data-ttu-id="c2a60-106">Метод</span><span class="sxs-lookup"><span data-stu-id="c2a60-106">Method</span></span>|<span data-ttu-id="c2a60-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c2a60-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c2a60-108">Метод DoCallback</span><span class="sxs-lookup"><span data-stu-id="c2a60-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="c2a60-109">Выполняет указанную функцию в подразделении.</span><span class="sxs-lookup"><span data-stu-id="c2a60-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c2a60-110">Требования</span><span class="sxs-lookup"><span data-stu-id="c2a60-110">Requirements</span></span>  
 <span data-ttu-id="c2a60-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2a60-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2a60-112">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c2a60-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c2a60-113">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c2a60-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2a60-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2a60-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2a60-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c2a60-115">See also</span></span>

- [<span data-ttu-id="c2a60-116">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="c2a60-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
