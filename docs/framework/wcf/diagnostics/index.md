---
title: "Администрирование и диагностика"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, diagnostics
- Windows Communication Foundation, administration
- diagnostics [WCF]
- WCF, diagnostics
- administration [WCF]
- WCF, administration
ms.assetid: 34c81c08-0e0f-4fbc-9ae8-91948640ee43
caps.latest.revision: "19"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2f103570cf7d94a9ac6256f3db991c44767fa7c4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="administration-and-diagnostics"></a>Администрирование и диагностика
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] предоставляет широкий набор функций, благодаря которому можно отслеживать разные этапы времени существования приложения. Например, можно использовать конфигурацию для настройки служб и клиентов при развертывании. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] содержит большой набор счетчиков производительности, с помощью которых можно измерять производительность приложения. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] также предоставляет данные проверки службы в среде выполнения с помощью поставщика инструментария управления Windows (WMI) [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Когда в приложении происходит ошибка или оно начинает функционировать неверно, журнал событий позволяет понять, серьезны ли причины нарушения. Также можно использовать журнал сообщений и функцию трассировки сообщений для того, чтобы понять, какие события происходят в приложении на всех этапах его работы. Эти функции помогают разработчикам и ИТ-специалистам устранять неполадки в приложении [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в случае его неверного функционирования.  
  
> [!NOTE]
>  Если вы получили ошибок без определенные сведения о данных, следует включить `includeExceptionDetailInFaults` атрибут [ \<serviceDebug >](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) элемента конфигурации. Тем самым [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] дается указание отправлять клиентам сведения об исключениях, благодаря чему можно обнаружить многие распространенные проблемы, не прибегая к более сложным методам диагностики. Дополнительные сведения см. в разделе [отправка и получение ошибки](../../../../docs/framework/wcf/sending-and-receiving-faults.md).  
  
## <a name="diagnostics-features-provided-by-wcf"></a>Возможности диагностики, предоставляемые WCF  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] обеспечивает следующие функции диагностики:  
  
-   Сквозная трассировка предоставляет данные инструментирования для устранения неполадок в работе приложения без использования отладчика. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] выводит трассировки основных этапов процесса, а также сообщения об ошибках. Они могут включать открытие фабрики каналов или отправку и получение сообщений узлом службы. Трассировку можно включить для запущенного приложения, чтобы отслеживать ход его выполнения. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][трассировки](../../../../docs/framework/wcf/diagnostics/tracing/index.md) раздела. Чтобы понять, как использовать трассировку для отладки приложения, в разделе [с помощью трассировки для устранения неполадок приложения](../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md) раздела.  
  
-   Ведение журнала сообщений позволяет увидеть, как выглядят сообщения до и после передачи. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][ведение журнала сообщений](../../../../docs/framework/wcf/diagnostics/message-logging.md) раздела.  
  
-   Трассировка событий записывает события в журнал событий для анализа серьезных проблем. Вы можете затем использовать средство «Просмотр событий» для проверки любых нарушений. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][ведение журнала событий](../../../../docs/framework/wcf/diagnostics/event-logging/index.md) раздела.  
  
-   С помощью счетчиков производительности, предоставляемых системным монитором, можно отслеживать работу приложения и состояние системы. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][счетчики производительности](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md) раздела.  
  
-   Пространство имен <xref:System.ServiceModel.Configuration> позволяет загружать файлы конфигурации и настраивать конечные точки службы или клиента. Можно воспользоваться объектной моделью, чтобы создать скрипты изменений для нескольких приложений, если необходимо выполнить развертывание обновлений на нескольких компьютерах. Кроме того, можно использовать [средство редактирования конфигурации (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) для изменения параметров конфигурации, с помощью графического интерфейса мастера. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Настройка приложения](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md) раздела.  
  
-   WMI позволяет получать информацию о прослушивающих компьютер службах и используемых привязках. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][с помощью Windows Management Instrumentation для диагностики](../../../../docs/framework/wcf/diagnostics/wmi/index.md) раздела.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] также предоставляет несколько инструментов графического интерфейса пользователя (GUI) и командной строки, благодаря которым упрощается создание и развертывание приложений [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], а также управление ими. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Средства Windows Communication Foundation](../../../../docs/framework/wcf/tools.md). Например, можно использовать [средство редактирования конфигурации (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) для создания и редактирования [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] параметры конфигурации, с помощью мастера, вместо непосредственного редактирования XML-кода. Можно также использовать [программы Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) для просмотра, группировки и фильтрации сообщений трассировки, чтобы произвести диагностику, восстановления и проверки неисправностей [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] служб.  
  
## <a name="see-also"></a>См. также  
 [Настройка приложения](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md)  
 [Развертывание служб](../../../../docs/framework/wcf/diagnostics/deploying-services.md)  
 [Справочник по исключениям](../../../../docs/framework/wcf/diagnostics/exceptions-reference/index.md)  
 [Ведение журнала событий](../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [Ведение журнала сообщений](../../../../docs/framework/wcf/diagnostics/message-logging.md)  
 [Редактор конфигурации (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)  
 [Средство просмотра трассировки служб (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)  
 [Средство регистрации ServiceModel](../../../../docs/framework/wcf/diagnostics/servicemodel-registration-tool.md)  
 [Трассировка](../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [С помощью инструментария WMI для диагностики](../../../../docs/framework/wcf/diagnostics/wmi/index.md)  
 [Счетчики производительности](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)  
 [Средства Windows Communication Foundation](../../../../docs/framework/wcf/tools.md)
