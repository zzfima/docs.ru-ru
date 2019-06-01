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
# <a name="clr-hosting-interfaces"></a>Интерфейсы размещения CLR
В этом разделе описываются интерфейсы, которые неуправляемые узлы могут использовать для интеграции общеязыковой среды выполнения (CLR) в свои приложения. Сведения относятся к .NET Framework версии 2.0 и более поздних версий. Эти интерфейсы позволяют узлу управлять многих других аспектов среды выполнения, чем это было возможно в версиях 1.0 и 1.1 и обеспечивают более тесную интеграцию среды CLR и модели выполнения основного приложения.  
  
 В .NET Framework версий 1.0 и 1.1 модель размещения включена неуправляемый узел загружать среду CLR в процесс для настройки определенных параметров и получения уведомлений о событиях. Тем не менее, как правило, узел и среда CLR выполнялись независимо друг от друга в этом процессе. В .NET Framework версии 2.0 и более поздних версий новые уровни абстракции позволяют узла, который предоставляют многие ресурсы, в настоящее время предоставляемые типы в сборке Win32, и расширить набор возможностей, которые можно настроить узел.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Интерфейс IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 Предоставляет метод, который выполняет обратный вызов для зарегистрированного события.  
  
 [Интерфейс IApartmentCallback](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)  
 Предоставляет методы для осуществления обратных вызовов в подразделении.  
  
 [Интерфейс IAppDomainBinding](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)  
 Предоставляет методы для настройки конфигурации времени выполнения.  
  
 [Интерфейс ICatalogServices](../../../../docs/framework/unmanaged-api/hosting/icatalogservices-interface.md)  
 Предоставляет методы для создания каталога служб. (Этот интерфейс поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода).  
  
 [Интерфейс ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 Предоставляет методы, поддерживающие обмен данными между узлом и о сборках среды CLR.  
  
 [Интерфейс ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 Управляет списком сборок, загружаемых средой CLR, а не приложением.  
  
 [Интерфейс ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 Предоставляет методы для получения доступа к и настроить различные аспекты, среда CLR узла.  
  
 [Интерфейс ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 Предоставляет методы, которые позволяют ведущему приложению связать набор задач с идентификатором и понятное имя.  
  
 [Интерфейс ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 Предоставляет методы, позволяющие основному приложению настроить пользовательские дампы кучи для отчетов об ошибках.  
  
 [Интерфейс ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 Предоставляет методы, позволяющие узлу взаимодействовать с системой сборки мусора среды CLR.  
  
 [Интерфейс ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 Предоставляет методы для оценки и идентифицировать изменения в данные политики для сборки узла.  
  
 [Интерфейс ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 Ведущее приложение может блокировать определенные управляемые классы, методы, свойства и поля запуска частично доверенного кода.  
  
 [Интерфейс ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 Реализует метод обратного вызова, который позволяет ведущему приложению уведомлять среду CLR о состоянии указанного запросов ввода-вывода.  
  
 [Интерфейс ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 Позволяет узлу отчетов об условиях нехватки памяти с помощью подхода, аналогичную Win32 `CreateMemoryResourceNotification` функции.  
  
 [Интерфейс ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 Предоставляет методы, позволяющие основному приложению регистрировать и отменять регистрацию обратных вызовов для событий среды CLR.  
  
 [Интерфейс ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 Предоставляет методы, позволяющие основному приложению задать политику действий, выполняемых в случае сбоев и использование времени ожидания.  
  
 [Интерфейс ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 Предоставляет методы, позволяющие основному приложению получить проверочные идентификаторы сборки с помощью сборки удостоверяющие сведения, является внутренним для среды CLR, без необходимости создания или понять этот идентификатор.  
  
 [Интерфейс ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)  
 Предоставляет методы, позволяющие основному приложению управлять набор сборок, на который указывает файл или поток, используя данные идентификации сборки, которые являются внутренними для среды CLR, без необходимости создания или интерпретации этих данных.  
  
 [Интерфейс ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 Предоставляет возможности, аналогичную [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), с дополнительным методом, чтобы задать интерфейс управления узла.  
  
 [Интерфейс ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 Предоставляет методы для узла для получения сведений о запрошенных задач и для выявления взаимоблокировок в реализации синхронизации.  
  
 [Интерфейс ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 Предоставляет методы, позволяющие основному приложению отправлять запросы среды CLR, или для предоставления уведомления в среду CLR о соответствующей задаче.  
  
 [Интерфейс ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 Предоставляет методы, позволяющие основному приложению запрашивать явным образом, что среда CLR создайте новую задачу, выполняемую задачу и географического языка и языка и региональных параметров для задачи.  
  
 [Интерфейс ICLRValidator](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)  
 Предоставляет методы для проверки переносимого исполняемого (PE) образа и сообщение об ошибках проверки.  
  
 [Интерфейс ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)  
 Предоставляет методы для настройки среды CLR.  
  
 [Интерфейс ICorThreadpool](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)  
 Предоставляет методы для доступа к пулу потоков.  
  
 [Интерфейс IDebuggerInfo](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)  
 Предоставляет методы для получения сведений о состоянии служб отладки.  
  
 [Интерфейс IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)  
 Предоставляет методы для уведомления узла о блокировании и разблокировании потоков службами отладки.  
  
 [Интерфейс IGCHost](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)  
 Предоставляет методы для получения информации о сборщик мусора, а также для управления некоторыми аспектами сбора мусора.  
  
 [Интерфейс IGCHost2](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)  
 Предоставляет [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) метод, который позволяет ведущему приложению задать размер сегмент сборки мусора и максимальный размер нулевого поколения в систему сбора мусора значения больше `DWORD`.  
  
 [Интерфейс IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)  
 Предоставляет метод, который позволяет сборщику мусора запросить узла, чтобы изменить ограничения виртуальной памяти.  
  
 [Интерфейс IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)  
 Предоставляет методы для участия в планировании потоков, которые в противном случае был бы заблокирован для сборки мусора.  
  
 [Интерфейс IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 Предоставляет методы, которые позволяют ведущему приложению задать набор сборок, которые должны быть загружены средой CLR или узлом.  
  
 [Интерфейс IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 Предоставляет методы, которые позволяют ведущему приложению загружать сборки и модули независимо от среды CLR.  
  
 [Интерфейс IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 Предоставляет представление события автоматического сброса реализовано узлом.  
  
 [Интерфейс IHostControl](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 Предоставляет методы для настройки загрузки сборок, а также для определения интерфейсов поддерживает узла размещения.  
  
 [Интерфейс IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 Служит в качестве представления главного приложения из критических секций для управления потоками.  
  
 [Интерфейс IHostGCManager](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
 Предоставляет методы, которые уведомить узел событий в механизм сборки мусора, реализуемых средой CLR.  
  
 [Интерфейс IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 Предоставляет методы, позволяющие среде CLR для взаимодействия с помощью портов завершения ввода-вывода, предоставленный средой размещения.  
  
 [Интерфейс IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 Предоставляет методы для выделения точного количества памяти из кучи через узел среды CLR.  
  
 [Интерфейс IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 Предоставляет реализацию главного приложения является представлением событие со сбросом вручную.  
  
 [Интерфейс IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 Предоставляет методы для среды CLR для выполнения запросов виртуальной памяти через узел, вместо использования стандартных функций Win32 виртуальной памяти.  
  
 [Интерфейс IHostPolicyManager](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 Предоставляет методы для уведомления узла действий, которые среда CLR выполняет сборку для прерываний, время ожидания или сбоев.  
  
 [Интерфейс IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 Позволяет поддерживать сведения о контексте безопасности, реализованных в ведущем CLR.  
  
 [Интерфейс IHostSecurityManager](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 Предоставляет методы, включить доступ к и позволяют управлять контекст безопасности текущего потока.  
  
 [Интерфейс IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 Предоставляет представление семафора реализовано узлом.  
  
 [Интерфейс IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 Предоставляет методы для среды CLR для создания примитивы синхронизации, вызвав узла, а не с помощью функции синхронизации Win32.  
  
 [Интерфейс IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 Предоставляет методы, позволяющие среде CLR для взаимодействия с узлом для управления задачами.  
  
 [Интерфейс IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 Предоставляет методы, позволяющие среде CLR для работы с задачами через узел вместо использования функции потоков или волокон стандартной операционной системе.  
  
 [Интерфейс IHostThreadPoolManager](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 Предоставляет методы для настройки пула потоков и очередь рабочих элементов в пуле потоков среды CLR.  
  
 [Интерфейс IManagedObject](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)  
 Предоставляет методы для управления управляемого объекта.  
  
 «IObjectHandle»  
 Предоставляет метод для распаковки объектов маршалинг по значению, косвенного обращения.  
  
 [Интерфейс ITypeName](../../../../docs/framework/unmanaged-api/hosting/itypename-interface.md)  
 Предоставляет методы для получения сведений об имени типа. (Этот интерфейс поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода).  
  
 [Интерфейс ITypeNameBuilder](../../../../docs/framework/unmanaged-api/hosting/itypenamebuilder-interface.md)  
 Предоставляет методы для создания имени типа. (Этот интерфейс поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода).  
  
 [Интерфейс ITypeNameFactory](../../../../docs/framework/unmanaged-api/hosting/itypenamefactory-interface.md)  
 Предоставляет методы для разбора имени типа. (Этот интерфейс поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода).  
  
 «IValidator»  
 Предоставляет методы для проверки переносимого исполняемого (PE) образа и сообщение об ошибках проверки.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Устаревшие интерфейсы размещения CLR и коклассы](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 Содержит разделы, описывающие интерфейсы размещения, предоставляемые в .NET Framework версий 1.0 и 1.1.  
  
 [Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 Содержит разделы, описывающие интерфейсы размещения, предоставляемые в .NET Framework 4.
