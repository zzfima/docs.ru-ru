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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129809"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="b8a05-102">Интерфейс IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="b8a05-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="b8a05-103">Предоставляет методы для осуществления обратных вызовов в подразделении.</span><span class="sxs-lookup"><span data-stu-id="b8a05-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="b8a05-104">*Подразделения* — это логический контейнер, в рамках процесса для объектов, которые совместно используют те же требования доступа потоке.</span><span class="sxs-lookup"><span data-stu-id="b8a05-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b8a05-105">Методы</span><span class="sxs-lookup"><span data-stu-id="b8a05-105">Methods</span></span>  
  
|<span data-ttu-id="b8a05-106">Метод</span><span class="sxs-lookup"><span data-stu-id="b8a05-106">Method</span></span>|<span data-ttu-id="b8a05-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b8a05-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b8a05-108">Метод DoCallback</span><span class="sxs-lookup"><span data-stu-id="b8a05-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="b8a05-109">Выполняет указанную функцию в подразделении.</span><span class="sxs-lookup"><span data-stu-id="b8a05-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b8a05-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b8a05-110">Requirements</span></span>  
 <span data-ttu-id="b8a05-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8a05-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8a05-112">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b8a05-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b8a05-113">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b8a05-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="b8a05-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b8a05-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b8a05-115">См. также</span><span class="sxs-lookup"><span data-stu-id="b8a05-115">See also</span></span>

- [<span data-ttu-id="b8a05-116">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="b8a05-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
