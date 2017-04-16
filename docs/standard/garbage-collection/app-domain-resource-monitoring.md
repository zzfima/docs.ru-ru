---
title: "Application Domain Resource Monitoring | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "monitoring managed memory use by application domain"
  - "application domains, memory use"
  - "memory use, monitoring"
  - "application domains, resource monitoring"
ms.assetid: 318bedf8-7f35-4f00-b34a-2b7b8e3fa315
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Application Domain Resource Monitoring
Отслеживание ресурсов домена приложения \(ARM\) позволяет приложениям следить, как домен приложения использует ресурсы процессора и памяти.  Это полезно для приложений, таких как ASP.NET, использующих большое количество приложений в длительном процессе.  Ведущее приложение может выгрузить домен приложения, который неблагоприятно влияет на быстродействие всего процесса, но только если оно может определить проблемное приложение.  ARM содержит сведения, которые можно использовать для принятия подобных решений.  
  
 Например, у размещенной службы может быть несколько приложений, выполняемых на сервере ASP.NET.  Если одно из приложений процесса начинает потреблять слишком много ресурсов памяти или процессора, служба размещения может использовать ARM, чтобы определить домен приложения, ставший причиной проблемы.  
  
 ARM потребляет немного ресурсов и может использоваться в работающих приложениях.  Собранные данные доступны с помощью журнала трассировки событий Windows \(ETW\) или напрямую с помощью управляемых и неуправляемых интерфейсов API.  
  
## Включение отслеживания ресурсов  
 ARM можно включить четырьмя способами: применяя конфигурационный файл при запуске среды CLR, с помощью неуправляемого интерфейса API размещения, используя управляемый код или прослушивая события ETW для ARM.  
  
 Сразу же после своего включения ARM начинает сбор данных для всех доменов приложений в процессе.  Если домен приложения был создан до включения ARM, накопление данных начинается после включения ARM, а не при создании домена приложения. Включенный ARM отключить нельзя.  
  
-   Можно включить ARM при запуске среды CLR, добавив элемент [\<appDomainResourceMonitoring\>](../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md) в файл конфигурации и установив атрибуту `enabled` значение `true`.  Значение `false` \(по умолчанию\) означает только, что ARM не включается при запуске, его можно активировать позднее, используя один из других механизмов активации.  
  
-   Ведущее приложение может включить ARM, запрашивая интерфейс размещения [ICLRAppDomainResourceMonitor](../../../ocs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md).  После успешного получения этого интерфейса ARM оказывается включенным.  
  
-   Чтобы включить ARM из управляемого кода, можно задать для статического \(`Shared` в Visual Basic\) свойства <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=fullName> значение `true`.  ARM включается сразу же после задания этого свойства.  
  
-   Можно включить ARM и после запуска, прослушивая события ETW.  При включении открытого поставщика `Microsoft-Windows-DotNETRuntime` с помощью ключевого слова `AppDomainResourceManagementKeyword` ARM включается и начинает создавать события для всех доменов приложений.  Чтобы связать данные с доменами приложений и потоками, также необходимо включить поставщик `Microsoft-Windows-DotNETRuntimeRundown` с ключевым словом `ThreadingKeyword`.  
  
## Использование ARM  
 ARM предоставляет данные о суммарном времени процессора, используемом доменом приложения, и три вида данных об использовании памяти.  
  
-   **Общее время процессора для домена приложения, в секундах**: рассчитывается путем сложения времен потоков, сообщенных операционной системой, для всех потоков, выполнявшихся в домене приложения во время его существования.  Блокированные или спящие потоки не используют время процессора.  Когда поток вызывает неуправляемый код, время, в течение которого поток выполнял неуправляемый код, учитывается для домена приложения, из которого был выполнен вызов.  
  
    -   Управляемый интерфейс API: свойство <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=fullName>.  
  
    -   Интерфейс API размещения: метод [ICLRAppDomainResourceMonitor::GetCurrentCpuTime](../Topic/ICLRAppDomainResourceMonitor::GetCurrentCpuTime%20Method.md).  
  
    -   События ETW: события `ThreadCreated`, `ThreadAppDomainEnter` и `ThreadTerminated`.  Сведения о поставщиках и ключевых словах см. в подразделе, описывающем события отслеживания ресурсов домена приложения, в разделе [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md).  
  
-   **Общие управляемые распределения, выполненные доменом распределения во время существования, в байтах**: общие выделения не всегда отражают использование памяти доменом приложения, так как распределенные объекты могут быть короткоживущими.  Но если приложение распределяет и освобождает большое количество объектов, стоимость распределений может быть значительной.  
  
    -   Управляемый интерфейс API: свойство <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=fullName>.  
  
    -   Интерфейс API размещения: метод [ICLRAppDomainResourceMonitor::GetCurrentAllocated](../Topic/ICLRAppDomainResourceMonitor::GetCurrentAllocated%20Method.md).  
  
    -   События ETW: событие `AppDomainMemAllocated`, поле `Allocated`.  
  
-   **Управляемая память, в байтах, на которую ссылается домен приложения и которая пережила последнюю полную блокирующую сборку мусора**: это число оказывается точным только после полной блокирующей сборки. \(Это отличается от параллельных сборок мусора, которые выполняются в фоновом режиме и не блокируют приложение.\) Например, перегрузка метода <xref:System.GC.Collect?displayProperty=fullName> вызывает полную блокирующую сборку мусора.  
  
    -   Управляемый интерфейс API: свойство <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=fullName>.  
  
    -   Интерфейс API размещения: метод [ICLRAppDomainResourceMonitor::GetCurrentSurvived](../Topic/ICLRAppDomainResourceMonitor::GetCurrentSurvived%20Method.md), параметр `pAppDomainBytesSurvived`.  
  
    -   События ETW: событие `AppDomainMemSurvived`, поле `Survived`.  
  
-   **Общая управляемая память, в байтах, на которую ссылается процесс и которая пережила последнюю полную блокирующую сборку мусора**: с этим числом можно сравнить память, сохранившуюся в куче для отдельных доменов приложений.  
  
    -   Управляемый интерфейс API: свойство <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=fullName>.  
  
    -   Интерфейс API размещения: метод [ICLRAppDomainResourceMonitor::GetCurrentSurvived](../Topic/ICLRAppDomainResourceMonitor::GetCurrentSurvived%20Method.md), параметр `pTotalBytesSurvived`.  
  
    -   События ETW: событие `AppDomainMemSurvived`, поле `ProcessSurvived`.  
  
### Определение момента выполнения полной блокирующей сборки мусора  
 Чтобы определить, когда показатели счетчиков памяти, сохранившиеся в куче, являются точными, нужно знать о полной блокирующей сборке мусора, как только она происходит.  Используемый для этого метод зависит от интерфейса API, применяемого для получения статистики ARM.  
  
#### Управляемый интерфейс API  
 Если применяются свойства класса <xref:System.AppDomain>, для регистрации уведомления о полных сборках мусора можно использовать метод <xref:System.GC.RegisterForFullGCNotification%2A?displayProperty=fullName>.  Используемый порог неважен, так как ожидается завершение сборки мусора, а не ее наступления.  Затем можно вызвать метод <xref:System.GC.WaitForFullGCComplete%2A?displayProperty=fullName>, выполняющий блокировку до завершения полной сборки мусора.  Можно создать поток, вызывающий этот метод в цикле и выполняющий весь необходимый анализ после возвращения управления методом.  
  
 Либо можно периодически вызывать метод <xref:System.GC.CollectionCount%2A?displayProperty=fullName>, проверяя, не увеличился ли счетчик сборок мусора для поколения 2.  В зависимости от частоты опроса этот метод может не обеспечивать точное указание выполнения полной сборки мусора.  
  
#### Интерфейс API размещения  
 При использовании неуправляемого API размещения ведущее приложение должно передать среде CLR реализацию интерфейса [IHostGCManager](../../../ocs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md).  Среда CLR вызывает метод [IHostGCManager::SuspensionEnding](../Topic/IHostGCManager::SuspensionEnding%20Method.md) при возобновлении выполнения потоков, приостановленных во время сборки мусора.  Среда CLR передает поколение выполненной сборки мусора как параметр метода, чтобы ведущее приложение могло определить, является ли сборка полной или частичной.  Созданная разработчиком реализация метода [IHostGCManager::SuspensionEnding](../Topic/IHostGCManager::SuspensionEnding%20Method.md) может запросить память, сохранившуюся в куче, чтобы гарантировать получение счетчиков сразу же после их обновления.  
  
## См. также  
 <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=fullName>   
 [Интерфейс ICLRAppDomainResourceMonitor](../../../ocs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)   
 [\<appDomainResourceMonitoring\>](../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)   
 [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md)