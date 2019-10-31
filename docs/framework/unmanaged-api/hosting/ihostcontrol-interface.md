---
title: Интерфейс IHostControl
ms.date: 03/30/2017
api_name:
- IHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl
helpviewer_keywords:
- IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type:
- apiref
ms.openlocfilehash: 444a78705c61d5a53764f55185ef1a907830bd71
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195884"
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="56c3b-102">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="56c3b-102">IHostControl Interface</span></span>
<span data-ttu-id="56c3b-103">Предоставляет методы для настройки загрузки сборок и для определения того, какие интерфейсы размещения поддерживает узел.</span><span class="sxs-lookup"><span data-stu-id="56c3b-103">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="56c3b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="56c3b-104">Methods</span></span>  
  
|<span data-ttu-id="56c3b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="56c3b-105">Method</span></span>|<span data-ttu-id="56c3b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="56c3b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="56c3b-107">Метод GetHostManager</span><span class="sxs-lookup"><span data-stu-id="56c3b-107">GetHostManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="56c3b-108">Возвращает указатель интерфейса на реализацию интерфейса узла с указанным `IID`.</span><span class="sxs-lookup"><span data-stu-id="56c3b-108">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="56c3b-109">Метод SetAppDomainManager</span><span class="sxs-lookup"><span data-stu-id="56c3b-109">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="56c3b-110">Уведомляет узел о том, что домен приложения создан.</span><span class="sxs-lookup"><span data-stu-id="56c3b-110">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="56c3b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="56c3b-111">Requirements</span></span>  
 <span data-ttu-id="56c3b-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56c3b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56c3b-113">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="56c3b-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="56c3b-114">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="56c3b-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="56c3b-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56c3b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56c3b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="56c3b-116">See also</span></span>

- <xref:System.AppDomainManager>
- [<span data-ttu-id="56c3b-117">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="56c3b-117">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="56c3b-118">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="56c3b-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="56c3b-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="56c3b-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
