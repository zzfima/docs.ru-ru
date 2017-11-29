---
title: "Интерфейс IHostSecurityContext"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityContext
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityContext
helpviewer_keywords: IHostSecurityContext interface [.NET Framework hosting]
ms.assetid: 88e2eac0-8ccb-404f-abbc-287d55159842
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1d3c616ced761b696f50e9207e6fad312f06c31c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="4f4cf-102">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="4f4cf-102">IHostSecurityContext Interface</span></span>
<span data-ttu-id="4f4cf-103">Позволяет общеязыковая среда выполнения (CLR), чтобы сохранить сведения о контексте безопасности, реализуемых основным приложением.</span><span class="sxs-lookup"><span data-stu-id="4f4cf-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4f4cf-104">Методы</span><span class="sxs-lookup"><span data-stu-id="4f4cf-104">Methods</span></span>  
  
|<span data-ttu-id="4f4cf-105">Метод</span><span class="sxs-lookup"><span data-stu-id="4f4cf-105">Method</span></span>|<span data-ttu-id="4f4cf-106">Описание</span><span class="sxs-lookup"><span data-stu-id="4f4cf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4f4cf-107">Capture-метод</span><span class="sxs-lookup"><span data-stu-id="4f4cf-107">Capture Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|<span data-ttu-id="4f4cf-108">Возвращает точную копию `IHostSecurityContext` экземпляр возвращен из вызова [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="4f4cf-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f4cf-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="4f4cf-109">Remarks</span></span>  
 <span data-ttu-id="4f4cf-110">Узел может управлять доступом кода к маркерам потока из кода среды CLR и пользователя.</span><span class="sxs-lookup"><span data-stu-id="4f4cf-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="4f4cf-111">Также можно обеспечить, полный безопасность Контекстная информация, передаваемая через асинхронные операции или кодовые точки с ограниченным доступом.</span><span class="sxs-lookup"><span data-stu-id="4f4cf-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="4f4cf-112">`IHostSecurityContext`инкапсулирует эти сведения о контексте безопасности, являющиеся непрозрачными для среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4f4cf-112">`IHostSecurityContext` encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="4f4cf-113">Среда выполнения перехватывает эти сведения с помощью `Capture`, и перемещает ее через элемент подготовки к отправке рабочего потока пула, выполнение методов завершения и конструкторов класса и модуля.</span><span class="sxs-lookup"><span data-stu-id="4f4cf-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f4cf-114">Требования</span><span class="sxs-lookup"><span data-stu-id="4f4cf-114">Requirements</span></span>  
 <span data-ttu-id="4f4cf-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f4cf-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f4cf-116">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4f4cf-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4f4cf-117">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4f4cf-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4f4cf-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f4cf-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f4cf-119">См. также</span><span class="sxs-lookup"><span data-stu-id="4f4cf-119">See Also</span></span>  
 [<span data-ttu-id="4f4cf-120">Iclrhostprotectionmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4f4cf-120">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="4f4cf-121">IHostSecurityManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4f4cf-121">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="4f4cf-122">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="4f4cf-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
