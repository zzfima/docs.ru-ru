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
ms.openlocfilehash: 80bb68486e555d6c96cf8ee56ed6d60e41c7c5c6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127805"
---
# <a name="icorconfiguration-interface"></a><span data-ttu-id="38749-102">Интерфейс ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="38749-102">ICorConfiguration Interface</span></span>
<span data-ttu-id="38749-103">Предоставляет методы для настройки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="38749-103">Provides methods for configuring the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="38749-104">Методы</span><span class="sxs-lookup"><span data-stu-id="38749-104">Methods</span></span>  
  
|<span data-ttu-id="38749-105">Метод</span><span class="sxs-lookup"><span data-stu-id="38749-105">Method</span></span>|<span data-ttu-id="38749-106">Описание</span><span class="sxs-lookup"><span data-stu-id="38749-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="38749-107">Метод AddDebuggerSpecialThread</span><span class="sxs-lookup"><span data-stu-id="38749-107">AddDebuggerSpecialThread Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-adddebuggerspecialthread-method.md)|<span data-ttu-id="38749-108">Указывает службам отладки, что определенному потоку должен быть разрешено продолжать выполнение, пока отладчик не остановит работу приложения во время управляемых или неуправляемых сценариев отладки.</span><span class="sxs-lookup"><span data-stu-id="38749-108">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>|  
|[<span data-ttu-id="38749-109">Метод SetDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="38749-109">SetDebuggerThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setdebuggerthreadcontrol-method.md)|<span data-ttu-id="38749-110">Задает интерфейс обратного вызова, который службы отладки будут вызывать как потоки CLR, блокируются и разблокируются для отладки.</span><span class="sxs-lookup"><span data-stu-id="38749-110">Sets the callback interface that the debugging services will call as CLR threads are blocked and unblocked for debugging.</span></span>|  
|[<span data-ttu-id="38749-111">Метод SetGCHostControl</span><span class="sxs-lookup"><span data-stu-id="38749-111">SetGCHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgchostcontrol-method.md)|<span data-ttu-id="38749-112">Задает интерфейс обратного вызова, используемый сборщиком мусора для запроса изменения ограничения виртуальной памяти на узле.</span><span class="sxs-lookup"><span data-stu-id="38749-112">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>|  
|[<span data-ttu-id="38749-113">Метод SetGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="38749-113">SetGCThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgcthreadcontrol-method.md)|<span data-ttu-id="38749-114">Задает интерфейс обратного вызова для потоков планирования для задач, не относящихся к среде выполнения, которые в противном случае были бы заблокированы для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="38749-114">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="38749-115">Требования</span><span class="sxs-lookup"><span data-stu-id="38749-115">Requirements</span></span>  
 <span data-ttu-id="38749-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38749-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38749-117">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="38749-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="38749-118">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="38749-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="38749-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38749-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38749-120">См. также</span><span class="sxs-lookup"><span data-stu-id="38749-120">See also</span></span>

- [<span data-ttu-id="38749-121">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="38749-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="38749-122">Кокласс CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="38749-122">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
