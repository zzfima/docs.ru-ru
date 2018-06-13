---
title: Интерфейс IAppDomainBinding
ms.date: 03/30/2017
api_name:
- IAppDomainBinding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IAppDomainBinding
helpviewer_keywords:
- IAppDomainBinding interface [.NET Framework hosting]
ms.assetid: 368881ab-c4ea-4731-bf22-c596aac7c66c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6761ff204d299bc2db84e2e80d988306125a110
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430825"
---
# <a name="iappdomainbinding-interface"></a><span data-ttu-id="68e3c-102">Интерфейс IAppDomainBinding</span><span class="sxs-lookup"><span data-stu-id="68e3c-102">IAppDomainBinding Interface</span></span>
<span data-ttu-id="68e3c-103">Предоставляет метод, который вызывается общеязыковой среды выполнения (CLR) для уведомления ведущего приложения о том, что домен приложения был создан.</span><span class="sxs-lookup"><span data-stu-id="68e3c-103">Provides a method that is called by the common language runtime (CLR) to notify the host application that an application domain has been created.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="68e3c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="68e3c-104">Methods</span></span>  
  
|<span data-ttu-id="68e3c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="68e3c-105">Method</span></span>|<span data-ttu-id="68e3c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="68e3c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="68e3c-107">Метод OnAppDomain</span><span class="sxs-lookup"><span data-stu-id="68e3c-107">OnAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-onappdomain-method.md)|<span data-ttu-id="68e3c-108">Вызывается общеязыковой среды выполнения (CLR) для уведомления узла, что домен приложения был создан.</span><span class="sxs-lookup"><span data-stu-id="68e3c-108">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="68e3c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="68e3c-109">Requirements</span></span>  
 <span data-ttu-id="68e3c-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68e3c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68e3c-111">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="68e3c-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="68e3c-112">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="68e3c-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68e3c-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68e3c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68e3c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="68e3c-114">See Also</span></span>  
 [<span data-ttu-id="68e3c-115">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="68e3c-115">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
