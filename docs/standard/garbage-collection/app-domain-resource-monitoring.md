---
title: "Отслеживание ресурсов домена приложения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- monitoring managed memory use by application domain
- application domains, memory use
- memory use, monitoring
- application domains, resource monitoring
ms.assetid: 318bedf8-7f35-4f00-b34a-2b7b8e3fa315
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 62a514f94857044af5020d36a1cfd6ce06741ac7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="application-domain-resource-monitoring"></a>Отслеживание ресурсов домена приложения
Домен отслеживания ресурсов приложения (ARM) позволяет узлам отслеживать использование ресурсов ЦП и памяти доменом приложения. Это полезно для узлов, например ASP.NET, использующие нескольких доменов приложений в процессе длительное время. Узел можно выгрузить домен приложения, который отрицательно влияет на производительность всего процесса, но только если оно может определить проблемное приложение. ARM предоставляет сведения, которые можно использовать для помощи в принятии таких решений.  
  
 Например услуги размещения может иметь несколько приложений, выполняемых на сервере ASP.NET. Если одно приложение в процессе начинает потреблять слишком много памяти или слишком много процессорного времени, службы размещения позволяют ARM определить домен приложения, который вызывает проблему.  
  
 ARM очень достаточно прост для использования в работающих приложениях. Информацию можно получить с помощью трассировки событий для Windows (ETW) или напрямую с помощью управляемых и неуправляемых интерфейсов API.  
  
## <a name="enabling-resource-monitoring"></a>Включение отслеживания ресурсов  
 ARM можно включить четырьмя способами: путем указания файла конфигурации при запуске общеязыковой среды выполнения (CLR), с помощью неуправляемого интерфейса API размещения, с помощью управляемого кода или путем прослушивания события трассировки событий Windows ARM.  
  
 Сразу после включения ARM начинает сбор данных для всех доменов приложений в процессе. Если домен приложения был создан до включения ARM, накопление данных начинается после включения ARM, а не при создании домена приложения. После включения ARM отключить нельзя.  
  
-   Можно включить ARM при запуске среды CLR, добавив [ \<appDomainResourceMonitoring >](../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md) элемент в файл конфигурации и параметр `enabled` атрибут `true`. Значение `false` (по умолчанию) означает только, что ARM не включается при запуске, можно сделать это позже с помощью одного из других механизмов активации.  
  
-   Узел можно включить ARM, запрашивая [ICLRAppDomainResourceMonitor](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) размещение интерфейса. После успешного получения этого интерфейса ARM включен.  
  
-   Управляемый код можно включить ARM путем задания статического (`Shared` в Visual Basic) <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> свойства `true`. Как только это свойство задано, включения ARM.  
  
-   Можно включить ARM после запуска, прослушивание событий трассировки событий Windows. ARM включается и начинает создавать события для всех доменов приложений, при включении общего поставщика `Microsoft-Windows-DotNETRuntime` с помощью `AppDomainResourceManagementKeyword` ключевое слово. Чтобы связать данные с потоками и доменами приложений, необходимо также включить `Microsoft-Windows-DotNETRuntimeRundown` поставщика с `ThreadingKeyword` ключевое слово.  
  
## <a name="using-arm"></a>Использование ARM  
 ARM предоставляет полное время процессора, используемый для домена приложения и три вида данных об использовании памяти.  
  
-   **Общее время процессора для домена приложения, в секундах**: рассчитывается путем сложения времен потоков данным операционной системы для всех потоков, выполнявшихся в домене приложения во время существования. Заблокированные или находится в спящем режиме потоки не используют время процессора. Если поток выполняет вызов в машинном коде, время, затрачиваемое потока в машинном коде включается в число для домена приложения, где был выполнен вызов.  
  
    -   Управляемый интерфейс API: <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> свойство.  
  
    -   API размещения: [ICLRAppDomainResourceMonitor::GetCurrentCpuTime](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md) метод.  
  
    -   События трассировки событий Windows: `ThreadCreated`, `ThreadAppDomainEnter`, и `ThreadTerminated` события. Сведения о поставщиках и ключевые слова, в разделе «Ресурса события мониторинга домена приложения» в [события трассировки событий Windows среды CLR](../../../docs/framework/performance/clr-etw-events.md).  
  
-   **Общее число управляемых выделений, сделанных домен приложения во время существования, в байтах**: общие выделения не всегда отражают использование памяти доменом приложения, так как распределенные объекты могут быть короткоживущими. Тем не менее если приложение выделяет и освобождает большое количество объектов, стоимость распределений может быть значительно.  
  
    -   Управляемый интерфейс API: <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> свойство.  
  
    -   API размещения: [ICLRAppDomainResourceMonitor::GetCurrentAllocated](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md) метод.  
  
    -   События трассировки событий Windows: `AppDomainMemAllocated` событий, `Allocated` поля.  
  
-   **Управляемая память, в байтах, на который ссылается домен приложения и, оставшихся после последней полной блокирующей коллекции**: это число является точным только после полной блокирующей сборки. (Это отличается от параллельных сборок мусора, которые в фоновом режиме и не блокирует работу приложения.) Например <xref:System.GC.Collect?displayProperty=nameWithType> перегрузка метода вызывает полной блокирующей сборки.  
  
    -   Управляемый интерфейс API: <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> свойство.  
  
    -   API размещения: [ICLRAppDomainResourceMonitor::GetCurrentSurvived](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md) метода `pAppDomainBytesSurvived` параметра.  
  
    -   События трассировки событий Windows: `AppDomainMemSurvived` событий, `Survived` поля.  
  
-   **Общее число управляемой памяти, в байтах, на который ссылается процесс и, оставшихся после последней полной блокирующей коллекции**: с этим числом можно сравнить память, сохранившуюся для отдельных доменов приложений.  
  
    -   Управляемый интерфейс API: <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType> свойство.  
  
    -   API размещения: [ICLRAppDomainResourceMonitor::GetCurrentSurvived](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md) метода `pTotalBytesSurvived` параметра.  
  
    -   События трассировки событий Windows: `AppDomainMemSurvived` событий, `ProcessSurvived` поля.  
  
### <a name="determining-when-a-full-blocking-collection-occurs"></a>Определение момента выполнения полной, блокирующей сборки мусора  
 Чтобы определить, когда точны счетчиков памяти, необходимо знать, когда просто произошла полную блокирующую сборку. Для этого метод зависит от API-интерфейса можно использовать для получения статистики ARM.  
  
#### <a name="managed-api"></a>Управляемый API-Интерфейс  
 Если вы используете свойства <xref:System.AppDomain> , можно использовать <xref:System.GC.RegisterForFullGCNotification%2A?displayProperty=nameWithType> метода для регистрации для получения уведомлений о полная сборка мусора. Пороговое значение, используемого не имеет значения, так как ожидается завершение сборки мусора, а не подход коллекции. Затем можно вызвать <xref:System.GC.WaitForFullGCComplete%2A?displayProperty=nameWithType> метод, который блокируется до завершения полной сборки мусора. Можно создать поток, который вызывает метод в цикле и выполняющий весь необходимый анализ всякий раз, когда метод возвращает.  
  
 Кроме того, можно вызвать метод <xref:System.GC.CollectionCount%2A?displayProperty=nameWithType> метод периодически для просмотра, если увеличилось количество поколения 2. В зависимости от частоты опроса этот метод может не отображают точное вхождения полной сборки мусора.  
  
#### <a name="hosting-api"></a>API размещения  
 При использовании неуправляемого API размещения ведущее приложение должно передать среде CLR реализация [IHostGCManager](../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md) интерфейса. Среда CLR вызывает [IHostGCManager::SuspensionEnding](../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md) метод, когда он возобновляет выполнение потоков, которые были приостановлены, пока идет коллекцию. Среда CLR передает поколение выполненной сборки мусора как параметр метода, поэтому узла можно определить, была ли коллекция полной или частичной. Реализация [IHostGCManager::SuspensionEnding](../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md) метода можно запросить память, сохранившуюся, чтобы гарантировать получение счетчиков сразу же после их обновления.  
  
## <a name="see-also"></a>См. также  
 <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
 [ICLRAppDomainResourceMonitor-интерфейс](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [\<appDomainResourceMonitoring>](../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)  
 [События трассировки событий Windows в среде CLR](../../../docs/framework/performance/clr-etw-events.md)
