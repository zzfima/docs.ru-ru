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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 014e5c9951091046ae07374794743e82affcd5ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967743"
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="f1942-102">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="f1942-102">IHostControl Interface</span></span>
<span data-ttu-id="f1942-103">Предоставляет методы для настройки загрузки сборок, а также для определения интерфейсов поддерживает узла размещения.</span><span class="sxs-lookup"><span data-stu-id="f1942-103">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f1942-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f1942-104">Methods</span></span>  
  
|<span data-ttu-id="f1942-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f1942-105">Method</span></span>|<span data-ttu-id="f1942-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f1942-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f1942-107">Метод GetHostManager</span><span class="sxs-lookup"><span data-stu-id="f1942-107">GetHostManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="f1942-108">Получает указатель интерфейса для реализации интерфейса с указанным `IID`.</span><span class="sxs-lookup"><span data-stu-id="f1942-108">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="f1942-109">Метод SetAppDomainManager</span><span class="sxs-lookup"><span data-stu-id="f1942-109">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="f1942-110">Уведомляет ведущее приложение для создания домена приложения.</span><span class="sxs-lookup"><span data-stu-id="f1942-110">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f1942-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f1942-111">Requirements</span></span>  
 <span data-ttu-id="f1942-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1942-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1942-113">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f1942-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f1942-114">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f1942-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f1942-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1942-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1942-116">См. также</span><span class="sxs-lookup"><span data-stu-id="f1942-116">See also</span></span>

- <xref:System.AppDomainManager>
- [<span data-ttu-id="f1942-117">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="f1942-117">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="f1942-118">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="f1942-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="f1942-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="f1942-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
