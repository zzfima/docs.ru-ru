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
ms.openlocfilehash: 3efdf649d0039f2eb6b39d5cb17c839b90e97508
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="clr-hosting-interfaces"></a>Интерфейсы размещения CLR
В этом разделе описываются интерфейсы, которые неуправляемые узлов можно использовать для интеграции общеязыковой среды выполнения (CLR) в свои приложения. Сведения касаются платформы .NET Framework версии 2.0 и более поздних версиях. Эти интерфейсы позволяют основному приложению управлять многих других аспектов среды выполнения, чем было возможно в версиях 1.0 и 1.1 и обеспечивают более тесную интеграцию среды CLR и модели выполнения основного приложения.  
  
 В .NET Framework версий 1.0 и 1.1 модель размещения позволяла неуправляемому основному приложению загрузить среду CLR в процесс для настройки определенных параметров и получения уведомлений о событиях. Тем не менее, как правило, узел и среда CLR выполнялись независимо друг от друга в этом процессе. В .NET Framework версии 2.0 и более поздних версиях новые уровни абстракции позволили основному приложению предоставлять множество ресурсов, предоставляемых в данный момент на типы в сборке Win32, и расширить набор возможностей, которые можно настроить узел.  
  
## <a name="in-this-section"></a>Содержание  
 [IActionOnCLREvent-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 Предоставляет метод, который выполняет обратный вызов для зарегистрированного события.  
  
 [Iapartmentcallback-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)  
 Предоставляет методы для осуществления обратных вызовов в подразделении.  
  
 [Iappdomainbinding-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)  
 Предоставляет методы для параметра конфигурации времени выполнения.  
  
 [Icatalogservices-интерфейс](../../../../docs/framework/unmanaged-api/hosting/icatalogservices-interface.md)  
 Предоставляет методы для служб каталогизации. (Этот интерфейс поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода).  
  
 [Iclrassemblyidentitymanager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 Предоставляет методы, поддерживающие обмен данными между узлом и о сборках среды CLR.  
  
 [ICLRAssemblyReferenceList-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 Управляет списком сборок, загружаемых средой CLR, а не приложением.  
  
 [ICLRControl-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 Предоставляет методы для узла, чтобы получить доступ к и настроить различные аспекты среды CLR.  
  
 [Iclrdebugmanager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 Предоставляет методы, позволяющие ведущему приложению связать набор задач с идентификатором и понятным именем.  
  
 [Iclrerrorreportingmanager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 Предоставляет методы, позволяющие основному приложению настроить пользовательские дампы кучи для отчетов об ошибках.  
  
 [Iclrgcmanager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 Предоставляет методы, позволяющие хост-приложению взаимодействовать с системой сборки мусора среды CLR.  
  
 [Iclrhostbindingpolicymanager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 Предоставляет методы для вычисления и изменения в сведениях о политике для сборок взаимодействия узла.  
  
 [Iclrhostprotectionmanager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 Ведущее приложение может блокировать определенные управляемые классы, методы, свойства и поля при выполнении в частично доверенный код.  
  
 [ICLRIoCompletionManager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 Реализует метод обратного вызова, который позволяет ведущему приложению уведомления среды CLR о состоянии указанных запросов ввода-вывода.  
  
 [Iclrmemorynotificationcallback-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 Позволяет ведущему приложению отчетов об условиях нехватки памяти с помощью подход, аналогичный Win32 `CreateMemoryResourceNotification` функции.  
  
 [ICLROnEventManager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 Предоставляет методы, позволяющие основному приложению регистрировать и отменять регистрацию обратные вызовы для событий среды CLR.  
  
 [Интерфейс ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 Предоставляет методы, позволяющие основному приложению задать действия политики, которые необходимо выполнить в случае сбоев и увеличение времени ожидания.  
  
 [ICLRProbingAssemblyEnum-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 Предоставляет методы, позволяющие основному приложению получить проверочные идентификаторы сборки с помощью сведения об удостоверении сборки, которые являются внутренними для среды CLR, без необходимости создания или понять их подлинность.  
  
 [ICLRReferenceAssemblyEnum-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)  
 Предоставляет методы, позволяющие основному приложению управлять набор сборок, на который указывает файл или поток, используя данные идентификации сборки, которые являются внутренними для среды CLR, без необходимости создания или интерпретации этих данных.  
  
 [ICLRRuntimeHost-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 Предоставляет возможности, аналогичные для [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), с дополнительным методом, позволяющим задать интерфейс управления узла.  
  
 [ICLRSyncManager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 Предоставляет методы для узла, чтобы получить сведения о запрашиваемых задачах и взаимоблокировки в реализации синхронизации.  
  
 [ICLRTask-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 Предоставляет методы, позволяющие основному приложению выполнять запросы среды CLR или предоставлять уведомления в среде CLR о соответствующей задаче.  
  
 [ICLRTaskManager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 Предоставляет методы, позволяющие основному приложению запрашивать явным образом, среда CLR создать новую задачу, выполняемую задачу и устанавливаются географического языка и языка и региональных параметров для задачи.  
  
 [ICLRValidator-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)  
 Предоставляет методы для проверки переносимого исполняемого (PE) образа и возврат ошибок проверки.  
  
 [Icorconfiguration-интерфейс](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)  
 Предоставляет методы для настройки среды CLR.  
  
 [Icorthreadpool-интерфейс](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)  
 Предоставляет методы для доступа к пулу потоков.  
  
 [Idebuggerinfo-интерфейс](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)  
 Предоставляет методы для получения сведений о состоянии служб отладки.  
  
 [Idebuggerthreadcontrol-интерфейс](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)  
 Предоставляет методы для уведомления узла о блокировании и разблокировании потоков службами отладки.  
  
 [Igchost-интерфейс](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)  
 Предоставляет методы для получения сведений о системе сборки мусора, а также для управления некоторыми аспектами сбора мусора.  
  
 [Igchost2-интерфейс](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)  
 Предоставляет [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) метод, который позволяет ведущему приложению установите размер сегмент сборки мусора и максимальный размер нулевого поколения и система сбора мусора для значений больше `DWORD`.  
  
 [Igchostcontrol-интерфейс](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)  
 Предоставляет метод, который позволяет сборщику мусора запрашивать основное приложение для изменения ограничений на объем виртуальной памяти.  
  
 [Igcthreadcontrol-интерфейс](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)  
 Предоставляет методы для участия в планировании потоков, которые в противном случае были бы заблокированы для сборки мусора.  
  
 [Ihostassemblymanager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 Предоставляет методы, позволяющие хост-приложению задать набор сборок, которые должны быть загружены средой CLR или средой размещения.  
  
 [IHostAssemblyStore-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 Предоставляет методы, позволяющие основному приложению загружать сборки и модули независимо от среды CLR.  
  
 [IHostAutoEvent-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 Предоставляет представление события автоматического сброса, реализуемых основным приложением.  
  
 [IHostControl-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 Предоставляет методы для настройки загрузки сборок, а также для определения интерфейсов размещения, поддерживаемых основным приложением.  
  
 [IHostCrst-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 Служит в качестве узла представления критической секции для работы с потоками.  
  
 [IHostGCManager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
 Предоставляет методы, уведомляющие основное приложение о событиях в механизме сборки мусора, реализуемых средой CLR.  
  
 [IHostIoCompletionManager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 Предоставляет методы, позволяющие взаимодействовать с порты завершения ввода-вывода, предоставленный средой размещения среды CLR.  
  
 [IHostMalloc-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 Предоставляет методы для выделения точного количества памяти из кучи посредством основного приложения среды CLR.  
  
 [IHostManualEvent-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 Предоставляет реализацию узла представления событие ручного сброса.  
  
 [IHostMemoryManager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 Предоставляет методы для осуществления запросов виртуальной памяти через узел, вместо использования стандартных функций Win32 виртуальной памяти среды CLR.  
  
 [IHostPolicyManager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 Предоставляет методы, уведомляющие основное приложение действий, выполняемых средой CLR в случае возникновения прерываний, время ожидания или сбоев.  
  
 [IHostSecurityContext-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 Позволяет среде CLR возможность сохранять сведения о контексте безопасности, реализуемых основным приложением.  
  
 [IHostSecurityManager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 Предоставляет методы, включающие доступ к и контроль над контекст безопасности текущего потока.  
  
 [IHostSemaphore-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 Предоставляет представление семафора, реализуемых основным приложением.  
  
 [Ihostsyncmanager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 Предоставляет методы для среды CLR для создания примитивы синхронизации, вызвав узла, а не с помощью функции синхронизации Win32.  
  
 [IHostTask-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 Предоставляет методы, позволяющие среде CLR для связи с основным приложением для управления задачами.  
  
 [IHostTaskManager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 Предоставляет методы, позволяющие среде CLR работать с задачами посредством основного приложения, вместо того чтобы использовать функции работы с потоками или волокон стандартной операционной системе.  
  
 [IHostThreadPoolManager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 Предоставляет методы для настройки пула потоков и очередь рабочих элементов в пуле потоков среды CLR.  
  
 [IManagedObject-интерфейс](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)  
 Предоставляет методы для управления управляемыми объектами.  
  
 «IObjectHandle»  
 Предоставляет метод для распаковки маршалирования по значению объектов косвенного обращения.  
  
 [Itypename-интерфейс](../../../../docs/framework/unmanaged-api/hosting/itypename-interface.md)  
 Предоставляет методы для получения сведений об имени типа. (Этот интерфейс поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода).  
  
 [Itypenamebuilder-интерфейс](../../../../docs/framework/unmanaged-api/hosting/itypenamebuilder-interface.md)  
 Предоставляет методы для построения имени типа. (Этот интерфейс поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода).  
  
 [Itypenamefactory-интерфейс](../../../../docs/framework/unmanaged-api/hosting/itypenamefactory-interface.md)  
 Предоставляет методы для разбора имени типа. (Этот интерфейс поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода).  
  
 «IValidator»  
 Предоставляет методы для проверки переносимого исполняемого (PE) образа и возврат ошибок проверки.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Интерфейсы размещения устаревшие CLR и Coclasses](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 Содержит разделы, описывающие интерфейсы размещения, предоставляемые в .NET Framework версий 1.0 и 1.1.  
  
 [Интерфейсы размещения CLR, добавленные в .NET Framework 4 и 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 Содержит разделы, описывающие интерфейсы размещения, предоставляемые в [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].
