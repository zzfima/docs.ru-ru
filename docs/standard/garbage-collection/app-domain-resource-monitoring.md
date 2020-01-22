---
title: Отслеживание ресурсов домена приложения
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- monitoring managed memory use by application domain
- application domains, memory use
- memory use, monitoring
- application domains, resource monitoring
ms.assetid: 318bedf8-7f35-4f00-b34a-2b7b8e3fa315
ms.openlocfilehash: 54e300bef1818fd08f27d7920eec68ee1f2c45bb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141379"
---
# <a name="application-domain-resource-monitoring"></a>Отслеживание ресурсов домена приложения

Функция наблюдения за ресурсами доменов приложений (ARM) позволяет узлам отслеживать загрузку ЦП и использование памяти доменом приложения. Это полезно для некоторых узлов, таких как ASP.NET, которые используют несколько доменов приложений в длительных процессах. Узел может выгрузить домен приложения, если его работа понижает производительность процесса в целом. Но для нужно определить проблемное приложение. ARM предоставляет сведения, которые помогут решить эту задачу.

Например, на сервере ASP.NET службы размещения может выполняться несколько приложений. Если одно из приложений процесса потребляет слишком много памяти или процессорного времени, служба размещения с помощью ARM может определить проблемный домен приложения.

Функция ARM достаточно нетребовательна к ресурсам, что позволяет применять ее в работающих приложениях. Нужную информацию можно получить с помощью трассировки событий для Windows (ETW), а также управляемых или собственных интерфейсов API.

## <a name="enabling-resource-monitoring"></a>Включение наблюдения за ресурсами

ARM можно включить четырьмя способами: в файле конфигурации при запуске общеязыковой среды выполнения (CLR), через неуправляемый интерфейс API размещения, в управляемом коде или ожидая передачи событий трассировки событий Windows ARM.

Сразу после включения ARM начинает сбор данных всех доменов приложений в процессе. Если домен приложения создан до включения ARM, данные накапливаются лишь с момента включения ARM, но не с момента создания домена приложения. После включения ARM отключить нельзя.

- Вы можете включить ARM при запуске среды CLR. Для этого добавьте элемент [\<appDomainResourceMonitoring>](../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md) в файл конфигурации и присвойте атрибуту `enabled` значение `true`. Значение `false` (по умолчанию) просто означает, что ARM не включается автоматически при запуске. ARM можно включить позже с помощью любого другого механизма активации.

- Узел может включить ARM, подав запрос на интерфейс размещения [ICLRAppDomainResourceMonitor](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md). ARM включается после успешного получения этого интерфейса.

- Чтобы включить ARM из управляемого кода, задайте для статического свойства <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> (`Shared` в Visual Basic) значение `true`. ARM включается сразу после изменения этого свойства.

- Чтобы включить ARM после запуска, используйте ожидание передачи данных от функции трассировки событий Windows. ARM включается и начинает создавать события для всех доменов приложений при активации общего поставщика `Microsoft-Windows-DotNETRuntime` с помощью ключевого слова `AppDomainResourceManagementKeyword`. Чтобы связать данные с потоками и доменами приложений, также нужно включить поставщик `Microsoft-Windows-DotNETRuntimeRundown` с помощью ключевого слова `ThreadingKeyword`.

## <a name="using-arm"></a>Использование ARM

ARM передает данные общего процессорного времени, используемого доменом приложения, а также три параметра использования памяти.

- **Общее процессорное время для домена приложения, в секундах**. Результат вычисляется путем сложения значений времени для всех потоков операционной системы, выполнявшихся в домене приложения за весь период его существования. Заблокированные потоки и потоки в спящем режиме не используют процессорное время. Если поток вызывает машинный код, время нового потока в машинном коде включается в статистику по домену приложения, из которого он был вызван.

  - Управляемый интерфейс API: свойство <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>.

  - Интерфейс API размещения. Метод [ICLRAppDomainResourceMonitor::GetCurrentCpuTime](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md).

  - События трассировки событий Windows: события `ThreadCreated`, `ThreadAppDomainEnter` и `ThreadTerminated`. Сведения о поставщиках и ключевые слова вы найдете в разделе о событиях ресурсов для доменов приложения в статье [События трассировки событий Windows в среде CLR](../../../docs/framework/performance/clr-etw-events.md).

- **Общий объем выделенной управляемой памяти для домена приложения за все время его существования (в байтах)** . Общий объем выделенной памяти не всегда правильно отражает использование памяти доменом приложения, так как объекты могут выделяться на короткий промежуток времени. Но накладные расходы могут оказаться существенными, если приложение часто выделяет и освобождает большое количество объектов.

  - Управляемый интерфейс API: свойство <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>.

  - Интерфейс API размещения. Метод [ICLRAppDomainResourceMonitor::GetCurrentAllocated](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md).

  - События трассировки событий Windows: событие `AppDomainMemAllocated`, поле `Allocated`.

- **Управляемая память (в байтах), которая используется доменом приложения и осталась выделенной после последней полной блокирующей сборки мусора**. Этот параметр имеет смысл, только если выполнялась полная блокирующая сборка. (в отличие от параллельных операций сборки, которые выполняются в фоновом режиме и не блокируют работу приложения). Например, перегрузка метода <xref:System.GC.Collect?displayProperty=nameWithType> вызывает полную блокирующую сборку мусора.

  - Управляемый интерфейс API: свойство <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>.

  - Интерфейс API размещения. Метод [ICLRAppDomainResourceMonitor::GetCurrentSurvived](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md), параметр `pAppDomainBytesSurvived`.

  - События трассировки событий Windows: событие `AppDomainMemSurvived`, поле `Survived`.

- **Общий объем управляемой памяти (в байтах), которая используется процессом и осталась выделенной после последней полной блокирующей сборки мусора**. Это значение можно сравнить с объемами памяти, которая осталась выделенной для отдельных доменов приложений.

  - Управляемый интерфейс API: свойство <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>.

  - Интерфейс API размещения. Метод [ICLRAppDomainResourceMonitor::GetCurrentSurvived](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md), параметр `pTotalBytesSurvived`.

  - События трассировки событий Windows: событие `AppDomainMemSurvived`, поле `ProcessSurvived`.

### <a name="determining-when-a-full-blocking-collection-occurs"></a>Как определить время полной блокирующей сборки мусора

Чтобы определить точность сведений об оставшемся объеме памяти, нужно узнать время последней полной блокирующей сборки. Метод определения времени зависит от того, какой API-интерфейс вы используете для изучения статистики ARM.

#### <a name="managed-api"></a>Управляемый API

Если вы используете свойства класса <xref:System.AppDomain>, метод <xref:System.GC.RegisterForFullGCNotification%2A?displayProperty=nameWithType> позволяет зарегистрироваться для получения уведомлений о полных сборках. Указываемое здесь пороговое значение не играет роли, так как вас интересует только завершение сборки, а не ее приближение. После этого вызовите метод <xref:System.GC.WaitForFullGCComplete%2A?displayProperty=nameWithType>, который блокируется до завершения полной сборки. Вы можете создать отдельный поток, который вызывает этот метод в цикле и проводит анализ данных при каждом завершении метода.

Кроме того, вы можете периодически вызвать метод <xref:System.GC.CollectionCount%2A?displayProperty=nameWithType>, чтобы отслеживать увеличение количества сборок для поколения 2. В зависимости от частоты опроса такой подход не всегда будет давать точные сведения о времени выполнения полной сборки мусора.

#### <a name="hosting-api"></a>Интерфейс API размещения

Если вы используете API размещения, а не управляемый API, узел должен передать в среду CLR реализацию интерфейса [IHostGCManager](../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md). Среда CLR вызывает метод [IHostGCManager::SuspensionEnding](../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md) из этого интерфейса, когда возобновляет выполнение потоков, приостановленных на время сбора мусора. Среда CLR передает в параметре этого метода номер поколения выполненной сборки. Это позволяет узлу определить тип сборки (полная или частичная). Вы можете поместить запросы данных оставшейся памяти в реализацию метода [IHostGCManager::SuspensionEnding](../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md), чтобы получать их сразу же по мере обновления.

## <a name="see-also"></a>См. также

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [Интерфейс ICLRAppDomainResourceMonitor](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [\<appDomainResourceMonitoring>](../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)
- [События трассировки событий Windows в среде CLR](../../../docs/framework/performance/clr-etw-events.md)
