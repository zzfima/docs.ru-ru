---
title: Интерфейс ICorConfiguration
ms.date: 03/30/2017
api_name:
- ICorConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorConfiguration
helpviewer_keywords:
- ICorConfiguration interface [.NET Framework hosting]
ms.assetid: aaf96116-372b-4538-afb1-9e0fcdac1f98
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b24e278b3449d0e17377495cef0f445c1ebed734
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763280"
---
# <a name="icorconfiguration-interface"></a><span data-ttu-id="f5d4a-102">Интерфейс ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="f5d4a-102">ICorConfiguration Interface</span></span>
<span data-ttu-id="f5d4a-103">Предоставляет методы для настройки общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="f5d4a-103">Provides methods for configuring the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f5d4a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f5d4a-104">Methods</span></span>  
  
|<span data-ttu-id="f5d4a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f5d4a-105">Method</span></span>|<span data-ttu-id="f5d4a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f5d4a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f5d4a-107">Метод AddDebuggerSpecialThread</span><span class="sxs-lookup"><span data-stu-id="f5d4a-107">AddDebuggerSpecialThread Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-adddebuggerspecialthread-method.md)|<span data-ttu-id="f5d4a-108">Указывает службы отладки, что определенным потоком должны продолжить выполнение при завершении работы приложения во время сценариев отладки управляемого или неуправляемого отладчика.</span><span class="sxs-lookup"><span data-stu-id="f5d4a-108">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>|  
|[<span data-ttu-id="f5d4a-109">Метод SetDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="f5d4a-109">SetDebuggerThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setdebuggerthreadcontrol-method.md)|<span data-ttu-id="f5d4a-110">Задает интерфейс обратного вызова, который будет вызывать службы отладки при блокировании и разблокировании потоков среды CLR для отладки.</span><span class="sxs-lookup"><span data-stu-id="f5d4a-110">Sets the callback interface that the debugging services will call as CLR threads are blocked and unblocked for debugging.</span></span>|  
|[<span data-ttu-id="f5d4a-111">Метод SetGCHostControl</span><span class="sxs-lookup"><span data-stu-id="f5d4a-111">SetGCHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgchostcontrol-method.md)|<span data-ttu-id="f5d4a-112">Задает интерфейс обратного вызова, используемый сборщиком мусора для запроса узла, чтобы изменить ограничения виртуальной памяти.</span><span class="sxs-lookup"><span data-stu-id="f5d4a-112">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>|  
|[<span data-ttu-id="f5d4a-113">Метод SetGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="f5d4a-113">SetGCThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgcthreadcontrol-method.md)|<span data-ttu-id="f5d4a-114">Задает интерфейс обратного вызова для планирования потоков без выполнения задач, которые в противном случае был бы заблокирован для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="f5d4a-114">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f5d4a-115">Требования</span><span class="sxs-lookup"><span data-stu-id="f5d4a-115">Requirements</span></span>  
 <span data-ttu-id="f5d4a-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5d4a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5d4a-117">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f5d4a-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f5d4a-118">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f5d4a-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f5d4a-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5d4a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5d4a-120">См. также</span><span class="sxs-lookup"><span data-stu-id="f5d4a-120">See also</span></span>

- [<span data-ttu-id="f5d4a-121">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="f5d4a-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="f5d4a-122">Кокласс CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="f5d4a-122">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
