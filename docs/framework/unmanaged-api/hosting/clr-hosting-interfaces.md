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
# <a name="clr-hosting-interfaces"></a>Интерфейсы размещения CLR
В этом разделе описываются интерфейсы, которые неуправляемые узлы могут использовать для интеграции среды CLR в свои приложения. Информация относится к .NET Framework версии 2,0 и более поздним версиям. Эти интерфейсы позволяют ведущему приложению управлять многими другими аспектами среды выполнения, чем было возможно в версиях 1,0 и 1,1, и обеспечивать более тесную интеграцию между средой CLR и моделью выполнения узла.  
  
 В .NET Framework версии 1,0 и 1,1 модель размещения позволяла неуправляемому узлу загружать среду CLR в процесс, настраивать определенные параметры и получать уведомления о событиях. Однако в общем случае узел и среда CLR выполнялись независимо в этом процессе. В .NET Framework версии 2,0 и более поздних новые уровни абстракции позволяют ведущему приложению предоставлять множество ресурсов, предоставляемых типами в сборке Win32, и расширять набор возможностей, которые может настраивать узел.  
  
## <a name="in-this-section"></a>Содержание  
 [Интерфейс IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 Предоставляет метод, который выполняет обратный вызов для зарегистрированного события.  
  
 [Интерфейс IApartmentCallback](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)  
 Предоставляет методы для выполнения обратных вызовов в апартаменте.  
  
 [Интерфейс IAppDomainBinding](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)  
 Предоставляет методы для настройки конфигурации времени выполнения.  
  
 [Интерфейс ICatalogServices](../../../../docs/framework/unmanaged-api/hosting/icatalogservices-interface.md)  
 Предоставляет методы для каталогизации служб. (Этот интерфейс поддерживает .NET Frameworkную инфраструктуру и не предназначен для непосредственного использования в коде.)  
  
 [Интерфейс ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 Предоставляет методы, поддерживающие взаимодействие между узлом и средой CLR о сборках.  
  
 [Интерфейс ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 Управляет списком сборок, загружаемых средой CLR, а не узлом.  
  
 [Интерфейс ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 Предоставляет узлу методы для получения доступа и настройки различных аспектов среды CLR.  
  
 [Интерфейс ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 Предоставляет методы, позволяющие узлу связать набор задач с идентификатором и понятным именем.  
  
 [Интерфейс ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 Предоставляет методы, позволяющие основному приложению настраивать дампы пользовательской кучи для отчетов об ошибках.  
  
 [Интерфейс ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 Предоставляет методы, позволяющие основному приложению взаимодействовать с системой сборки мусора среды CLR.  
  
 [Интерфейс ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 Предоставляет методам для узла возможность оценивать и передавать изменения в сведениях о политике для сборок.  
  
 [Интерфейс ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 Позволяет узлу блокировать выполнение конкретных управляемых классов, методов, свойств и полей в частично доверяемом коде.  
  
 [Интерфейс ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 Реализует метод обратного вызова, который позволяет ведущему приложению уведомлять среду CLR о состоянии указанных запросов ввода-вывода.  
  
 [Интерфейс ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 Позволяет узлу сообщать об условиях нехватки памяти с помощью подхода, аналогичного функции Win32 `CreateMemoryResourceNotification`.  
  
 [Интерфейс ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 Предоставляет методы, позволяющие основному приложению регистрировать и отменять регистрацию обратных вызовов для событий CLR.  
  
 [Интерфейс ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 Предоставляет методы, позволяющие основному приложению указывать действия политики, выполняемые в случае сбоев и истечения времени ожидания.  
  
 [Интерфейс ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 Предоставляет методы, позволяющие основному приложению получать идентификаторы проверки сборки с помощью сведений об удостоверении сборки, которые являются внутренними для CLR, без необходимости создания или понимания этого удостоверения.  
  
 [Интерфейс ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)  
 Предоставляет методы, позволяющие основному приложению манипулировать набором сборок, на которые ссылается файл или поток, с помощью данных идентификации сборок, которые являются внутренними для CLR, без необходимости создавать или анализировать эти удостоверения.  
  
 [Интерфейс ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 Предоставляет возможности, аналогичные [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), и дополнительный метод для установки интерфейса управления узла.  
  
 [Интерфейс ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 Предоставляет основному приложению методы для получения сведений о запрошенных задачах и обнаружения взаимоблокировок в своей реализации синхронизации.  
  
 [Интерфейс ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 Предоставляет методы, позволяющие основному приложению выполнять запросы среды CLR или предоставлять для среды CLR уведомление о связанной задаче.  
  
 [Интерфейс ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 Предоставляет методы, позволяющие основному приложению запрашивать явно, что среда CLR создает новую задачу, получает текущую выполняемую задачу и задает язык и региональные параметры для задачи.  
  
 [Интерфейс ICLRValidator](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)  
 Предоставляет методы для проверки переносимых исполняемых (PE) образов и создания отчетов об ошибках проверки.  
  
 [Интерфейс ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)  
 Предоставляет методы для настройки среды CLR.  
  
 [Интерфейс ICorThreadpool](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)  
 Предоставляет методы для доступа к пулу потоков.  
  
 [Интерфейс IDebuggerInfo](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)  
 Предоставляет методы для получения сведений о состоянии служб отладки.  
  
 [Интерфейс IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)  
 Предоставляет методы для уведомления узла о блокировке и разблокировке потоков службами отладки.  
  
 [Интерфейс IGCHost](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)  
 Предоставляет методы для получения сведений о системе сборки мусора и для управления некоторыми аспектами сборки мусора.  
  
 [Интерфейс IGCHost2](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)  
 Предоставляет метод [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) , позволяющий основному приложению задавать размер сегмента сборки мусора и максимальный размер нулевого поколения системы сборки мусора для значений, превышающих `DWORD`.  
  
 [Интерфейс IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)  
 Предоставляет метод, позволяющий сборщику мусора запрашивать изменение ограничений виртуальной памяти на узле.  
  
 [Интерфейс IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)  
 Предоставляет методы для участия в планировании потоков, которые в противном случае были бы заблокированы для сборки мусора.  
  
 [Интерфейс IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 Предоставляет методы, позволяющие основному приложению указывать наборы сборок, которые должны загружаться средой CLR или узлом.  
  
 [Интерфейс IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 Предоставляет методы, позволяющие основному приложению загружать сборки и модули независимо от среды CLR.  
  
 [Интерфейс IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 Предоставляет представление события автоматического сброса, реализованного хостом.  
  
 [Интерфейс IHostControl](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 Предоставляет методы для настройки загрузки сборок и для определения того, какие интерфейсы размещения поддерживает узел.  
  
 [Интерфейс IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 Служит в качестве представления критической секции для потоков в основном приложении.  
  
 [Интерфейс IHostGCManager](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
 Предоставляет методы, которые уведомляют узел о событиях в механизме сборки мусора, реализованном средой CLR.  
  
 [Интерфейс IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 Предоставляет методы, позволяющие среде CLR взаимодействовать с портами завершения ввода-вывода, предоставляемыми узлом.  
  
 [Интерфейс IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 Предоставляет методы для CLR, чтобы запрашивать детализированные выделения из кучи через узел.  
  
 [Интерфейс IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 Предоставляет реализацию представления события ручного сброса в узле.  
  
 [Интерфейс IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 Предоставляет методы для среды CLR для выполнения запросов к виртуальной памяти через основное приложение вместо использования стандартных функций виртуальной памяти Win32.  
  
 [Интерфейс IHostPolicyManager](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 Предоставляет методы, уведомляющие узел о действиях, выполняемых средой CLR в случае прерываний, времени ожидания или сбоев.  
  
 [Интерфейс IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 Позволяет среде CLR поддерживать сведения о контексте безопасности, реализуемые узлом.  
  
 [Интерфейс IHostSecurityManager](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 Предоставляет методы, обеспечивающие доступ к контексту безопасности выполняющегося потока и управление им.  
  
 [Интерфейс IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 Предоставляет представление семафора, реализованного узлом.  
  
 [Интерфейс IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 Предоставляет методы для среды CLR для создания примитивов синхронизации путем вызова узла вместо использования функций синхронизации Win32.  
  
 [Интерфейс IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 Предоставляет методы, позволяющие среде CLR взаимодействовать с узлом для управления задачами.  
  
 [Интерфейс IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 Предоставляет методы, позволяющие среде CLR работать с задачами через основное приложение, а не использовать стандартные функции потоков или волоконно-оптической операционной системы.  
  
 [Интерфейс IHostThreadPoolManager](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 Предоставляет методы для среды CLR для настройки пула потоков и постановки рабочих элементов в очередь в пул потоков.  
  
 [Интерфейс IManagedObject](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)  
 Предоставляет методы для управления управляемым объектом.  
  
 "Иобжександле"  
 Предоставляет метод для распаковки объектов, перенаправляемых по значению, из косвенного обращения.  
  
 [Интерфейс ITypeName](../../../../docs/framework/unmanaged-api/hosting/itypename-interface.md)  
 Предоставляет методы для получения сведений о имени типа. (Этот интерфейс поддерживает .NET Frameworkную инфраструктуру и не предназначен для непосредственного использования в коде.)  
  
 [Интерфейс ITypeNameBuilder](../../../../docs/framework/unmanaged-api/hosting/itypenamebuilder-interface.md)  
 Предоставляет методы для создания имени типа. (Этот интерфейс поддерживает .NET Frameworkную инфраструктуру и не предназначен для непосредственного использования в коде.)  
  
 [Интерфейс ITypeNameFactory](../../../../docs/framework/unmanaged-api/hosting/itypenamefactory-interface.md)  
 Предоставляет методы для деконструирования имени типа. (Этот интерфейс поддерживает .NET Frameworkную инфраструктуру и не предназначен для непосредственного использования в коде.)  
  
 IValidator  
 Предоставляет методы для проверки переносимых исполняемых (PE) образов и создания отчетов об ошибках проверки.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Устаревшие интерфейсы размещения CLR и коклассы](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 Содержит разделы, описывающие интерфейсы размещения, предоставляемые в .NET Framework версии 1,0 и 1,1.  
  
 [Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 Содержит разделы, описывающие интерфейсы размещения, предоставляемые в .NET Framework 4.
