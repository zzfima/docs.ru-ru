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
ms.openlocfilehash: e2c3a3057003d0035bfcb096a94c84d610e3056f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134190"
---
# <a name="iappdomainbinding-interface"></a><span data-ttu-id="f9a9e-102">Интерфейс IAppDomainBinding</span><span class="sxs-lookup"><span data-stu-id="f9a9e-102">IAppDomainBinding Interface</span></span>
<span data-ttu-id="f9a9e-103">Предоставляет метод, который вызывается общеязыковой среды выполнения (CLR), для уведомления ведущего приложения о том, что домен приложения был создан.</span><span class="sxs-lookup"><span data-stu-id="f9a9e-103">Provides a method that is called by the common language runtime (CLR) to notify the host application that an application domain has been created.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f9a9e-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f9a9e-104">Methods</span></span>  
  
|<span data-ttu-id="f9a9e-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f9a9e-105">Method</span></span>|<span data-ttu-id="f9a9e-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f9a9e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f9a9e-107">Метод OnAppDomain</span><span class="sxs-lookup"><span data-stu-id="f9a9e-107">OnAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-onappdomain-method.md)|<span data-ttu-id="f9a9e-108">Вызывается общеязыковой среды выполнения (CLR), для уведомления узла о том, что домен приложения был создан.</span><span class="sxs-lookup"><span data-stu-id="f9a9e-108">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f9a9e-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f9a9e-109">Requirements</span></span>  
 <span data-ttu-id="f9a9e-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9a9e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9a9e-111">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f9a9e-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f9a9e-112">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f9a9e-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="f9a9e-113">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f9a9e-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f9a9e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f9a9e-114">See also</span></span>

- [<span data-ttu-id="f9a9e-115">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="f9a9e-115">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
