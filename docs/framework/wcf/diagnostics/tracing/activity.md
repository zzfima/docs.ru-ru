---
title: Действие
ms.date: 03/30/2017
ms.assetid: 70471705-f55f-4da1-919f-4b580f172665
ms.openlocfilehash: 7f498c1f2222add197f428386076148cccc9ad06
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64656295"
---
# <a name="activity"></a>Действие
В этом разделе описываются трассировки действий в модели трассировки Windows Communication Foundation (WCF). Действия — это блоки обработки, позволяющие пользователю сузить область сбоя. Ошибки, возникающие в одном действии, напрямую связаны между собой. Например, операция заканчивается неудачей в результате сбоя при расшифровывании сообщения. Трассировки операции и расшифровывания сообщения появляются в том же действии и показывают прямую связь между ошибкой расшифровывания и ошибкой запроса.  
  
## <a name="configuring-activity-tracing"></a>Настройка трассировки действий  
 WCF предоставляет предварительно определенные действия для приложений обработки (см. в разделе [список действий](../../../../../docs/framework/wcf/diagnostics/tracing/activity-list.md)). Кроме того, действия можно определить программно для группирования пользовательских трассировок. Дополнительные сведения см. в разделе [создающие трассировки пользовательского кода](../../../../../docs/framework/wcf/diagnostics/tracing/emitting-user-code-traces.md).  
  
 Чтобы создать трассировки действия во время выполнения, используйте `ActivityTracing` для `System.ServiceModel` трассировки источника, или других WCF или пользовательские источники трассировки, как показано в следующем примере кода конфигурации.  
  
```xml  
<source name="System.ServiceModel" switchValue="Verbose,ActivityTracing">  
```  
  
 Сведения об элементе конфигурации и используемых атрибутах см. в статье [Настройка трассировки](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md) раздела.  
  
## <a name="viewing-activities"></a>Просмотр действий  
 Вы можете просматривать действия и свою функциональность в [программа Service Trace Viewer (SvcTraceViewer.exe)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md). Если функция ActivityTracing включена, данное средство сортирует трассировки на основе действий. Также можно просматривать перенаправления трассировок. Перенаправление трассировки показывает, как различные действия связаны между собой. Таким образом, можно увидеть, какие действия приводят к запуску других действий. Например, запрос сообщения привел к запуску процедуры подтверждения для получения маркера безопасного диалога.  
  
### <a name="correlating-activities-in-service-trace-viewer"></a>Корреляция действия в программе Service Trace Viewer  
 В программе Service Trace Viewer предусмотрено два представления действий.  
  
- **Список** представление, где идентификатор действия используется для непосредственной корреляции трассировок из различных процессов. Трассировки из различных процессов (например, клиента и службы) с одним и тем же идентификатором действия группируются в одном действии. Поэтому ошибка службы и вызванная ей ошибка на клиенте будут отображены в программе в одном представлении действий.  
  
- **Граф** представление, где действия группируются в процессы. В этом представлении трассировки клиента и службы с одинаковым идентификатором действия находятся в различных действиях. Для корреляции действий с одинаковым идентификатором в различных процессах программа отображает потоки сообщений в связанных действиях.  
  
 Дополнительные сведения и ее графическое представление средства просмотра трассировки службы, см. в разделе [программа Service Trace Viewer (SvcTraceViewer.exe)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) и [с помощью программы Service Trace Viewer для просмотра корреляцию трассировок и Устранение неполадок](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).  
  
## <a name="defining-the-scope-of-an-activity"></a>Определение области действия  
 Действие определяется во время проектирования и обозначает логический блок обработки. Созданные трассировки с одинаковым идентификатором действия являются связанными напрямую; они представляют собой часть одного действия. Поскольку действие может пересекать границы конечной точки (например, запрос), для действия определяются две области.  
  
- Область `Global` для каждого приложения. В этой области действие определяется 128-разрядным глобальным уникальным идентификатором действия (gAId). Идентификатор gAid распространяется на конечные точки.  
  
- Область `Local` для каждой конечной точки. В этой области действие определяется своим идентификатором gAId, а также именем источника трассировки, создающего трассировки действий, и идентификатором процесса. Эти три значения составляют идентификатор локального действия, lAId. Идентификатор lAId используется для определения (локальных) границ действия.  
  
## <a name="trace-schema"></a>Схема трассировки  
 Трассировки можно создавать с использованием любой схемы и для различных платформ Майкрософт. «e2e (от «End to End») представляет собой часто используемые схему. Эта схема включает 128-разрядный идентификатор (gAId), имя источника трассировки и идентификатор процесса. В управляемом коде <xref:System.Diagnostics.XmlWriterTraceListener> создает трассировки по схеме E2E.  
  
 Разработчики могут задавать идентификатор действия, выдаваемый вместе с трассировкой, путем присвоения свойству <xref:System.Diagnostics.CorrelationManager.ActivityId%2A> значения идентификатора GUID в локальной памяти потока. В следующем примере это показано.  
  
```csharp
// set the current Activity ID to a new GUID.  
CorrelationManager.ActivityId = Guid.NewGuid();  
```
  
 Задание идентификатора gAId в локальной памяти потока будет засвидетельствовано при создании трассировок с помощью источника трассировки, как показано в следующем примере.  
  
```csharp
TraceSource traceSource = new TraceSource("myTraceSource");  
traceSource.TraceEvent(TraceEventType.Warning, eventId, "Information");  
```  
  
 В выданной трассировке будут содержаться идентификатор gAId, находящийся в данный момент в локальной памяти потока, имя источника трассировки, переданное в качестве параметра конструктору источника трассировки, и идентификатор текущего процесса.  
  
## <a name="activity-lifetime"></a>Время существования действия  
 Строго говоря, свидетельство действия начинается при первом использовании идентификатора действия в созданной трассировке и заканчивается при последнем использовании идентификатора действия в созданной трассировке. Предварительно определенный набор типов трассировок, включающий "Запуск" и "Остановку", предоставляется пространством имен <xref:System.Diagnostics> для явной пометки границ времени существования действия.  
  
- Запуск: Обозначает начало действия. Трассировка «Start» предоставляет запись о начале нового этапа обработки. В ней содержится новый идентификатор действия для заданного источника трассировки в заданном процессе, кроме случая распространения идентификатора действия на конечные точки, в котором наблюдается одна трассировка «Запуск» для каждой конечной точки. Примером запуска нового действия является создание нового потока для обработки или нового открытого метода.  
  
- Остановка: Указывает конец действия. Трассировку «Остановка» предоставляет запись о завершении существующего этапа обработки. В ней содержится существующий идентификатор действия для заданного источника трассировки в заданном процессе, кроме случая распространения идентификатора действия на конечные точки, в котором наблюдается одна трассировка «Остановка» для каждой конечной точки.  Остановки действия является примеры завершение потока обработки или выход из метода, начало которого было обозначено с трассировкой «Start».  
  
- Приостановка. Обозначает приостановку обработки действия. Трассировка «Приостановка» содержится идентификатор существующего действия которого ожидается возобновить позже. Между событиями «Приостановка» и «Возобновление» никакие трассировки из источника трассировки не создаются. Примером является приостановка действия при вызове внешней функции библиотеки или при ожидании ресурса, такого как порт завершения ввода-вывода.  
  
- Возобновление. Обозначает продолжение обработки действия. В трассировке «Возобновление» содержится идентификатор существующего действия, последней трассировкой из текущего источника трассировки была трассировка «Приостановка». Примером является возврат после вызова внешней функции библиотеки или получение сигнала возобновления обработки от ресурса, такого как порт завершения ввода-вывода.  
  
- Для передачи: Так как некоторые действия вызываются другими или относятся к ним, действия могут быть связаны с другими действиями с помощью трассировок «Перенаправление». Трассировка перенаправления записывает непосредственное отношение одного действия к другому.  
  
 Трассировки Start и Stop не являются критически важными для корреляции. Однако они могут способствовать повышению производительности, профилированию и проверке области действия.  
  
 Используя эти типы, средства могут оптимизировать журналы трассировки для поиска непосредственно связанных событий одного действия или событий в связанных действиях, если средство прослеживает трассировки перенаправления. Например, средства прекращают анализ журналов для заданного действия при обнаружении трассировки Start и Stop.  
  
 Эти типы трассировки можно также использовать для профилирования. Ресурсы, которые использовались в течение интервала, определенного маркерами запуска и остановки, представляют инклюзивное время действия, включающее содержащиеся логические действия. После вычитания интервалов времени между трассировками Suspend и Resume получается фактическое время действия.  
  
 Трассировку «Остановка» особенно полезно использовать для проверки области реализованных действий. Если некоторые трассировки обработки появляются после трассировки Stop, а не в рамках заданного действия, это может указывать на дефект в коде.  
  
## <a name="guidelines-for-using-activity-tracing"></a>Рекомендации по использованию трассировки действий  
 Ниже приведены рекомендации по использованию трассировок ActivityTracing (Start, Stop, Suspend, Resume и Transfer).  
  
- Трассировка является направленным циклическим графом, а не деревом. Можно вернуть управление действию, которое породило заданное действие.  
  
- Действие обозначает границу обработки, что может быть существенным для администратора системы или для возможности поддержки.  
  
- Связывает каждого метода WCF, как на клиенте и сервере, с началом нового действия, а затем (после выполнения работы) завершением нового действия и возврат к внешнему действию.  
  
- Долго выполняющиеся (текущие) действия, такие как прослушивание соединений или ожидание сообщений, представляются соответствующими маркерами запуска и остановки.  
  
- Действия, инициируемые получением или обработкой сообщения, представляются границами трассировки.  
  
- Действия представляют действия, а не обязательно объекты. Действие должно интерпретироваться как «это происходило при. . . (была создана существенная трассировка)".  
  
## <a name="see-also"></a>См. также

- [Настройка трассировки](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)
- [Использование программы Service Trace Viewer для просмотра скоррелированных трассировок и устранения неполадок](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [Сценарии сквозной трассировки](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)
- [Средство просмотра трассировки служб (SvcTraceViewer.exe)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
- [Создание трассировки пользовательского кода](../../../../../docs/framework/wcf/diagnostics/tracing/emitting-user-code-traces.md)
