---
title: "Интерфейсы размещения CLR"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fd954419f46313a239ddf5a309a646e3d2f1b9bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="clr-hosting-interfaces"></a><span data-ttu-id="04ecb-102">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="04ecb-102">CLR Hosting Interfaces</span></span>
<span data-ttu-id="04ecb-103">В этом разделе описываются интерфейсы, которые неуправляемые узлов можно использовать для интеграции общеязыковой среды выполнения (CLR) в свои приложения.</span><span class="sxs-lookup"><span data-stu-id="04ecb-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span> <span data-ttu-id="04ecb-104">Сведения касаются платформы .NET Framework версии 2.0 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="04ecb-104">The information pertains to the .NET Framework version 2.0 and later versions.</span></span> <span data-ttu-id="04ecb-105">Эти интерфейсы позволяют основному приложению управлять многих других аспектов среды выполнения, чем было возможно в версиях 1.0 и 1.1 и обеспечивают более тесную интеграцию среды CLR и модели выполнения основного приложения.</span><span class="sxs-lookup"><span data-stu-id="04ecb-105">These interfaces enable the host to control many more aspects of the runtime than was possible in versions 1.0 and 1.1, and provide much tighter integration between the CLR and the host's execution model.</span></span>  
  
 <span data-ttu-id="04ecb-106">В .NET Framework версий 1.0 и 1.1 модель размещения позволяла неуправляемому основному приложению загрузить среду CLR в процесс для настройки определенных параметров и получения уведомлений о событиях.</span><span class="sxs-lookup"><span data-stu-id="04ecb-106">In the .NET Framework version 1.0 and 1.1, the hosting model enabled an unmanaged host to load the CLR into a process, to configure certain settings, and to receive event notifications.</span></span> <span data-ttu-id="04ecb-107">Тем не менее, как правило, узел и среда CLR выполнялись независимо друг от друга в этом процессе.</span><span class="sxs-lookup"><span data-stu-id="04ecb-107">However, in general, the host and the CLR ran independently in that process.</span></span> <span data-ttu-id="04ecb-108">В .NET Framework версии 2.0 и более поздних версиях новые уровни абстракции позволили основному приложению предоставлять множество ресурсов, предоставляемых в данный момент на типы в сборке Win32, и расширить набор возможностей, которые можно настроить узел.</span><span class="sxs-lookup"><span data-stu-id="04ecb-108">In the .NET Framework version 2.0 and later versions, new layers of abstraction let the host provide many of the resources currently provided by the types in the Win32 assembly, and extend the set of capabilities that the host can configure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="04ecb-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="04ecb-109">In This Section</span></span>  
 [<span data-ttu-id="04ecb-110">Интерфейс IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="04ecb-110">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 <span data-ttu-id="04ecb-111">Предоставляет метод, который выполняет обратный вызов для зарегистрированного события.</span><span class="sxs-lookup"><span data-stu-id="04ecb-111">Provides a method that performs a callback for a registered event.</span></span>  
  
 [<span data-ttu-id="04ecb-112">Интерфейс IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="04ecb-112">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)  
 <span data-ttu-id="04ecb-113">Предоставляет методы для осуществления обратных вызовов в подразделении.</span><span class="sxs-lookup"><span data-stu-id="04ecb-113">Provides methods for making callbacks within an apartment.</span></span>  
  
 [<span data-ttu-id="04ecb-114">Интерфейс IAppDomainBinding</span><span class="sxs-lookup"><span data-stu-id="04ecb-114">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)  
 <span data-ttu-id="04ecb-115">Предоставляет методы для параметра конфигурации времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="04ecb-115">Provides methods for setting run-time configuration.</span></span>  
  
 [<span data-ttu-id="04ecb-116">Интерфейс ICatalogServices</span><span class="sxs-lookup"><span data-stu-id="04ecb-116">ICatalogServices Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icatalogservices-interface.md)  
 <span data-ttu-id="04ecb-117">Предоставляет методы для служб каталогизации.</span><span class="sxs-lookup"><span data-stu-id="04ecb-117">Provides methods for cataloging services.</span></span> <span data-ttu-id="04ecb-118">(Этот интерфейс поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода).</span><span class="sxs-lookup"><span data-stu-id="04ecb-118">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="04ecb-119">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="04ecb-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 <span data-ttu-id="04ecb-120">Предоставляет методы, поддерживающие обмен данными между узлом и о сборках среды CLR.</span><span class="sxs-lookup"><span data-stu-id="04ecb-120">Provides methods that support communication between the host and the CLR about assemblies.</span></span>  
  
 [<span data-ttu-id="04ecb-121">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="04ecb-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 <span data-ttu-id="04ecb-122">Управляет списком сборок, загружаемых средой CLR, а не приложением.</span><span class="sxs-lookup"><span data-stu-id="04ecb-122">Manages a list of assemblies that are loaded by the CLR and not by the host.</span></span>  
  
 [<span data-ttu-id="04ecb-123">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="04ecb-123">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 <span data-ttu-id="04ecb-124">Предоставляет методы для узла, чтобы получить доступ к и настроить различные аспекты среды CLR.</span><span class="sxs-lookup"><span data-stu-id="04ecb-124">Provides methods for the host to gain access to, and configure various aspects of, the CLR.</span></span>  
  
 [<span data-ttu-id="04ecb-125">Интерфейс ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="04ecb-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 <span data-ttu-id="04ecb-126">Предоставляет методы, позволяющие ведущему приложению связать набор задач с идентификатором и понятным именем.</span><span class="sxs-lookup"><span data-stu-id="04ecb-126">Provides methods that enable a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
 [<span data-ttu-id="04ecb-127">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="04ecb-127">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 <span data-ttu-id="04ecb-128">Предоставляет методы, позволяющие основному приложению настроить пользовательские дампы кучи для отчетов об ошибках.</span><span class="sxs-lookup"><span data-stu-id="04ecb-128">Provides methods that enable the host to configure custom heap dumps for error reporting.</span></span>  
  
 [<span data-ttu-id="04ecb-129">Интерфейс ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="04ecb-129">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 <span data-ttu-id="04ecb-130">Предоставляет методы, позволяющие хост-приложению взаимодействовать с системой сборки мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="04ecb-130">Provides methods that enable a host to interact with the CLR's garbage collection system.</span></span>  
  
 [<span data-ttu-id="04ecb-131">Интерфейс ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="04ecb-131">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 <span data-ttu-id="04ecb-132">Предоставляет методы для вычисления и изменения в сведениях о политике для сборок взаимодействия узла.</span><span class="sxs-lookup"><span data-stu-id="04ecb-132">Provides methods for the host to evaluate and communicate changes in policy information for assemblies.</span></span>  
  
 [<span data-ttu-id="04ecb-133">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="04ecb-133">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 <span data-ttu-id="04ecb-134">Ведущее приложение может блокировать определенные управляемые классы, методы, свойства и поля при выполнении в частично доверенный код.</span><span class="sxs-lookup"><span data-stu-id="04ecb-134">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
 [<span data-ttu-id="04ecb-135">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="04ecb-135">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 <span data-ttu-id="04ecb-136">Реализует метод обратного вызова, который позволяет ведущему приложению уведомления среды CLR о состоянии указанных запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="04ecb-136">Implements a callback method that enables the host to notify the CLR of the status of specified I/O requests.</span></span>  
  
 [<span data-ttu-id="04ecb-137">Интерфейс ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="04ecb-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 <span data-ttu-id="04ecb-138">Позволяет ведущему приложению отчетов об условиях нехватки памяти с помощью подход, аналогичный Win32 `CreateMemoryResourceNotification` функции.</span><span class="sxs-lookup"><span data-stu-id="04ecb-138">Enables the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
 [<span data-ttu-id="04ecb-139">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="04ecb-139">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 <span data-ttu-id="04ecb-140">Предоставляет методы, позволяющие основному приложению регистрировать и отменять регистрацию обратные вызовы для событий среды CLR.</span><span class="sxs-lookup"><span data-stu-id="04ecb-140">Provides methods that enable the host to register and unregister callbacks for CLR events.</span></span>  
  
 [<span data-ttu-id="04ecb-141">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="04ecb-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 <span data-ttu-id="04ecb-142">Предоставляет методы, позволяющие основному приложению задать действия политики, которые необходимо выполнить в случае сбоев и увеличение времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="04ecb-142">Provides methods that enable the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
 [<span data-ttu-id="04ecb-143">Интерфейс ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="04ecb-143">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 <span data-ttu-id="04ecb-144">Предоставляет методы, позволяющие основному приложению получить проверочные идентификаторы сборки с помощью сведения об удостоверении сборки, которые являются внутренними для среды CLR, без необходимости создания или понять их подлинность.</span><span class="sxs-lookup"><span data-stu-id="04ecb-144">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the CLR, without needing to create or understand that identity.</span></span>  
  
 [<span data-ttu-id="04ecb-145">Интерфейс ICLRReferenceAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="04ecb-145">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)  
 <span data-ttu-id="04ecb-146">Предоставляет методы, позволяющие основному приложению управлять набор сборок, на который указывает файл или поток, используя данные идентификации сборки, которые являются внутренними для среды CLR, без необходимости создания или интерпретации этих данных.</span><span class="sxs-lookup"><span data-stu-id="04ecb-146">Provides methods that enable the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the CLR, without needing to create or understand those identities.</span></span>  
  
 [<span data-ttu-id="04ecb-147">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="04ecb-147">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 <span data-ttu-id="04ecb-148">Предоставляет возможности, аналогичные для [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), с дополнительным методом, позволяющим задать интерфейс управления узла.</span><span class="sxs-lookup"><span data-stu-id="04ecb-148">Provides capabilities similar to [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), with an additional method to set the host control interface.</span></span>  
  
 [<span data-ttu-id="04ecb-149">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="04ecb-149">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 <span data-ttu-id="04ecb-150">Предоставляет методы для узла, чтобы получить сведения о запрашиваемых задачах и взаимоблокировки в реализации синхронизации.</span><span class="sxs-lookup"><span data-stu-id="04ecb-150">Provides methods for the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
 [<span data-ttu-id="04ecb-151">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="04ecb-151">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 <span data-ttu-id="04ecb-152">Предоставляет методы, позволяющие основному приложению выполнять запросы среды CLR или предоставлять уведомления в среде CLR о соответствующей задаче.</span><span class="sxs-lookup"><span data-stu-id="04ecb-152">Provides methods that enable the host to make requests of the CLR, or to provide notification to the CLR about the associated task.</span></span>  
  
 [<span data-ttu-id="04ecb-153">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="04ecb-153">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 <span data-ttu-id="04ecb-154">Предоставляет методы, позволяющие основному приложению запрашивать явным образом, среда CLR создать новую задачу, выполняемую задачу и устанавливаются географического языка и языка и региональных параметров для задачи.</span><span class="sxs-lookup"><span data-stu-id="04ecb-154">Provides methods that enable the host to request explicitly that the CLR create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
 [<span data-ttu-id="04ecb-155">Интерфейс ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="04ecb-155">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)  
 <span data-ttu-id="04ecb-156">Предоставляет методы для проверки переносимого исполняемого (PE) образа и возврат ошибок проверки.</span><span class="sxs-lookup"><span data-stu-id="04ecb-156">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
 [<span data-ttu-id="04ecb-157">Интерфейс ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="04ecb-157">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)  
 <span data-ttu-id="04ecb-158">Предоставляет методы для настройки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="04ecb-158">Provides methods for configuring the CLR.</span></span>  
  
 [<span data-ttu-id="04ecb-159">Интерфейс ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="04ecb-159">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)  
 <span data-ttu-id="04ecb-160">Предоставляет методы для доступа к пулу потоков.</span><span class="sxs-lookup"><span data-stu-id="04ecb-160">Provides methods for accessing the thread pool.</span></span>  
  
 [<span data-ttu-id="04ecb-161">Интерфейс IDebuggerInfo</span><span class="sxs-lookup"><span data-stu-id="04ecb-161">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)  
 <span data-ttu-id="04ecb-162">Предоставляет методы для получения сведений о состоянии служб отладки.</span><span class="sxs-lookup"><span data-stu-id="04ecb-162">Provides methods for obtaining information about the state of the debugging services.</span></span>  
  
 [<span data-ttu-id="04ecb-163">Интерфейс IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="04ecb-163">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)  
 <span data-ttu-id="04ecb-164">Предоставляет методы для уведомления узла о блокировании и разблокировании потоков службами отладки.</span><span class="sxs-lookup"><span data-stu-id="04ecb-164">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
 [<span data-ttu-id="04ecb-165">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="04ecb-165">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)  
 <span data-ttu-id="04ecb-166">Предоставляет методы для получения сведений о системе сборки мусора, а также для управления некоторыми аспектами сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="04ecb-166">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
 [<span data-ttu-id="04ecb-167">Интерфейс IGCHost2</span><span class="sxs-lookup"><span data-stu-id="04ecb-167">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)  
 <span data-ttu-id="04ecb-168">Предоставляет [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) метод, который позволяет ведущему приложению установите размер сегмент сборки мусора и максимальный размер нулевого поколения и система сбора мусора для значений больше `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="04ecb-168">Provides the [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method that enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation zero to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="04ecb-169">Интерфейс IGCHostControl</span><span class="sxs-lookup"><span data-stu-id="04ecb-169">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)  
 <span data-ttu-id="04ecb-170">Предоставляет метод, который позволяет сборщику мусора запрашивать основное приложение для изменения ограничений на объем виртуальной памяти.</span><span class="sxs-lookup"><span data-stu-id="04ecb-170">Provides a method that enables the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
 [<span data-ttu-id="04ecb-171">Интерфейс IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="04ecb-171">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)  
 <span data-ttu-id="04ecb-172">Предоставляет методы для участия в планировании потоков, которые в противном случае были бы заблокированы для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="04ecb-172">Provides methods for participating in the scheduling of threads that would otherwise be blocked for garbage collection.</span></span>  
  
 [<span data-ttu-id="04ecb-173">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="04ecb-173">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 <span data-ttu-id="04ecb-174">Предоставляет методы, позволяющие хост-приложению задать набор сборок, которые должны быть загружены средой CLR или средой размещения.</span><span class="sxs-lookup"><span data-stu-id="04ecb-174">Provides methods that enable a host to specify sets of assemblies that should be loaded by the CLR or by the host.</span></span>  
  
 [<span data-ttu-id="04ecb-175">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="04ecb-175">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 <span data-ttu-id="04ecb-176">Предоставляет методы, позволяющие основному приложению загружать сборки и модули независимо от среды CLR.</span><span class="sxs-lookup"><span data-stu-id="04ecb-176">Provides methods that enable a host to load assemblies and modules independently of the CLR.</span></span>  
  
 [<span data-ttu-id="04ecb-177">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="04ecb-177">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 <span data-ttu-id="04ecb-178">Предоставляет представление события автоматического сброса, реализуемых основным приложением.</span><span class="sxs-lookup"><span data-stu-id="04ecb-178">Provides a representation of an auto-reset event implemented by the host.</span></span>  
  
 [<span data-ttu-id="04ecb-179">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="04ecb-179">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 <span data-ttu-id="04ecb-180">Предоставляет методы для настройки загрузки сборок, а также для определения интерфейсов размещения, поддерживаемых основным приложением.</span><span class="sxs-lookup"><span data-stu-id="04ecb-180">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
 [<span data-ttu-id="04ecb-181">Интерфейс IHostCrst</span><span class="sxs-lookup"><span data-stu-id="04ecb-181">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 <span data-ttu-id="04ecb-182">Служит в качестве узла представления критической секции для работы с потоками.</span><span class="sxs-lookup"><span data-stu-id="04ecb-182">Serves as the host's representation of a critical section for threading.</span></span>  
  
 [<span data-ttu-id="04ecb-183">Интерфейс IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="04ecb-183">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
 <span data-ttu-id="04ecb-184">Предоставляет методы, уведомляющие основное приложение о событиях в механизме сборки мусора, реализуемых средой CLR.</span><span class="sxs-lookup"><span data-stu-id="04ecb-184">Provides methods that notify the host of events in the garbage collection mechanism implemented by the CLR.</span></span>  
  
 [<span data-ttu-id="04ecb-185">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="04ecb-185">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 <span data-ttu-id="04ecb-186">Предоставляет методы, позволяющие взаимодействовать с порты завершения ввода-вывода, предоставленный средой размещения среды CLR.</span><span class="sxs-lookup"><span data-stu-id="04ecb-186">Provides methods that enable the CLR to interact with I/O completion ports provided by the host.</span></span>  
  
 [<span data-ttu-id="04ecb-187">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="04ecb-187">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 <span data-ttu-id="04ecb-188">Предоставляет методы для выделения точного количества памяти из кучи посредством основного приложения среды CLR.</span><span class="sxs-lookup"><span data-stu-id="04ecb-188">Provides methods for the CLR to request fine-grained allocations from the heap through the host.</span></span>  
  
 [<span data-ttu-id="04ecb-189">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="04ecb-189">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 <span data-ttu-id="04ecb-190">Предоставляет реализацию узла представления событие ручного сброса.</span><span class="sxs-lookup"><span data-stu-id="04ecb-190">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
 [<span data-ttu-id="04ecb-191">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="04ecb-191">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 <span data-ttu-id="04ecb-192">Предоставляет методы для осуществления запросов виртуальной памяти через узел, вместо использования стандартных функций Win32 виртуальной памяти среды CLR.</span><span class="sxs-lookup"><span data-stu-id="04ecb-192">Provides methods for the CLR to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
 [<span data-ttu-id="04ecb-193">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="04ecb-193">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 <span data-ttu-id="04ecb-194">Предоставляет методы, уведомляющие основное приложение действий, выполняемых средой CLR в случае возникновения прерываний, время ожидания или сбоев.</span><span class="sxs-lookup"><span data-stu-id="04ecb-194">Provides methods that notify the host of the actions the CLR performs in case of aborts, timeouts, or failures.</span></span>  
  
 [<span data-ttu-id="04ecb-195">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="04ecb-195">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 <span data-ttu-id="04ecb-196">Позволяет среде CLR возможность сохранять сведения о контексте безопасности, реализуемых основным приложением.</span><span class="sxs-lookup"><span data-stu-id="04ecb-196">Enables the CLR to maintain security context information implemented by the host.</span></span>  
  
 [<span data-ttu-id="04ecb-197">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="04ecb-197">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 <span data-ttu-id="04ecb-198">Предоставляет методы, включающие доступ к и контроль над контекст безопасности текущего потока.</span><span class="sxs-lookup"><span data-stu-id="04ecb-198">Provides methods that enable access to, and control over, the security context of the currently executing thread.</span></span>  
  
 [<span data-ttu-id="04ecb-199">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="04ecb-199">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 <span data-ttu-id="04ecb-200">Предоставляет представление семафора, реализуемых основным приложением.</span><span class="sxs-lookup"><span data-stu-id="04ecb-200">Provides a representation of a semaphore implemented by the host.</span></span>  
  
 [<span data-ttu-id="04ecb-201">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="04ecb-201">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 <span data-ttu-id="04ecb-202">Предоставляет методы для среды CLR для создания примитивы синхронизации, вызвав узла, а не с помощью функции синхронизации Win32.</span><span class="sxs-lookup"><span data-stu-id="04ecb-202">Provides methods for the CLR to create synchronization primitives by calling the host, instead of using the Win32 synchronization functions.</span></span>  
  
 [<span data-ttu-id="04ecb-203">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="04ecb-203">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 <span data-ttu-id="04ecb-204">Предоставляет методы, позволяющие среде CLR для связи с основным приложением для управления задачами.</span><span class="sxs-lookup"><span data-stu-id="04ecb-204">Provides methods that enable the CLR to communicate with the host to manage tasks.</span></span>  
  
 [<span data-ttu-id="04ecb-205">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="04ecb-205">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 <span data-ttu-id="04ecb-206">Предоставляет методы, позволяющие среде CLR работать с задачами посредством основного приложения, вместо того чтобы использовать функции работы с потоками или волокон стандартной операционной системе.</span><span class="sxs-lookup"><span data-stu-id="04ecb-206">Provides methods that enable the CLR to work with tasks through the host instead of using the standard operating system threading or fiber functions.</span></span>  
  
 [<span data-ttu-id="04ecb-207">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="04ecb-207">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 <span data-ttu-id="04ecb-208">Предоставляет методы для настройки пула потоков и очередь рабочих элементов в пуле потоков среды CLR.</span><span class="sxs-lookup"><span data-stu-id="04ecb-208">Provides methods for the CLR to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
 [<span data-ttu-id="04ecb-209">Интерфейс IManagedObject</span><span class="sxs-lookup"><span data-stu-id="04ecb-209">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)  
 <span data-ttu-id="04ecb-210">Предоставляет методы для управления управляемыми объектами.</span><span class="sxs-lookup"><span data-stu-id="04ecb-210">Provides methods for controlling a managed object.</span></span>  
  
 <span data-ttu-id="04ecb-211">«IObjectHandle»</span><span class="sxs-lookup"><span data-stu-id="04ecb-211">"IObjectHandle"</span></span>  
 <span data-ttu-id="04ecb-212">Предоставляет метод для распаковки маршалирования по значению объектов косвенного обращения.</span><span class="sxs-lookup"><span data-stu-id="04ecb-212">Provides a method for unwrapping marshal-by-value objects from indirection.</span></span>  
  
 [<span data-ttu-id="04ecb-213">Интерфейс ITypeName</span><span class="sxs-lookup"><span data-stu-id="04ecb-213">ITypeName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypename-interface.md)  
 <span data-ttu-id="04ecb-214">Предоставляет методы для получения сведений об имени типа.</span><span class="sxs-lookup"><span data-stu-id="04ecb-214">Provides methods for obtaining type name information.</span></span> <span data-ttu-id="04ecb-215">(Этот интерфейс поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода).</span><span class="sxs-lookup"><span data-stu-id="04ecb-215">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="04ecb-216">Интерфейс ITypeNameBuilder</span><span class="sxs-lookup"><span data-stu-id="04ecb-216">ITypeNameBuilder Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypenamebuilder-interface.md)  
 <span data-ttu-id="04ecb-217">Предоставляет методы для построения имени типа.</span><span class="sxs-lookup"><span data-stu-id="04ecb-217">Provides methods for building a type name.</span></span> <span data-ttu-id="04ecb-218">(Этот интерфейс поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода).</span><span class="sxs-lookup"><span data-stu-id="04ecb-218">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="04ecb-219">Интерфейс ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="04ecb-219">ITypeNameFactory Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypenamefactory-interface.md)  
 <span data-ttu-id="04ecb-220">Предоставляет методы для разбора имени типа.</span><span class="sxs-lookup"><span data-stu-id="04ecb-220">Provides methods for deconstructing a type name.</span></span> <span data-ttu-id="04ecb-221">(Этот интерфейс поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода).</span><span class="sxs-lookup"><span data-stu-id="04ecb-221">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 <span data-ttu-id="04ecb-222">«IValidator»</span><span class="sxs-lookup"><span data-stu-id="04ecb-222">"IValidator"</span></span>  
 <span data-ttu-id="04ecb-223">Предоставляет методы для проверки переносимого исполняемого (PE) образа и возврат ошибок проверки.</span><span class="sxs-lookup"><span data-stu-id="04ecb-223">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="04ecb-224">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="04ecb-224">Related Sections</span></span>  
 [<span data-ttu-id="04ecb-225">Устаревшие интерфейсы размещения CLR и коклассы</span><span class="sxs-lookup"><span data-stu-id="04ecb-225">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="04ecb-226">Содержит разделы, описывающие интерфейсы размещения, предоставляемые в .NET Framework версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="04ecb-226">Contains topics that describe the hosting interfaces provided in the .NET Framework version 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="04ecb-227">Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5</span><span class="sxs-lookup"><span data-stu-id="04ecb-227">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="04ecb-228">Содержит разделы, описывающие интерфейсы размещения, предоставляемые в [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="04ecb-228">Contains topics that describe the hosting interfaces provided in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>
