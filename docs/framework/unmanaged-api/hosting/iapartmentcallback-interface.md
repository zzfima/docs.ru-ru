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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985519"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="635d0-102">Интерфейс IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="635d0-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="635d0-103">Предоставляет методы для осуществления обратных вызовов в подразделении.</span><span class="sxs-lookup"><span data-stu-id="635d0-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="635d0-104">*Подразделения* — это логический контейнер, в рамках процесса для объектов, которые совместно используют те же требования доступа потоке.</span><span class="sxs-lookup"><span data-stu-id="635d0-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="635d0-105">Методы</span><span class="sxs-lookup"><span data-stu-id="635d0-105">Methods</span></span>  
  
|<span data-ttu-id="635d0-106">Метод</span><span class="sxs-lookup"><span data-stu-id="635d0-106">Method</span></span>|<span data-ttu-id="635d0-107">Описание</span><span class="sxs-lookup"><span data-stu-id="635d0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="635d0-108">Метод DoCallback</span><span class="sxs-lookup"><span data-stu-id="635d0-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="635d0-109">Выполняет указанную функцию в подразделении.</span><span class="sxs-lookup"><span data-stu-id="635d0-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="635d0-110">Требования</span><span class="sxs-lookup"><span data-stu-id="635d0-110">Requirements</span></span>  
 <span data-ttu-id="635d0-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="635d0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="635d0-112">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="635d0-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="635d0-113">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="635d0-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="635d0-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="635d0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="635d0-115">См. также</span><span class="sxs-lookup"><span data-stu-id="635d0-115">See also</span></span>

- [<span data-ttu-id="635d0-116">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="635d0-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
