---
title: Администрирование и диагностика
ms.date: 03/30/2017
helpviewer_keywords:
  - 'Windows Communication Foundation, diagnostics'
  - 'Windows Communication Foundation, administration'
  - 'diagnostics [WCF]'
  - 'WCF, diagnostics'
  - 'administration [WCF]'
  - 'WCF, administration'
ms.assetid: 34c81c08-0e0f-4fbc-9ae8-91948640ee43
---
# <a name="administration-and-diagnostics"></a>Администрирование и диагностика
Windows Communication Foundation (WCF) предоставляет широкий набор функций, которые помогут вам отслеживать разные этапы жизненного цикла приложения. Например, можно использовать конфигурацию для настройки служб и клиентов при развертывании. WCF включает в себя большой набор счетчиков производительности с помощью которых можно измерять производительность приложения. WCF также предоставляет данные проверки службы во время выполнения через поставщика WCF инструментария управления Windows (WMI). Когда в приложении происходит ошибка или оно начинает функционировать неверно, журнал событий позволяет понять, серьезны ли причины нарушения. Также можно использовать журнал сообщений и функцию трассировки сообщений для того, чтобы понять, какие события происходят в приложении на всех этапах его работы. Эти функции помогают разработчикам и ИТ-специалистам для устранения неполадок приложения WCF, когда он работает правильно.  
  
> [!NOTE]
>  При возникновении ошибок не получаете подробные сведения о, следует включить `includeExceptionDetailInFaults` атрибут [ \<serviceDebug >](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) элемента конфигурации. Это предписывает WCF для отправки клиентам, сведения об исключениях, что дает возможность обнаружить многие распространенные проблемы, не требуя более сложным методам диагностики. Дополнительные сведения см. в разделе [Sending and Receiving Faults](../../../../docs/framework/wcf/sending-and-receiving-faults.md).  
  
## <a name="diagnostics-features-provided-by-wcf"></a>Возможности диагностики, предоставляемые WCF  
 WCF предоставляет следующие функции диагностики:  
  
-   Сквозная трассировка предоставляет данные инструментирования для устранения неполадок в работе приложения без использования отладчика. WCF выводит трассировки основных этапов процесса, а также сообщения об ошибках. Они могут включать открытие фабрики каналов или отправку и получение сообщений узлом службы. Трассировку можно включить для запущенного приложения, чтобы отслеживать ход его выполнения. Дополнительные сведения см. в разделе [трассировки](../../../../docs/framework/wcf/diagnostics/tracing/index.md) раздела. Чтобы понять, как использовать трассировку для отладки приложения, см. в разделе [с помощью трассировки для устранения неполадок приложения](../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md) раздела.  
  
-   Ведение журнала сообщений позволяет увидеть, как выглядят сообщения до и после передачи. Дополнительные сведения см. в разделе [ведение журнала сообщений](../../../../docs/framework/wcf/diagnostics/message-logging.md) раздела.  
  
-   Трассировка событий записывает события в журнал событий для анализа серьезных проблем. Вы можете затем использовать средство «Просмотр событий» для проверки любых нарушений. Дополнительные сведения см. в разделе [ведение журнала событий](../../../../docs/framework/wcf/diagnostics/event-logging/index.md) раздела.  
  
-   С помощью счетчиков производительности, предоставляемых системным монитором, можно отслеживать работу приложения и состояние системы. Дополнительные сведения см. в разделе [счетчики производительности](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md) раздела.  
  
-   Пространство имен <xref:System.ServiceModel.Configuration> позволяет загружать файлы конфигурации и настраивать конечные точки службы или клиента. Можно воспользоваться объектной моделью, чтобы создать скрипты изменений для нескольких приложений, если необходимо выполнить развертывание обновлений на нескольких компьютерах. Кроме того, можно использовать [средство редактирования конфигурации (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) для изменения параметров конфигурации, с помощью мастера графического интерфейса пользователя. Дополнительные сведения см. в разделе [Настройка приложения](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md) раздела.  
  
-   WMI позволяет получать информацию о прослушивающих компьютер службах и используемых привязках. Дополнительные сведения см. в разделе [с помощью Windows Management Instrumentation для диагностики](../../../../docs/framework/wcf/diagnostics/wmi/index.md) раздела.  
  
 WCF также предоставляет несколько графического пользовательского интерфейса и средства командной строки для упрощения создания, развертывания и управления приложениями WCF. Дополнительные сведения см. в разделе [средства Windows Communication Foundation](../../../../docs/framework/wcf/tools.md). Например, можно использовать [средство редактирования конфигурации (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) создавать и изменять параметры конфигурации WCF, с помощью мастера, вместо непосредственного редактирования XML. Можно также использовать [программа Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) для просмотра, группировки и фильтрации сообщений трассировки для диагностики, устранения и проверки неисправностей служб WCF.  
  
## <a name="see-also"></a>См. также
- [Настройка приложения](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md)
- [Развертывание служб](../../../../docs/framework/wcf/diagnostics/deploying-services.md)
- [Справочник по исключениям](../../../../docs/framework/wcf/diagnostics/exceptions-reference/index.md)
- [Ведение журнала событий](../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [Ведение журналов сообщений](../../../../docs/framework/wcf/diagnostics/message-logging.md)
- [Редактор конфигурации (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)
- [Средство просмотра трассировки служб (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
- [Средство регистрации ServiceModel](../../../../docs/framework/wcf/diagnostics/servicemodel-registration-tool.md)
- [Трассировка](../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Использование инструментария управления Windows для диагностики](../../../../docs/framework/wcf/diagnostics/wmi/index.md)
- [Счетчики производительности](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
- [Средства Windows Communication Foundation](../../../../docs/framework/wcf/tools.md)
