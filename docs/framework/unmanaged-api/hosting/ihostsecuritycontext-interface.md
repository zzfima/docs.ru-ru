---
title: Интерфейс IHostSecurityContext
ms.date: 03/30/2017
api_name:
- IHostSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext
helpviewer_keywords:
- IHostSecurityContext interface [.NET Framework hosting]
ms.assetid: 88e2eac0-8ccb-404f-abbc-287d55159842
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d71b7e1265110a70329377ce8ab7430e1943c49
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59124037"
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="ad5d3-102">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="ad5d3-102">IHostSecurityContext Interface</span></span>
<span data-ttu-id="ad5d3-103">Позволяет общеязыковой среды выполнения (CLR), чтобы сохранить сведения о контексте безопасности, реализованных в ведущем.</span><span class="sxs-lookup"><span data-stu-id="ad5d3-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ad5d3-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ad5d3-104">Methods</span></span>  
  
|<span data-ttu-id="ad5d3-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ad5d3-105">Method</span></span>|<span data-ttu-id="ad5d3-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ad5d3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ad5d3-107">Метод Capture</span><span class="sxs-lookup"><span data-stu-id="ad5d3-107">Capture Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|<span data-ttu-id="ad5d3-108">Возвращает точную копию `IHostSecurityContext` экземпляр, возвращаемый из вызова [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="ad5d3-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad5d3-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="ad5d3-109">Remarks</span></span>  
 <span data-ttu-id="ad5d3-110">Управляющее приложение может определять все доступ кода к маркерам потока кодом среды CLR и пользователя.</span><span class="sxs-lookup"><span data-stu-id="ad5d3-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="ad5d3-111">Также можно обеспечить, полную безопасность сведений о контексте передается через асинхронные операции или кодовые точки с ограниченным доступом.</span><span class="sxs-lookup"><span data-stu-id="ad5d3-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="ad5d3-112">`IHostSecurityContext` инкапсулирует эти сведения о контексте безопасности, который является непрозрачным для среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="ad5d3-112">`IHostSecurityContext` encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="ad5d3-113">Среда выполнения перехватывает эти сведения с помощью `Capture`, и перемещает ее в поток пула рабочих элементов диспетчеризации, выполнения метода завершения и модуль и класс конструкторы.</span><span class="sxs-lookup"><span data-stu-id="ad5d3-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad5d3-114">Требования</span><span class="sxs-lookup"><span data-stu-id="ad5d3-114">Requirements</span></span>  
 <span data-ttu-id="ad5d3-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad5d3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad5d3-116">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ad5d3-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ad5d3-117">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ad5d3-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ad5d3-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad5d3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad5d3-119">См. также</span><span class="sxs-lookup"><span data-stu-id="ad5d3-119">See also</span></span>

- [<span data-ttu-id="ad5d3-120">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="ad5d3-120">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="ad5d3-121">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="ad5d3-121">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="ad5d3-122">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="ad5d3-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
