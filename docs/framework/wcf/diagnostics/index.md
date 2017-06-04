---
title: "Администрирование и диагностика | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "администрирование [WCF]"
  - "диагностика [WCF]"
  - "WCF, администрирование"
  - "WCF, диагностика"
  - "Windows Communication Foundation, администрирование"
  - "Windows Communication Foundation, диагностика"
ms.assetid: 34c81c08-0e0f-4fbc-9ae8-91948640ee43
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# Администрирование и диагностика
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] предоставляет широкий набор функций, благодаря которому можно отслеживать разные этапы времени существования приложения.Например, вы можете использовать конфигурацию для настройки служб и клиентов при развертывании.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] содержит большой набор счетчиков производительности, с помощью которых можно измерять производительность приложения.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] также предоставляет данные проверки службы во время ее выполнения поставщиком [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Инструментария управления Windows \(WMI\).Когда в приложении происходит ошибка или оно начинает функционировать неверно, журнал событий позволяет понять, серьезны ли причины нарушения.Также можно использовать журнал сообщений и функцию трассировки сообщений для того, чтобы понять, какие события происходят в приложении на всех этапах его работы.Эти функции помогают разработчикам и ИТ\-специалистам устранять неполадки в приложении [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в случае его неверного функционирования.  
  
> [!NOTE]
>  Если вы получаете сообщения об ошибках, но не получаете подробные сведения о причинах их возникновения, необходимо включить атрибут `includeExceptionDetailInFaults` элемента конфигурации [\<serviceDebug\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md).Тем самым [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] дается указание отправлять клиентам сведения об исключениях, благодаря чему можно обнаружить многие распространенные проблемы, не прибегая к более сложным методам диагностики.Дополнительные сведения см. в разделе [Сбои при отправке и получении](../../../../docs/framework/wcf/sending-and-receiving-faults.md).  
  
## Функции диагностики, предоставляемые WCF  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] обеспечивает следующие функции диагностики:  
  
-   Сквозная трассировка предоставляет данные инструментирования для устранения неполадок в работе приложения без использования отладчика.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] выводит трассировки основных этапов процесса, а также сообщения об ошибках.Они могут включать открытие фабрики каналов или отправку и получение сообщений узлом службы.Трассировку можно включить для запущенного приложения, чтобы отслеживать ход его выполнения.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] см. раздел [Трассировка](../../../../docs/framework/wcf/diagnostics/tracing/index.md).Для получения информации о том, как можно использовать трассировку для отладки приложения, см. раздел [Использование трассировки для устранения неполадок приложения](../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).  
  
-   Ведение журнала сообщений позволяет вам увидеть, как выглядят сообщения до и после передачи.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] см. раздел [Ведение журнала сообщений](../../../../docs/framework/wcf/diagnostics/message-logging.md).  
  
-   Трассировка событий записывает события в журнал событий для анализа серьезных проблем.Вы можете затем использовать средство «Просмотр событий» для проверки любых нарушений.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] см. раздел [Ведение журнала событий](../../../../docs/framework/wcf/diagnostics/event-logging/index.md).  
  
-   Счетчики производительности, предоставляемые Системным монитором, позволяют отслеживать работу вашего приложения и работоспособность системы.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] см. раздел [Счетчики производительности](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md).  
  
-   Пространство имен <xref:System.ServiceModel.Configuration> позволяет загружать файлы конфигурации и настраивать конечные точки службы или клиента.Можно воспользоваться объектной моделью, чтобы создать скрипты изменений для нескольких приложений, если необходимо выполнить развертывание обновлений на нескольких компьютерах.Вы также можете использовать [Средство редактирования конфигурации \(SvcConfigEditor.exe\)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) для редактирования параметров конфигурации с помощью мастера Графического интерфейса пользователя.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] см. раздел [Настройка приложения](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md).  
  
-   WMI позволяет получать информацию о службах, прослушивающихся на компьютере, и используемых привязках.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] см. раздел [Использование Windows Management Instrumentation для диагностики](../../../../docs/framework/wcf/diagnostics/wmi/index.md).  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] также предоставляет несколько инструментов графического интерфейса пользователя \(GUI\) и командной строки, благодаря которым упрощается создание и развертывание приложений [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], а также управление ими.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Средства Windows Communication Foundation](../../../../docs/framework/wcf/tools.md).Например, можно использовать [Средство редактирования конфигурации \(SvcConfigEditor.exe\)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) для создания и изменения параметров конфигурации [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с помощью мастера, вместо того чтобы редактировать непосредственно XML.Также можно воспользоваться [Программа Service Trace Viewer \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) для просмотра, группировки и фильтрации сообщений трассировки в целях диагностики, устранения и проверки неисправностей служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## См. также  
 [Настройка приложения](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md)   
 [Развертывание служб](../../../../docs/framework/wcf/diagnostics/deploying-services.md)   
 [Справочник по исключениям](../../../../docs/framework/wcf/diagnostics/exceptions-reference/index.md)   
 [Ведение журнала событий](../../../../docs/framework/wcf/diagnostics/event-logging/index.md)   
 [Ведение журнала сообщений](../../../../docs/framework/wcf/diagnostics/message-logging.md)   
 [Средство редактирования конфигурации \(SvcConfigEditor.exe\)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)   
 [Программа Service Trace Viewer \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)   
 [Средство регистрации ServiceModel](../../../../docs/framework/wcf/diagnostics/servicemodel-registration-tool.md)   
 [Трассировка](../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Использование Windows Management Instrumentation для диагностики](../../../../docs/framework/wcf/diagnostics/wmi/index.md)   
 [Счетчики производительности](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)   
 [Средства Windows Communication Foundation](../../../../docs/framework/wcf/tools.md)