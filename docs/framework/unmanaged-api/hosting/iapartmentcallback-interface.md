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
ms.openlocfilehash: ffa06fd42b5cfa09817bae9f0b3a3810e30f99c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430971"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="8c0bc-102">Интерфейс IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="8c0bc-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="8c0bc-103">Предоставляет методы для осуществления обратных вызовов в подразделении.</span><span class="sxs-lookup"><span data-stu-id="8c0bc-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="8c0bc-104">*Подразделения* — это логический контейнер, в рамках процесса для объектов, которые совместно используют те же требования доступа потока.</span><span class="sxs-lookup"><span data-stu-id="8c0bc-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8c0bc-105">Методы</span><span class="sxs-lookup"><span data-stu-id="8c0bc-105">Methods</span></span>  
  
|<span data-ttu-id="8c0bc-106">Метод</span><span class="sxs-lookup"><span data-stu-id="8c0bc-106">Method</span></span>|<span data-ttu-id="8c0bc-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8c0bc-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8c0bc-108">Метод DoCallback</span><span class="sxs-lookup"><span data-stu-id="8c0bc-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="8c0bc-109">Выполняет заданную функцию в подразделении.</span><span class="sxs-lookup"><span data-stu-id="8c0bc-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8c0bc-110">Требования</span><span class="sxs-lookup"><span data-stu-id="8c0bc-110">Requirements</span></span>  
 <span data-ttu-id="8c0bc-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c0bc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c0bc-112">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8c0bc-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8c0bc-113">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8c0bc-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8c0bc-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c0bc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c0bc-115">См. также</span><span class="sxs-lookup"><span data-stu-id="8c0bc-115">See Also</span></span>  
 [<span data-ttu-id="8c0bc-116">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="8c0bc-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
