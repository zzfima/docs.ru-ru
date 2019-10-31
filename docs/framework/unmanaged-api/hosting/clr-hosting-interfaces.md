---
title: Интерфейсы размещения CLR
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
ms.openlocfilehash: 66fdd97d101f5ea53a96b996a2a60e5ed65a2701
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131970"
---
# <a name="clr-hosting-interfaces"></a><span data-ttu-id="f90e4-102">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="f90e4-102">CLR Hosting Interfaces</span></span>
<span data-ttu-id="f90e4-103">В этом разделе описываются интерфейсы, которые неуправляемые узлы могут использовать для интеграции среды CLR в свои приложения.</span><span class="sxs-lookup"><span data-stu-id="f90e4-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span> <span data-ttu-id="f90e4-104">Информация относится к .NET Framework версии 2,0 и более поздним версиям.</span><span class="sxs-lookup"><span data-stu-id="f90e4-104">The information pertains to the .NET Framework version 2.0 and later versions.</span></span> <span data-ttu-id="f90e4-105">Эти интерфейсы позволяют ведущему приложению управлять многими другими аспектами среды выполнения, чем было возможно в версиях 1,0 и 1,1, и обеспечивать более тесную интеграцию между средой CLR и моделью выполнения узла.</span><span class="sxs-lookup"><span data-stu-id="f90e4-105">These interfaces enable the host to control many more aspects of the runtime than was possible in versions 1.0 and 1.1, and provide much tighter integration between the CLR and the host's execution model.</span></span>  
  
 <span data-ttu-id="f90e4-106">В .NET Framework версии 1,0 и 1,1 модель размещения позволяла неуправляемому узлу загружать среду CLR в процесс, настраивать определенные параметры и получать уведомления о событиях.</span><span class="sxs-lookup"><span data-stu-id="f90e4-106">In the .NET Framework version 1.0 and 1.1, the hosting model enabled an unmanaged host to load the CLR into a process, to configure certain settings, and to receive event notifications.</span></span> <span data-ttu-id="f90e4-107">Однако в общем случае узел и среда CLR выполнялись независимо в этом процессе.</span><span class="sxs-lookup"><span data-stu-id="f90e4-107">However, in general, the host and the CLR ran independently in that process.</span></span> <span data-ttu-id="f90e4-108">В .NET Framework версии 2,0 и более поздних новые уровни абстракции позволяют ведущему приложению предоставлять множество ресурсов, предоставляемых типами в сборке Win32, и расширять набор возможностей, которые может настраивать узел.</span><span class="sxs-lookup"><span data-stu-id="f90e4-108">In the .NET Framework version 2.0 and later versions, new layers of abstraction let the host provide many of the resources currently provided by the types in the Win32 assembly, and extend the set of capabilities that the host can configure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f90e4-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="f90e4-109">In This Section</span></span>  
 [<span data-ttu-id="f90e4-110">Интерфейс IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="f90e4-110">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 <span data-ttu-id="f90e4-111">Предоставляет метод, который выполняет обратный вызов для зарегистрированного события.</span><span class="sxs-lookup"><span data-stu-id="f90e4-111">Provides a method that performs a callback for a registered event.</span></span>  
  
 [<span data-ttu-id="f90e4-112">Интерфейс IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="f90e4-112">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)  
 <span data-ttu-id="f90e4-113">Предоставляет методы для выполнения обратных вызовов в апартаменте.</span><span class="sxs-lookup"><span data-stu-id="f90e4-113">Provides methods for making callbacks within an apartment.</span></span>  
  
 [<span data-ttu-id="f90e4-114">Интерфейс IAppDomainBinding</span><span class="sxs-lookup"><span data-stu-id="f90e4-114">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)  
 <span data-ttu-id="f90e4-115">Предоставляет методы для настройки конфигурации времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="f90e4-115">Provides methods for setting run-time configuration.</span></span>  
  
 [<span data-ttu-id="f90e4-116">Интерфейс ICatalogServices</span><span class="sxs-lookup"><span data-stu-id="f90e4-116">ICatalogServices Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icatalogservices-interface.md)  
 <span data-ttu-id="f90e4-117">Предоставляет методы для каталогизации служб.</span><span class="sxs-lookup"><span data-stu-id="f90e4-117">Provides methods for cataloging services.</span></span> <span data-ttu-id="f90e4-118">(Этот интерфейс поддерживает .NET Frameworkную инфраструктуру и не предназначен для непосредственного использования в коде.)</span><span class="sxs-lookup"><span data-stu-id="f90e4-118">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="f90e4-119">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="f90e4-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 <span data-ttu-id="f90e4-120">Предоставляет методы, поддерживающие взаимодействие между узлом и средой CLR о сборках.</span><span class="sxs-lookup"><span data-stu-id="f90e4-120">Provides methods that support communication between the host and the CLR about assemblies.</span></span>  
  
 [<span data-ttu-id="f90e4-121">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="f90e4-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 <span data-ttu-id="f90e4-122">Управляет списком сборок, загружаемых средой CLR, а не узлом.</span><span class="sxs-lookup"><span data-stu-id="f90e4-122">Manages a list of assemblies that are loaded by the CLR and not by the host.</span></span>  
  
 [<span data-ttu-id="f90e4-123">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="f90e4-123">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 <span data-ttu-id="f90e4-124">Предоставляет узлу методы для получения доступа и настройки различных аспектов среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f90e4-124">Provides methods for the host to gain access to, and configure various aspects of, the CLR.</span></span>  
  
 [<span data-ttu-id="f90e4-125">Интерфейс ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="f90e4-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 <span data-ttu-id="f90e4-126">Предоставляет методы, позволяющие узлу связать набор задач с идентификатором и понятным именем.</span><span class="sxs-lookup"><span data-stu-id="f90e4-126">Provides methods that enable a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
 [<span data-ttu-id="f90e4-127">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="f90e4-127">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 <span data-ttu-id="f90e4-128">Предоставляет методы, позволяющие основному приложению настраивать дампы пользовательской кучи для отчетов об ошибках.</span><span class="sxs-lookup"><span data-stu-id="f90e4-128">Provides methods that enable the host to configure custom heap dumps for error reporting.</span></span>  
  
 [<span data-ttu-id="f90e4-129">Интерфейс ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="f90e4-129">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 <span data-ttu-id="f90e4-130">Предоставляет методы, позволяющие основному приложению взаимодействовать с системой сборки мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f90e4-130">Provides methods that enable a host to interact with the CLR's garbage collection system.</span></span>  
  
 [<span data-ttu-id="f90e4-131">Интерфейс ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="f90e4-131">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 <span data-ttu-id="f90e4-132">Предоставляет методам для узла возможность оценивать и передавать изменения в сведениях о политике для сборок.</span><span class="sxs-lookup"><span data-stu-id="f90e4-132">Provides methods for the host to evaluate and communicate changes in policy information for assemblies.</span></span>  
  
 [<span data-ttu-id="f90e4-133">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="f90e4-133">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 <span data-ttu-id="f90e4-134">Позволяет узлу блокировать выполнение конкретных управляемых классов, методов, свойств и полей в частично доверяемом коде.</span><span class="sxs-lookup"><span data-stu-id="f90e4-134">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
 [<span data-ttu-id="f90e4-135">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="f90e4-135">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 <span data-ttu-id="f90e4-136">Реализует метод обратного вызова, который позволяет ведущему приложению уведомлять среду CLR о состоянии указанных запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="f90e4-136">Implements a callback method that enables the host to notify the CLR of the status of specified I/O requests.</span></span>  
  
 [<span data-ttu-id="f90e4-137">Интерфейс ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="f90e4-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 <span data-ttu-id="f90e4-138">Позволяет узлу сообщать об условиях нехватки памяти с помощью подхода, аналогичного функции Win32 `CreateMemoryResourceNotification`.</span><span class="sxs-lookup"><span data-stu-id="f90e4-138">Enables the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
 [<span data-ttu-id="f90e4-139">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="f90e4-139">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 <span data-ttu-id="f90e4-140">Предоставляет методы, позволяющие основному приложению регистрировать и отменять регистрацию обратных вызовов для событий CLR.</span><span class="sxs-lookup"><span data-stu-id="f90e4-140">Provides methods that enable the host to register and unregister callbacks for CLR events.</span></span>  
  
 [<span data-ttu-id="f90e4-141">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="f90e4-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 <span data-ttu-id="f90e4-142">Предоставляет методы, позволяющие основному приложению указывать действия политики, выполняемые в случае сбоев и истечения времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="f90e4-142">Provides methods that enable the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
 [<span data-ttu-id="f90e4-143">Интерфейс ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="f90e4-143">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 <span data-ttu-id="f90e4-144">Предоставляет методы, позволяющие основному приложению получать идентификаторы проверки сборки с помощью сведений об удостоверении сборки, которые являются внутренними для CLR, без необходимости создания или понимания этого удостоверения.</span><span class="sxs-lookup"><span data-stu-id="f90e4-144">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the CLR, without needing to create or understand that identity.</span></span>  
  
 [<span data-ttu-id="f90e4-145">Интерфейс ICLRReferenceAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="f90e4-145">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)  
 <span data-ttu-id="f90e4-146">Предоставляет методы, позволяющие основному приложению манипулировать набором сборок, на которые ссылается файл или поток, с помощью данных идентификации сборок, которые являются внутренними для CLR, без необходимости создавать или анализировать эти удостоверения.</span><span class="sxs-lookup"><span data-stu-id="f90e4-146">Provides methods that enable the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the CLR, without needing to create or understand those identities.</span></span>  
  
 [<span data-ttu-id="f90e4-147">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="f90e4-147">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 <span data-ttu-id="f90e4-148">Предоставляет возможности, аналогичные [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), и дополнительный метод для установки интерфейса управления узла.</span><span class="sxs-lookup"><span data-stu-id="f90e4-148">Provides capabilities similar to [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), with an additional method to set the host control interface.</span></span>  
  
 [<span data-ttu-id="f90e4-149">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="f90e4-149">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 <span data-ttu-id="f90e4-150">Предоставляет основному приложению методы для получения сведений о запрошенных задачах и обнаружения взаимоблокировок в своей реализации синхронизации.</span><span class="sxs-lookup"><span data-stu-id="f90e4-150">Provides methods for the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
 [<span data-ttu-id="f90e4-151">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="f90e4-151">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 <span data-ttu-id="f90e4-152">Предоставляет методы, позволяющие основному приложению выполнять запросы среды CLR или предоставлять для среды CLR уведомление о связанной задаче.</span><span class="sxs-lookup"><span data-stu-id="f90e4-152">Provides methods that enable the host to make requests of the CLR, or to provide notification to the CLR about the associated task.</span></span>  
  
 [<span data-ttu-id="f90e4-153">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="f90e4-153">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 <span data-ttu-id="f90e4-154">Предоставляет методы, позволяющие основному приложению запрашивать явно, что среда CLR создает новую задачу, получает текущую выполняемую задачу и задает язык и региональные параметры для задачи.</span><span class="sxs-lookup"><span data-stu-id="f90e4-154">Provides methods that enable the host to request explicitly that the CLR create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
 [<span data-ttu-id="f90e4-155">Интерфейс ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="f90e4-155">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)  
 <span data-ttu-id="f90e4-156">Предоставляет методы для проверки переносимых исполняемых (PE) образов и создания отчетов об ошибках проверки.</span><span class="sxs-lookup"><span data-stu-id="f90e4-156">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
 [<span data-ttu-id="f90e4-157">Интерфейс ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="f90e4-157">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)  
 <span data-ttu-id="f90e4-158">Предоставляет методы для настройки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f90e4-158">Provides methods for configuring the CLR.</span></span>  
  
 [<span data-ttu-id="f90e4-159">Интерфейс ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="f90e4-159">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)  
 <span data-ttu-id="f90e4-160">Предоставляет методы для доступа к пулу потоков.</span><span class="sxs-lookup"><span data-stu-id="f90e4-160">Provides methods for accessing the thread pool.</span></span>  
  
 [<span data-ttu-id="f90e4-161">Интерфейс IDebuggerInfo</span><span class="sxs-lookup"><span data-stu-id="f90e4-161">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)  
 <span data-ttu-id="f90e4-162">Предоставляет методы для получения сведений о состоянии служб отладки.</span><span class="sxs-lookup"><span data-stu-id="f90e4-162">Provides methods for obtaining information about the state of the debugging services.</span></span>  
  
 [<span data-ttu-id="f90e4-163">Интерфейс IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="f90e4-163">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)  
 <span data-ttu-id="f90e4-164">Предоставляет методы для уведомления узла о блокировке и разблокировке потоков службами отладки.</span><span class="sxs-lookup"><span data-stu-id="f90e4-164">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
 [<span data-ttu-id="f90e4-165">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="f90e4-165">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)  
 <span data-ttu-id="f90e4-166">Предоставляет методы для получения сведений о системе сборки мусора и для управления некоторыми аспектами сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="f90e4-166">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
 [<span data-ttu-id="f90e4-167">Интерфейс IGCHost2</span><span class="sxs-lookup"><span data-stu-id="f90e4-167">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)  
 <span data-ttu-id="f90e4-168">Предоставляет метод [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) , позволяющий основному приложению задавать размер сегмента сборки мусора и максимальный размер нулевого поколения системы сборки мусора для значений, превышающих `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="f90e4-168">Provides the [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method that enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation zero to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="f90e4-169">Интерфейс IGCHostControl</span><span class="sxs-lookup"><span data-stu-id="f90e4-169">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)  
 <span data-ttu-id="f90e4-170">Предоставляет метод, позволяющий сборщику мусора запрашивать изменение ограничений виртуальной памяти на узле.</span><span class="sxs-lookup"><span data-stu-id="f90e4-170">Provides a method that enables the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
 [<span data-ttu-id="f90e4-171">Интерфейс IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="f90e4-171">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)  
 <span data-ttu-id="f90e4-172">Предоставляет методы для участия в планировании потоков, которые в противном случае были бы заблокированы для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="f90e4-172">Provides methods for participating in the scheduling of threads that would otherwise be blocked for garbage collection.</span></span>  
  
 [<span data-ttu-id="f90e4-173">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="f90e4-173">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 <span data-ttu-id="f90e4-174">Предоставляет методы, позволяющие основному приложению указывать наборы сборок, которые должны загружаться средой CLR или узлом.</span><span class="sxs-lookup"><span data-stu-id="f90e4-174">Provides methods that enable a host to specify sets of assemblies that should be loaded by the CLR or by the host.</span></span>  
  
 [<span data-ttu-id="f90e4-175">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="f90e4-175">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 <span data-ttu-id="f90e4-176">Предоставляет методы, позволяющие основному приложению загружать сборки и модули независимо от среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f90e4-176">Provides methods that enable a host to load assemblies and modules independently of the CLR.</span></span>  
  
 [<span data-ttu-id="f90e4-177">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="f90e4-177">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 <span data-ttu-id="f90e4-178">Предоставляет представление события автоматического сброса, реализованного хостом.</span><span class="sxs-lookup"><span data-stu-id="f90e4-178">Provides a representation of an auto-reset event implemented by the host.</span></span>  
  
 [<span data-ttu-id="f90e4-179">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="f90e4-179">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 <span data-ttu-id="f90e4-180">Предоставляет методы для настройки загрузки сборок и для определения того, какие интерфейсы размещения поддерживает узел.</span><span class="sxs-lookup"><span data-stu-id="f90e4-180">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
 [<span data-ttu-id="f90e4-181">Интерфейс IHostCrst</span><span class="sxs-lookup"><span data-stu-id="f90e4-181">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 <span data-ttu-id="f90e4-182">Служит в качестве представления критической секции для потоков в основном приложении.</span><span class="sxs-lookup"><span data-stu-id="f90e4-182">Serves as the host's representation of a critical section for threading.</span></span>  
  
 [<span data-ttu-id="f90e4-183">Интерфейс IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="f90e4-183">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
 <span data-ttu-id="f90e4-184">Предоставляет методы, которые уведомляют узел о событиях в механизме сборки мусора, реализованном средой CLR.</span><span class="sxs-lookup"><span data-stu-id="f90e4-184">Provides methods that notify the host of events in the garbage collection mechanism implemented by the CLR.</span></span>  
  
 [<span data-ttu-id="f90e4-185">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="f90e4-185">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 <span data-ttu-id="f90e4-186">Предоставляет методы, позволяющие среде CLR взаимодействовать с портами завершения ввода-вывода, предоставляемыми узлом.</span><span class="sxs-lookup"><span data-stu-id="f90e4-186">Provides methods that enable the CLR to interact with I/O completion ports provided by the host.</span></span>  
  
 [<span data-ttu-id="f90e4-187">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="f90e4-187">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 <span data-ttu-id="f90e4-188">Предоставляет методы для CLR, чтобы запрашивать детализированные выделения из кучи через узел.</span><span class="sxs-lookup"><span data-stu-id="f90e4-188">Provides methods for the CLR to request fine-grained allocations from the heap through the host.</span></span>  
  
 [<span data-ttu-id="f90e4-189">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="f90e4-189">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 <span data-ttu-id="f90e4-190">Предоставляет реализацию представления события ручного сброса в узле.</span><span class="sxs-lookup"><span data-stu-id="f90e4-190">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
 [<span data-ttu-id="f90e4-191">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="f90e4-191">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 <span data-ttu-id="f90e4-192">Предоставляет методы для среды CLR для выполнения запросов к виртуальной памяти через основное приложение вместо использования стандартных функций виртуальной памяти Win32.</span><span class="sxs-lookup"><span data-stu-id="f90e4-192">Provides methods for the CLR to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
 [<span data-ttu-id="f90e4-193">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="f90e4-193">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 <span data-ttu-id="f90e4-194">Предоставляет методы, уведомляющие узел о действиях, выполняемых средой CLR в случае прерываний, времени ожидания или сбоев.</span><span class="sxs-lookup"><span data-stu-id="f90e4-194">Provides methods that notify the host of the actions the CLR performs in case of aborts, timeouts, or failures.</span></span>  
  
 [<span data-ttu-id="f90e4-195">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="f90e4-195">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 <span data-ttu-id="f90e4-196">Позволяет среде CLR поддерживать сведения о контексте безопасности, реализуемые узлом.</span><span class="sxs-lookup"><span data-stu-id="f90e4-196">Enables the CLR to maintain security context information implemented by the host.</span></span>  
  
 [<span data-ttu-id="f90e4-197">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="f90e4-197">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 <span data-ttu-id="f90e4-198">Предоставляет методы, обеспечивающие доступ к контексту безопасности выполняющегося потока и управление им.</span><span class="sxs-lookup"><span data-stu-id="f90e4-198">Provides methods that enable access to, and control over, the security context of the currently executing thread.</span></span>  
  
 [<span data-ttu-id="f90e4-199">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="f90e4-199">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 <span data-ttu-id="f90e4-200">Предоставляет представление семафора, реализованного узлом.</span><span class="sxs-lookup"><span data-stu-id="f90e4-200">Provides a representation of a semaphore implemented by the host.</span></span>  
  
 [<span data-ttu-id="f90e4-201">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="f90e4-201">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 <span data-ttu-id="f90e4-202">Предоставляет методы для среды CLR для создания примитивов синхронизации путем вызова узла вместо использования функций синхронизации Win32.</span><span class="sxs-lookup"><span data-stu-id="f90e4-202">Provides methods for the CLR to create synchronization primitives by calling the host, instead of using the Win32 synchronization functions.</span></span>  
  
 [<span data-ttu-id="f90e4-203">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="f90e4-203">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 <span data-ttu-id="f90e4-204">Предоставляет методы, позволяющие среде CLR взаимодействовать с узлом для управления задачами.</span><span class="sxs-lookup"><span data-stu-id="f90e4-204">Provides methods that enable the CLR to communicate with the host to manage tasks.</span></span>  
  
 [<span data-ttu-id="f90e4-205">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="f90e4-205">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 <span data-ttu-id="f90e4-206">Предоставляет методы, позволяющие среде CLR работать с задачами через основное приложение, а не использовать стандартные функции потоков или волоконно-оптической операционной системы.</span><span class="sxs-lookup"><span data-stu-id="f90e4-206">Provides methods that enable the CLR to work with tasks through the host instead of using the standard operating system threading or fiber functions.</span></span>  
  
 [<span data-ttu-id="f90e4-207">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="f90e4-207">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 <span data-ttu-id="f90e4-208">Предоставляет методы для среды CLR для настройки пула потоков и постановки рабочих элементов в очередь в пул потоков.</span><span class="sxs-lookup"><span data-stu-id="f90e4-208">Provides methods for the CLR to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
 [<span data-ttu-id="f90e4-209">Интерфейс IManagedObject</span><span class="sxs-lookup"><span data-stu-id="f90e4-209">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)  
 <span data-ttu-id="f90e4-210">Предоставляет методы для управления управляемым объектом.</span><span class="sxs-lookup"><span data-stu-id="f90e4-210">Provides methods for controlling a managed object.</span></span>  
  
 <span data-ttu-id="f90e4-211">"Иобжександле"</span><span class="sxs-lookup"><span data-stu-id="f90e4-211">"IObjectHandle"</span></span>  
 <span data-ttu-id="f90e4-212">Предоставляет метод для распаковки объектов, перенаправляемых по значению, из косвенного обращения.</span><span class="sxs-lookup"><span data-stu-id="f90e4-212">Provides a method for unwrapping marshal-by-value objects from indirection.</span></span>  
  
 [<span data-ttu-id="f90e4-213">Интерфейс ITypeName</span><span class="sxs-lookup"><span data-stu-id="f90e4-213">ITypeName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypename-interface.md)  
 <span data-ttu-id="f90e4-214">Предоставляет методы для получения сведений о имени типа.</span><span class="sxs-lookup"><span data-stu-id="f90e4-214">Provides methods for obtaining type name information.</span></span> <span data-ttu-id="f90e4-215">(Этот интерфейс поддерживает .NET Frameworkную инфраструктуру и не предназначен для непосредственного использования в коде.)</span><span class="sxs-lookup"><span data-stu-id="f90e4-215">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="f90e4-216">Интерфейс ITypeNameBuilder</span><span class="sxs-lookup"><span data-stu-id="f90e4-216">ITypeNameBuilder Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypenamebuilder-interface.md)  
 <span data-ttu-id="f90e4-217">Предоставляет методы для создания имени типа.</span><span class="sxs-lookup"><span data-stu-id="f90e4-217">Provides methods for building a type name.</span></span> <span data-ttu-id="f90e4-218">(Этот интерфейс поддерживает .NET Frameworkную инфраструктуру и не предназначен для непосредственного использования в коде.)</span><span class="sxs-lookup"><span data-stu-id="f90e4-218">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="f90e4-219">Интерфейс ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="f90e4-219">ITypeNameFactory Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypenamefactory-interface.md)  
 <span data-ttu-id="f90e4-220">Предоставляет методы для деконструирования имени типа.</span><span class="sxs-lookup"><span data-stu-id="f90e4-220">Provides methods for deconstructing a type name.</span></span> <span data-ttu-id="f90e4-221">(Этот интерфейс поддерживает .NET Frameworkную инфраструктуру и не предназначен для непосредственного использования в коде.)</span><span class="sxs-lookup"><span data-stu-id="f90e4-221">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 <span data-ttu-id="f90e4-222">IValidator</span><span class="sxs-lookup"><span data-stu-id="f90e4-222">"IValidator"</span></span>  
 <span data-ttu-id="f90e4-223">Предоставляет методы для проверки переносимых исполняемых (PE) образов и создания отчетов об ошибках проверки.</span><span class="sxs-lookup"><span data-stu-id="f90e4-223">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f90e4-224">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="f90e4-224">Related Sections</span></span>  
 [<span data-ttu-id="f90e4-225">Устаревшие интерфейсы размещения CLR и коклассы</span><span class="sxs-lookup"><span data-stu-id="f90e4-225">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="f90e4-226">Содержит разделы, описывающие интерфейсы размещения, предоставляемые в .NET Framework версии 1,0 и 1,1.</span><span class="sxs-lookup"><span data-stu-id="f90e4-226">Contains topics that describe the hosting interfaces provided in the .NET Framework version 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="f90e4-227">Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5</span><span class="sxs-lookup"><span data-stu-id="f90e4-227">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="f90e4-228">Содержит разделы, описывающие интерфейсы размещения, предоставляемые в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f90e4-228">Contains topics that describe the hosting interfaces provided in the .NET Framework 4.</span></span>
