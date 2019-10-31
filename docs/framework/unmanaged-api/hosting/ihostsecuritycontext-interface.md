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
ms.openlocfilehash: 993d16818b25dfefe1f53c7afd06bc9857d9eb24
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121526"
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="f6e54-102">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="f6e54-102">IHostSecurityContext Interface</span></span>
<span data-ttu-id="f6e54-103">Позволяет среде CLR поддерживать сведения о контексте безопасности, реализуемые узлом.</span><span class="sxs-lookup"><span data-stu-id="f6e54-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f6e54-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f6e54-104">Methods</span></span>  
  
|<span data-ttu-id="f6e54-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f6e54-105">Method</span></span>|<span data-ttu-id="f6e54-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f6e54-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f6e54-107">Метод Capture</span><span class="sxs-lookup"><span data-stu-id="f6e54-107">Capture Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|<span data-ttu-id="f6e54-108">Возвращает клон экземпляра `IHostSecurityContext`, возвращенного из вызова [IHostSecurityManager:: getsecuritycontext-](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="f6e54-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6e54-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="f6e54-109">Remarks</span></span>  
 <span data-ttu-id="f6e54-110">Узел может управлять доступом кода к маркерам потоков как средой CLR, так и кодом пользователя.</span><span class="sxs-lookup"><span data-stu-id="f6e54-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="f6e54-111">Он также может гарантировать, что полные сведения о контексте безопасности передаются по асинхронным операциям или кодовым точкам с ограниченным доступом к коду.</span><span class="sxs-lookup"><span data-stu-id="f6e54-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="f6e54-112">`IHostSecurityContext` инкапсулирует эти сведения о контексте безопасности, которые непрозрачны для среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="f6e54-112">`IHostSecurityContext` encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="f6e54-113">Среда выполнения захватывает эти сведения с помощью `Capture`и перемещает их между отправкой рабочего элемента пула потоков, выполнением метода завершения, а также конструкторами модулей и классов.</span><span class="sxs-lookup"><span data-stu-id="f6e54-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6e54-114">Требования</span><span class="sxs-lookup"><span data-stu-id="f6e54-114">Requirements</span></span>  
 <span data-ttu-id="f6e54-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6e54-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6e54-116">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f6e54-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f6e54-117">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f6e54-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f6e54-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6e54-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6e54-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f6e54-119">See also</span></span>

- [<span data-ttu-id="f6e54-120">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="f6e54-120">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="f6e54-121">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="f6e54-121">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="f6e54-122">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="f6e54-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
