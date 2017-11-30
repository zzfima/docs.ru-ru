---
title: "Интерфейс ICorConfiguration"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorConfiguration
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorConfiguration
helpviewer_keywords: ICorConfiguration interface [.NET Framework hosting]
ms.assetid: aaf96116-372b-4538-afb1-9e0fcdac1f98
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6bc66abf28e90d858d993bd62e9c67f840af137b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorconfiguration-interface"></a><span data-ttu-id="dd25c-102">Интерфейс ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="dd25c-102">ICorConfiguration Interface</span></span>
<span data-ttu-id="dd25c-103">Предоставляет методы для настройки общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="dd25c-103">Provides methods for configuring the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dd25c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="dd25c-104">Methods</span></span>  
  
|<span data-ttu-id="dd25c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="dd25c-105">Method</span></span>|<span data-ttu-id="dd25c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="dd25c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dd25c-107">Adddebuggerspecialthread-метод</span><span class="sxs-lookup"><span data-stu-id="dd25c-107">AddDebuggerSpecialThread Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-adddebuggerspecialthread-method.md)|<span data-ttu-id="dd25c-108">Указывает службы отладки, в определенном потоке, что следует разрешить продолжить выполнение при завершении работы приложения во время отладки сценариев управляемого или неуправляемого отладчика.</span><span class="sxs-lookup"><span data-stu-id="dd25c-108">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>|  
|[<span data-ttu-id="dd25c-109">Setdebuggerthreadcontrol-метод</span><span class="sxs-lookup"><span data-stu-id="dd25c-109">SetDebuggerThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setdebuggerthreadcontrol-method.md)|<span data-ttu-id="dd25c-110">Задает интерфейс обратного вызова, который будет вызываться службами отладки при блокировании и разблокировании потоков среды CLR для отладки.</span><span class="sxs-lookup"><span data-stu-id="dd25c-110">Sets the callback interface that the debugging services will call as CLR threads are blocked and unblocked for debugging.</span></span>|  
|[<span data-ttu-id="dd25c-111">Setgchostcontrol-метод</span><span class="sxs-lookup"><span data-stu-id="dd25c-111">SetGCHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgchostcontrol-method.md)|<span data-ttu-id="dd25c-112">Задает интерфейс обратного вызова, используемый сборщиком мусора запрашивать основное приложение для изменения ограничений на объем виртуальной памяти.</span><span class="sxs-lookup"><span data-stu-id="dd25c-112">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>|  
|[<span data-ttu-id="dd25c-113">Setgcthreadcontrol-метод</span><span class="sxs-lookup"><span data-stu-id="dd25c-113">SetGCThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgcthreadcontrol-method.md)|<span data-ttu-id="dd25c-114">Задает интерфейс обратного вызова для планирования потоков без выполнения задач, которые в противном случае были бы заблокированы для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="dd25c-114">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dd25c-115">Требования</span><span class="sxs-lookup"><span data-stu-id="dd25c-115">Requirements</span></span>  
 <span data-ttu-id="dd25c-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd25c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd25c-117">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dd25c-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dd25c-118">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dd25c-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd25c-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd25c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd25c-120">См. также</span><span class="sxs-lookup"><span data-stu-id="dd25c-120">See Also</span></span>  
 [<span data-ttu-id="dd25c-121">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="dd25c-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="dd25c-122">Компонентный класс CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="dd25c-122">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
