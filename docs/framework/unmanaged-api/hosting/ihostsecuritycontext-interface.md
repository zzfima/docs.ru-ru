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
ms.openlocfilehash: 2c2500f013584ef4722ceaaaee91d5db54991639
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="1b6d2-102">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="1b6d2-102">IHostSecurityContext Interface</span></span>
<span data-ttu-id="1b6d2-103">Позволяет общеязыковая среда выполнения (CLR), чтобы сохранить сведения о контексте безопасности, реализуемых основным приложением.</span><span class="sxs-lookup"><span data-stu-id="1b6d2-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1b6d2-104">Методы</span><span class="sxs-lookup"><span data-stu-id="1b6d2-104">Methods</span></span>  
  
|<span data-ttu-id="1b6d2-105">Метод</span><span class="sxs-lookup"><span data-stu-id="1b6d2-105">Method</span></span>|<span data-ttu-id="1b6d2-106">Описание</span><span class="sxs-lookup"><span data-stu-id="1b6d2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1b6d2-107">Метод Capture</span><span class="sxs-lookup"><span data-stu-id="1b6d2-107">Capture Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|<span data-ttu-id="1b6d2-108">Возвращает точную копию `IHostSecurityContext` экземпляр возвращен из вызова [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="1b6d2-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b6d2-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="1b6d2-109">Remarks</span></span>  
 <span data-ttu-id="1b6d2-110">Узел может управлять доступом кода к маркерам потока из кода среды CLR и пользователя.</span><span class="sxs-lookup"><span data-stu-id="1b6d2-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="1b6d2-111">Также можно обеспечить, полный безопасность Контекстная информация, передаваемая через асинхронные операции или кодовые точки с ограниченным доступом.</span><span class="sxs-lookup"><span data-stu-id="1b6d2-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="1b6d2-112">`IHostSecurityContext` инкапсулирует эти сведения о контексте безопасности, являющиеся непрозрачными для среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="1b6d2-112">`IHostSecurityContext` encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="1b6d2-113">Среда выполнения перехватывает эти сведения с помощью `Capture`, и перемещает ее через элемент подготовки к отправке рабочего потока пула, выполнение методов завершения и конструкторов класса и модуля.</span><span class="sxs-lookup"><span data-stu-id="1b6d2-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b6d2-114">Требования</span><span class="sxs-lookup"><span data-stu-id="1b6d2-114">Requirements</span></span>  
 <span data-ttu-id="1b6d2-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b6d2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b6d2-116">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1b6d2-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1b6d2-117">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1b6d2-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b6d2-118">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b6d2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b6d2-119">См. также</span><span class="sxs-lookup"><span data-stu-id="1b6d2-119">See Also</span></span>  
 [<span data-ttu-id="1b6d2-120">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="1b6d2-120">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="1b6d2-121">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="1b6d2-121">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="1b6d2-122">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="1b6d2-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
