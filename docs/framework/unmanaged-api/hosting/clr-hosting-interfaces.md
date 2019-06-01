---
title: Интерфейсы размещения CLR
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80404e65263aa4ad245a8c8213630a4736bd7b11
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456882"
---
# <a name="clr-hosting-interfaces"></a><span data-ttu-id="4d098-102">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="4d098-102">CLR Hosting Interfaces</span></span>
<span data-ttu-id="4d098-103">В этом разделе описываются интерфейсы, которые неуправляемые узлы могут использовать для интеграции общеязыковой среды выполнения (CLR) в свои приложения.</span><span class="sxs-lookup"><span data-stu-id="4d098-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span> <span data-ttu-id="4d098-104">Сведения относятся к .NET Framework версии 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="4d098-104">The information pertains to the .NET Framework version 2.0 and later versions.</span></span> <span data-ttu-id="4d098-105">Эти интерфейсы позволяют узлу управлять многих других аспектов среды выполнения, чем это было возможно в версиях 1.0 и 1.1 и обеспечивают более тесную интеграцию среды CLR и модели выполнения основного приложения.</span><span class="sxs-lookup"><span data-stu-id="4d098-105">These interfaces enable the host to control many more aspects of the runtime than was possible in versions 1.0 and 1.1, and provide much tighter integration between the CLR and the host's execution model.</span></span>  
  
 <span data-ttu-id="4d098-106">В .NET Framework версий 1.0 и 1.1 модель размещения включена неуправляемый узел загружать среду CLR в процесс для настройки определенных параметров и получения уведомлений о событиях.</span><span class="sxs-lookup"><span data-stu-id="4d098-106">In the .NET Framework version 1.0 and 1.1, the hosting model enabled an unmanaged host to load the CLR into a process, to configure certain settings, and to receive event notifications.</span></span> <span data-ttu-id="4d098-107">Тем не менее, как правило, узел и среда CLR выполнялись независимо друг от друга в этом процессе.</span><span class="sxs-lookup"><span data-stu-id="4d098-107">However, in general, the host and the CLR ran independently in that process.</span></span> <span data-ttu-id="4d098-108">В .NET Framework версии 2.0 и более поздних версий новые уровни абстракции позволяют узла, который предоставляют многие ресурсы, в настоящее время предоставляемые типы в сборке Win32, и расширить набор возможностей, которые можно настроить узел.</span><span class="sxs-lookup"><span data-stu-id="4d098-108">In the .NET Framework version 2.0 and later versions, new layers of abstraction let the host provide many of the resources currently provided by the types in the Win32 assembly, and extend the set of capabilities that the host can configure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4d098-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="4d098-109">In This Section</span></span>  
 [<span data-ttu-id="4d098-110">Интерфейс IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="4d098-110">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 <span data-ttu-id="4d098-111">Предоставляет метод, который выполняет обратный вызов для зарегистрированного события.</span><span class="sxs-lookup"><span data-stu-id="4d098-111">Provides a method that performs a callback for a registered event.</span></span>  
  
 [<span data-ttu-id="4d098-112">Интерфейс IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="4d098-112">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)  
 <span data-ttu-id="4d098-113">Предоставляет методы для осуществления обратных вызовов в подразделении.</span><span class="sxs-lookup"><span data-stu-id="4d098-113">Provides methods for making callbacks within an apartment.</span></span>  
  
 [<span data-ttu-id="4d098-114">Интерфейс IAppDomainBinding</span><span class="sxs-lookup"><span data-stu-id="4d098-114">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)  
 <span data-ttu-id="4d098-115">Предоставляет методы для настройки конфигурации времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="4d098-115">Provides methods for setting run-time configuration.</span></span>  
  
 [<span data-ttu-id="4d098-116">Интерфейс ICatalogServices</span><span class="sxs-lookup"><span data-stu-id="4d098-116">ICatalogServices Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icatalogservices-interface.md)  
 <span data-ttu-id="4d098-117">Предоставляет методы для создания каталога служб.</span><span class="sxs-lookup"><span data-stu-id="4d098-117">Provides methods for cataloging services.</span></span> <span data-ttu-id="4d098-118">(Этот интерфейс поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода).</span><span class="sxs-lookup"><span data-stu-id="4d098-118">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="4d098-119">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="4d098-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 <span data-ttu-id="4d098-120">Предоставляет методы, поддерживающие обмен данными между узлом и о сборках среды CLR.</span><span class="sxs-lookup"><span data-stu-id="4d098-120">Provides methods that support communication between the host and the CLR about assemblies.</span></span>  
  
 [<span data-ttu-id="4d098-121">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="4d098-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 <span data-ttu-id="4d098-122">Управляет списком сборок, загружаемых средой CLR, а не приложением.</span><span class="sxs-lookup"><span data-stu-id="4d098-122">Manages a list of assemblies that are loaded by the CLR and not by the host.</span></span>  
  
 [<span data-ttu-id="4d098-123">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="4d098-123">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 <span data-ttu-id="4d098-124">Предоставляет методы для получения доступа к и настроить различные аспекты, среда CLR узла.</span><span class="sxs-lookup"><span data-stu-id="4d098-124">Provides methods for the host to gain access to, and configure various aspects of, the CLR.</span></span>  
  
 [<span data-ttu-id="4d098-125">Интерфейс ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="4d098-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 <span data-ttu-id="4d098-126">Предоставляет методы, которые позволяют ведущему приложению связать набор задач с идентификатором и понятное имя.</span><span class="sxs-lookup"><span data-stu-id="4d098-126">Provides methods that enable a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
 [<span data-ttu-id="4d098-127">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="4d098-127">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 <span data-ttu-id="4d098-128">Предоставляет методы, позволяющие основному приложению настроить пользовательские дампы кучи для отчетов об ошибках.</span><span class="sxs-lookup"><span data-stu-id="4d098-128">Provides methods that enable the host to configure custom heap dumps for error reporting.</span></span>  
  
 [<span data-ttu-id="4d098-129">Интерфейс ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="4d098-129">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 <span data-ttu-id="4d098-130">Предоставляет методы, позволяющие узлу взаимодействовать с системой сборки мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="4d098-130">Provides methods that enable a host to interact with the CLR's garbage collection system.</span></span>  
  
 [<span data-ttu-id="4d098-131">Интерфейс ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="4d098-131">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 <span data-ttu-id="4d098-132">Предоставляет методы для оценки и идентифицировать изменения в данные политики для сборки узла.</span><span class="sxs-lookup"><span data-stu-id="4d098-132">Provides methods for the host to evaluate and communicate changes in policy information for assemblies.</span></span>  
  
 [<span data-ttu-id="4d098-133">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="4d098-133">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 <span data-ttu-id="4d098-134">Ведущее приложение может блокировать определенные управляемые классы, методы, свойства и поля запуска частично доверенного кода.</span><span class="sxs-lookup"><span data-stu-id="4d098-134">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
 [<span data-ttu-id="4d098-135">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="4d098-135">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 <span data-ttu-id="4d098-136">Реализует метод обратного вызова, который позволяет ведущему приложению уведомлять среду CLR о состоянии указанного запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="4d098-136">Implements a callback method that enables the host to notify the CLR of the status of specified I/O requests.</span></span>  
  
 [<span data-ttu-id="4d098-137">Интерфейс ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="4d098-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 <span data-ttu-id="4d098-138">Позволяет узлу отчетов об условиях нехватки памяти с помощью подхода, аналогичную Win32 `CreateMemoryResourceNotification` функции.</span><span class="sxs-lookup"><span data-stu-id="4d098-138">Enables the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
 [<span data-ttu-id="4d098-139">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="4d098-139">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 <span data-ttu-id="4d098-140">Предоставляет методы, позволяющие основному приложению регистрировать и отменять регистрацию обратных вызовов для событий среды CLR.</span><span class="sxs-lookup"><span data-stu-id="4d098-140">Provides methods that enable the host to register and unregister callbacks for CLR events.</span></span>  
  
 [<span data-ttu-id="4d098-141">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="4d098-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 <span data-ttu-id="4d098-142">Предоставляет методы, позволяющие основному приложению задать политику действий, выполняемых в случае сбоев и использование времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="4d098-142">Provides methods that enable the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
 [<span data-ttu-id="4d098-143">Интерфейс ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="4d098-143">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 <span data-ttu-id="4d098-144">Предоставляет методы, позволяющие основному приложению получить проверочные идентификаторы сборки с помощью сборки удостоверяющие сведения, является внутренним для среды CLR, без необходимости создания или понять этот идентификатор.</span><span class="sxs-lookup"><span data-stu-id="4d098-144">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the CLR, without needing to create or understand that identity.</span></span>  
  
 [<span data-ttu-id="4d098-145">Интерфейс ICLRReferenceAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="4d098-145">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)  
 <span data-ttu-id="4d098-146">Предоставляет методы, позволяющие основному приложению управлять набор сборок, на который указывает файл или поток, используя данные идентификации сборки, которые являются внутренними для среды CLR, без необходимости создания или интерпретации этих данных.</span><span class="sxs-lookup"><span data-stu-id="4d098-146">Provides methods that enable the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the CLR, without needing to create or understand those identities.</span></span>  
  
 [<span data-ttu-id="4d098-147">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="4d098-147">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 <span data-ttu-id="4d098-148">Предоставляет возможности, аналогичную [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), с дополнительным методом, чтобы задать интерфейс управления узла.</span><span class="sxs-lookup"><span data-stu-id="4d098-148">Provides capabilities similar to [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), with an additional method to set the host control interface.</span></span>  
  
 [<span data-ttu-id="4d098-149">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="4d098-149">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 <span data-ttu-id="4d098-150">Предоставляет методы для узла для получения сведений о запрошенных задач и для выявления взаимоблокировок в реализации синхронизации.</span><span class="sxs-lookup"><span data-stu-id="4d098-150">Provides methods for the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
 [<span data-ttu-id="4d098-151">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="4d098-151">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 <span data-ttu-id="4d098-152">Предоставляет методы, позволяющие основному приложению отправлять запросы среды CLR, или для предоставления уведомления в среду CLR о соответствующей задаче.</span><span class="sxs-lookup"><span data-stu-id="4d098-152">Provides methods that enable the host to make requests of the CLR, or to provide notification to the CLR about the associated task.</span></span>  
  
 [<span data-ttu-id="4d098-153">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="4d098-153">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 <span data-ttu-id="4d098-154">Предоставляет методы, позволяющие основному приложению запрашивать явным образом, что среда CLR создайте новую задачу, выполняемую задачу и географического языка и языка и региональных параметров для задачи.</span><span class="sxs-lookup"><span data-stu-id="4d098-154">Provides methods that enable the host to request explicitly that the CLR create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
 [<span data-ttu-id="4d098-155">Интерфейс ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="4d098-155">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)  
 <span data-ttu-id="4d098-156">Предоставляет методы для проверки переносимого исполняемого (PE) образа и сообщение об ошибках проверки.</span><span class="sxs-lookup"><span data-stu-id="4d098-156">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
 [<span data-ttu-id="4d098-157">Интерфейс ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="4d098-157">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)  
 <span data-ttu-id="4d098-158">Предоставляет методы для настройки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="4d098-158">Provides methods for configuring the CLR.</span></span>  
  
 [<span data-ttu-id="4d098-159">Интерфейс ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="4d098-159">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)  
 <span data-ttu-id="4d098-160">Предоставляет методы для доступа к пулу потоков.</span><span class="sxs-lookup"><span data-stu-id="4d098-160">Provides methods for accessing the thread pool.</span></span>  
  
 [<span data-ttu-id="4d098-161">Интерфейс IDebuggerInfo</span><span class="sxs-lookup"><span data-stu-id="4d098-161">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)  
 <span data-ttu-id="4d098-162">Предоставляет методы для получения сведений о состоянии служб отладки.</span><span class="sxs-lookup"><span data-stu-id="4d098-162">Provides methods for obtaining information about the state of the debugging services.</span></span>  
  
 [<span data-ttu-id="4d098-163">Интерфейс IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="4d098-163">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)  
 <span data-ttu-id="4d098-164">Предоставляет методы для уведомления узла о блокировании и разблокировании потоков службами отладки.</span><span class="sxs-lookup"><span data-stu-id="4d098-164">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
 [<span data-ttu-id="4d098-165">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="4d098-165">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)  
 <span data-ttu-id="4d098-166">Предоставляет методы для получения информации о сборщик мусора, а также для управления некоторыми аспектами сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="4d098-166">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
 [<span data-ttu-id="4d098-167">Интерфейс IGCHost2</span><span class="sxs-lookup"><span data-stu-id="4d098-167">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)  
 <span data-ttu-id="4d098-168">Предоставляет [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) метод, который позволяет ведущему приложению задать размер сегмент сборки мусора и максимальный размер нулевого поколения в систему сбора мусора значения больше `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="4d098-168">Provides the [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method that enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation zero to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="4d098-169">Интерфейс IGCHostControl</span><span class="sxs-lookup"><span data-stu-id="4d098-169">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)  
 <span data-ttu-id="4d098-170">Предоставляет метод, который позволяет сборщику мусора запросить узла, чтобы изменить ограничения виртуальной памяти.</span><span class="sxs-lookup"><span data-stu-id="4d098-170">Provides a method that enables the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
 [<span data-ttu-id="4d098-171">Интерфейс IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="4d098-171">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)  
 <span data-ttu-id="4d098-172">Предоставляет методы для участия в планировании потоков, которые в противном случае был бы заблокирован для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="4d098-172">Provides methods for participating in the scheduling of threads that would otherwise be blocked for garbage collection.</span></span>  
  
 [<span data-ttu-id="4d098-173">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="4d098-173">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 <span data-ttu-id="4d098-174">Предоставляет методы, которые позволяют ведущему приложению задать набор сборок, которые должны быть загружены средой CLR или узлом.</span><span class="sxs-lookup"><span data-stu-id="4d098-174">Provides methods that enable a host to specify sets of assemblies that should be loaded by the CLR or by the host.</span></span>  
  
 [<span data-ttu-id="4d098-175">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="4d098-175">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 <span data-ttu-id="4d098-176">Предоставляет методы, которые позволяют ведущему приложению загружать сборки и модули независимо от среды CLR.</span><span class="sxs-lookup"><span data-stu-id="4d098-176">Provides methods that enable a host to load assemblies and modules independently of the CLR.</span></span>  
  
 [<span data-ttu-id="4d098-177">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="4d098-177">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 <span data-ttu-id="4d098-178">Предоставляет представление события автоматического сброса реализовано узлом.</span><span class="sxs-lookup"><span data-stu-id="4d098-178">Provides a representation of an auto-reset event implemented by the host.</span></span>  
  
 [<span data-ttu-id="4d098-179">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="4d098-179">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 <span data-ttu-id="4d098-180">Предоставляет методы для настройки загрузки сборок, а также для определения интерфейсов поддерживает узла размещения.</span><span class="sxs-lookup"><span data-stu-id="4d098-180">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
 [<span data-ttu-id="4d098-181">Интерфейс IHostCrst</span><span class="sxs-lookup"><span data-stu-id="4d098-181">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 <span data-ttu-id="4d098-182">Служит в качестве представления главного приложения из критических секций для управления потоками.</span><span class="sxs-lookup"><span data-stu-id="4d098-182">Serves as the host's representation of a critical section for threading.</span></span>  
  
 [<span data-ttu-id="4d098-183">Интерфейс IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="4d098-183">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
 <span data-ttu-id="4d098-184">Предоставляет методы, которые уведомить узел событий в механизм сборки мусора, реализуемых средой CLR.</span><span class="sxs-lookup"><span data-stu-id="4d098-184">Provides methods that notify the host of events in the garbage collection mechanism implemented by the CLR.</span></span>  
  
 [<span data-ttu-id="4d098-185">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="4d098-185">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 <span data-ttu-id="4d098-186">Предоставляет методы, позволяющие среде CLR для взаимодействия с помощью портов завершения ввода-вывода, предоставленный средой размещения.</span><span class="sxs-lookup"><span data-stu-id="4d098-186">Provides methods that enable the CLR to interact with I/O completion ports provided by the host.</span></span>  
  
 [<span data-ttu-id="4d098-187">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="4d098-187">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 <span data-ttu-id="4d098-188">Предоставляет методы для выделения точного количества памяти из кучи через узел среды CLR.</span><span class="sxs-lookup"><span data-stu-id="4d098-188">Provides methods for the CLR to request fine-grained allocations from the heap through the host.</span></span>  
  
 [<span data-ttu-id="4d098-189">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="4d098-189">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 <span data-ttu-id="4d098-190">Предоставляет реализацию главного приложения является представлением событие со сбросом вручную.</span><span class="sxs-lookup"><span data-stu-id="4d098-190">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
 [<span data-ttu-id="4d098-191">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="4d098-191">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 <span data-ttu-id="4d098-192">Предоставляет методы для среды CLR для выполнения запросов виртуальной памяти через узел, вместо использования стандартных функций Win32 виртуальной памяти.</span><span class="sxs-lookup"><span data-stu-id="4d098-192">Provides methods for the CLR to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
 [<span data-ttu-id="4d098-193">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="4d098-193">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 <span data-ttu-id="4d098-194">Предоставляет методы для уведомления узла действий, которые среда CLR выполняет сборку для прерываний, время ожидания или сбоев.</span><span class="sxs-lookup"><span data-stu-id="4d098-194">Provides methods that notify the host of the actions the CLR performs in case of aborts, timeouts, or failures.</span></span>  
  
 [<span data-ttu-id="4d098-195">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="4d098-195">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 <span data-ttu-id="4d098-196">Позволяет поддерживать сведения о контексте безопасности, реализованных в ведущем CLR.</span><span class="sxs-lookup"><span data-stu-id="4d098-196">Enables the CLR to maintain security context information implemented by the host.</span></span>  
  
 [<span data-ttu-id="4d098-197">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="4d098-197">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 <span data-ttu-id="4d098-198">Предоставляет методы, включить доступ к и позволяют управлять контекст безопасности текущего потока.</span><span class="sxs-lookup"><span data-stu-id="4d098-198">Provides methods that enable access to, and control over, the security context of the currently executing thread.</span></span>  
  
 [<span data-ttu-id="4d098-199">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="4d098-199">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 <span data-ttu-id="4d098-200">Предоставляет представление семафора реализовано узлом.</span><span class="sxs-lookup"><span data-stu-id="4d098-200">Provides a representation of a semaphore implemented by the host.</span></span>  
  
 [<span data-ttu-id="4d098-201">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="4d098-201">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 <span data-ttu-id="4d098-202">Предоставляет методы для среды CLR для создания примитивы синхронизации, вызвав узла, а не с помощью функции синхронизации Win32.</span><span class="sxs-lookup"><span data-stu-id="4d098-202">Provides methods for the CLR to create synchronization primitives by calling the host, instead of using the Win32 synchronization functions.</span></span>  
  
 [<span data-ttu-id="4d098-203">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="4d098-203">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 <span data-ttu-id="4d098-204">Предоставляет методы, позволяющие среде CLR для взаимодействия с узлом для управления задачами.</span><span class="sxs-lookup"><span data-stu-id="4d098-204">Provides methods that enable the CLR to communicate with the host to manage tasks.</span></span>  
  
 [<span data-ttu-id="4d098-205">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="4d098-205">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 <span data-ttu-id="4d098-206">Предоставляет методы, позволяющие среде CLR для работы с задачами через узел вместо использования функции потоков или волокон стандартной операционной системе.</span><span class="sxs-lookup"><span data-stu-id="4d098-206">Provides methods that enable the CLR to work with tasks through the host instead of using the standard operating system threading or fiber functions.</span></span>  
  
 [<span data-ttu-id="4d098-207">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="4d098-207">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 <span data-ttu-id="4d098-208">Предоставляет методы для настройки пула потоков и очередь рабочих элементов в пуле потоков среды CLR.</span><span class="sxs-lookup"><span data-stu-id="4d098-208">Provides methods for the CLR to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
 [<span data-ttu-id="4d098-209">Интерфейс IManagedObject</span><span class="sxs-lookup"><span data-stu-id="4d098-209">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)  
 <span data-ttu-id="4d098-210">Предоставляет методы для управления управляемого объекта.</span><span class="sxs-lookup"><span data-stu-id="4d098-210">Provides methods for controlling a managed object.</span></span>  
  
 <span data-ttu-id="4d098-211">«IObjectHandle»</span><span class="sxs-lookup"><span data-stu-id="4d098-211">"IObjectHandle"</span></span>  
 <span data-ttu-id="4d098-212">Предоставляет метод для распаковки объектов маршалинг по значению, косвенного обращения.</span><span class="sxs-lookup"><span data-stu-id="4d098-212">Provides a method for unwrapping marshal-by-value objects from indirection.</span></span>  
  
 [<span data-ttu-id="4d098-213">Интерфейс ITypeName</span><span class="sxs-lookup"><span data-stu-id="4d098-213">ITypeName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypename-interface.md)  
 <span data-ttu-id="4d098-214">Предоставляет методы для получения сведений об имени типа.</span><span class="sxs-lookup"><span data-stu-id="4d098-214">Provides methods for obtaining type name information.</span></span> <span data-ttu-id="4d098-215">(Этот интерфейс поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода).</span><span class="sxs-lookup"><span data-stu-id="4d098-215">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="4d098-216">Интерфейс ITypeNameBuilder</span><span class="sxs-lookup"><span data-stu-id="4d098-216">ITypeNameBuilder Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypenamebuilder-interface.md)  
 <span data-ttu-id="4d098-217">Предоставляет методы для создания имени типа.</span><span class="sxs-lookup"><span data-stu-id="4d098-217">Provides methods for building a type name.</span></span> <span data-ttu-id="4d098-218">(Этот интерфейс поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода).</span><span class="sxs-lookup"><span data-stu-id="4d098-218">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="4d098-219">Интерфейс ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="4d098-219">ITypeNameFactory Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypenamefactory-interface.md)  
 <span data-ttu-id="4d098-220">Предоставляет методы для разбора имени типа.</span><span class="sxs-lookup"><span data-stu-id="4d098-220">Provides methods for deconstructing a type name.</span></span> <span data-ttu-id="4d098-221">(Этот интерфейс поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода).</span><span class="sxs-lookup"><span data-stu-id="4d098-221">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 <span data-ttu-id="4d098-222">«IValidator»</span><span class="sxs-lookup"><span data-stu-id="4d098-222">"IValidator"</span></span>  
 <span data-ttu-id="4d098-223">Предоставляет методы для проверки переносимого исполняемого (PE) образа и сообщение об ошибках проверки.</span><span class="sxs-lookup"><span data-stu-id="4d098-223">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4d098-224">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="4d098-224">Related Sections</span></span>  
 [<span data-ttu-id="4d098-225">Устаревшие интерфейсы размещения CLR и коклассы</span><span class="sxs-lookup"><span data-stu-id="4d098-225">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="4d098-226">Содержит разделы, описывающие интерфейсы размещения, предоставляемые в .NET Framework версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="4d098-226">Contains topics that describe the hosting interfaces provided in the .NET Framework version 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="4d098-227">Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5</span><span class="sxs-lookup"><span data-stu-id="4d098-227">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="4d098-228">Содержит разделы, описывающие интерфейсы размещения, предоставляемые в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="4d098-228">Contains topics that describe the hosting interfaces provided in the .NET Framework 4.</span></span>
