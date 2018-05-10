---
title: Администрирование и диагностика
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, diagnostics
- Windows Communication Foundation, administration
- diagnostics [WCF]
- WCF, diagnostics
- administration [WCF]
- WCF, administration
ms.assetid: 34c81c08-0e0f-4fbc-9ae8-91948640ee43
ms.openlocfilehash: c69d5681b186fdfae168ceea8b35f5786eaf02c9
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="administration-and-diagnostics"></a>Администрирование и диагностика
Windows Communication Foundation (WCF) предоставляет широкий набор функций, которые можно отслеживать разные этапы жизненного цикла приложения. Например, можно использовать конфигурацию для настройки служб и клиентов при развертывании. WCF содержит большой набор счетчиков производительности для оценки производительности приложения. WCF также предоставляет данные проверки службы во время выполнения посредством поставщика WCF инструментария управления Windows (WMI). Когда в приложении происходит ошибка или оно начинает функционировать неверно, журнал событий позволяет понять, серьезны ли причины нарушения. Также можно использовать журнал сообщений и функцию трассировки сообщений для того, чтобы понять, какие события происходят в приложении на всех этапах его работы. Эти возможности помогают разработчикам и ИТ-специалистов, для устранения неполадок приложения WCF, когда он работает.  
  
> [!NOTE]
>  Если вы получили ошибок без определенные сведения о данных, следует включить `includeExceptionDetailInFaults` атрибут [ \<serviceDebug >](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) элемента конфигурации. Это указывает, что WCF для отправки клиентам, сведения об исключениях, что позволяет обнаружить многие распространенные проблемы, не требуя более сложным методам диагностики. Дополнительные сведения см. в разделе [отправка и получение ошибки](../../../../docs/framework/wcf/sending-and-receiving-faults.md).  
  
## <a name="diagnostics-features-provided-by-wcf"></a>Возможности диагностики, предоставляемые WCF  
 WCF предоставляет следующие функции диагностики:  
  
-   Сквозная трассировка предоставляет данные инструментирования для устранения неполадок в работе приложения без использования отладчика. WCF выводит трассировки основных этапов процесса, а также сообщения об ошибках. Они могут включать открытие фабрики каналов или отправку и получение сообщений узлом службы. Трассировку можно включить для запущенного приложения, чтобы отслеживать ход его выполнения. Дополнительные сведения см. в разделе [трассировки](../../../../docs/framework/wcf/diagnostics/tracing/index.md) раздела. Чтобы понять, как использовать трассировку для отладки приложения, в разделе [с помощью трассировки для устранения неполадок приложения](../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md) раздела.  
  
-   Ведение журнала сообщений позволяет увидеть, как выглядят сообщения до и после передачи. Дополнительные сведения см. в разделе [ведение журнала сообщений](../../../../docs/framework/wcf/diagnostics/message-logging.md) раздела.  
  
-   Трассировка событий записывает события в журнал событий для анализа серьезных проблем. Вы можете затем использовать средство «Просмотр событий» для проверки любых нарушений. Дополнительные сведения см. в разделе [ведение журнала событий](../../../../docs/framework/wcf/diagnostics/event-logging/index.md) раздела.  
  
-   С помощью счетчиков производительности, предоставляемых системным монитором, можно отслеживать работу приложения и состояние системы. Дополнительные сведения см. в разделе [счетчики производительности](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md) раздела.  
  
-   Пространство имен <xref:System.ServiceModel.Configuration> позволяет загружать файлы конфигурации и настраивать конечные точки службы или клиента. Можно воспользоваться объектной моделью, чтобы создать скрипты изменений для нескольких приложений, если необходимо выполнить развертывание обновлений на нескольких компьютерах. Кроме того, можно использовать [средство редактирования конфигурации (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) для изменения параметров конфигурации, с помощью графического интерфейса мастера. Дополнительные сведения см. в разделе [Настройка приложения](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md) раздела.  
  
-   WMI позволяет получать информацию о прослушивающих компьютер службах и используемых привязках. Дополнительные сведения см. в разделе [с помощью Windows Management Instrumentation для диагностики](../../../../docs/framework/wcf/diagnostics/wmi/index.md) раздела.  
  
 WCF также предоставляет несколько средств графического пользовательского интерфейса и программы командной строки, чтобы упростить создание, развертывание и управление приложениями WCF. Дополнительные сведения см. в разделе [средства Windows Communication Foundation](../../../../docs/framework/wcf/tools.md). Например, можно использовать [средство редактирования конфигурации (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) для создания и изменения параметров конфигурации WCF, с помощью мастера, вместо непосредственного редактирования XML-кода. Можно также использовать [программы Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) для просмотра, группировать и фильтровать сообщения трассировки, чтобы диагностики, устранения и проверки неисправностей служб WCF.  
  
## <a name="see-also"></a>См. также  
 [Настройка приложения](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md)  
 [Развертывание служб](../../../../docs/framework/wcf/diagnostics/deploying-services.md)  
 [Справочник по исключениям](../../../../docs/framework/wcf/diagnostics/exceptions-reference/index.md)  
 [Ведение журнала событий](../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [Ведение журналов сообщений](../../../../docs/framework/wcf/diagnostics/message-logging.md)  
 [Редактор конфигурации (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)  
 [Средство просмотра трассировки служб (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)  
 [Средство регистрации ServiceModel](../../../../docs/framework/wcf/diagnostics/servicemodel-registration-tool.md)  
 [Трассировка](../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Использование инструментария управления Windows для диагностики](../../../../docs/framework/wcf/diagnostics/wmi/index.md)  
 [Счетчики производительности](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)  
 [Средства Windows Communication Foundation](../../../../docs/framework/wcf/tools.md)
