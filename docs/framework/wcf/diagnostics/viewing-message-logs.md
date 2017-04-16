---
title: "Просмотр журналов сообщений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3012fa13-f650-45fb-aaea-c5cca8c7d372
caps.latest.revision: 22
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 22
---
# Просмотр журналов сообщений
В этом разделе описывается порядок просмотра журналов сообщений.  
  
## Просмотр журналов сообщений с помощью программы Service Trace Viewer  
 В процессе обработки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] сообщение подвергается преобразованиям.Следовательно, заносимое в журнал сообщение отражает только содержимое сообщения в точке его регистрации \(записи в журнал\), но не содержимое, передаваемое по линии связи.  
  
 Поскольку формат записи сообщения в журнал никак не связан с форматом передачи сообщения, в журнал сообщения всегда заносятся в раскодированном виде.Если ведение журнала сообщений настроено надлежащим образом, все сообщения в журнале должны быть представлены в виде обычного текста.Например, на формат \(обычный текст\) сообщений в журнале никак не влияет использование двоичного кодировщика сообщений.  
  
 Выходные данные прослушивателя XmlWriterTraceListener представляют собой файл, содержащий последовательность XML\-фрагментов.Необходимо иметь в виду, что этот файл не является допустимым файлом XML.Для просмотра файлов журналов сообщений рекомендуется использовать [Программа Service Trace Viewer \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).Дополнительные сведения об использовании этой программы см. в разделе [Использование программы Service Trace Viewer для просмотра скоррелированных трассировок и устранения неполадок](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).  
  
 В программе Service Trace Viewer сообщения содержатся на вкладке **Сообщение**.Сообщения, которые вызвали ошибку обработки или связаны с ошибкой обработки, выделяются желтым \(уровень предупреждения\) или красным \(уровень ошибки\) цветом, в зависимости от серьезности ошибки.При двойном щелчке на сообщении открывается трассировка сообщения в контексте запроса на обработку.  
  
> [!NOTE]
>  Если сообщение не имеет заголовка, тег `<header/>` в журнал не записывается.  
  
## Просмотр сообщений, записанных в журнал клиентом, ретранслятором и службой  
 Конкретная среда может содержать клиент, который отправляет сообщение ретранслятору, который в свою очередь пересылает сообщение службе.Если регистрация сообщений включена во всех трех точках и все три журнала сообщений одновременно просматриваются в [Программа Service Trace Viewer \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md), обмен сообщениями в журнале будет отражен неправильно.Это связано с тем, что идентификаторы `CorrelationId` и `ActivityId` в заголовке сообщения не являются уникальными для каждой пары "отправка\-получение".  
  
 Решить эту проблему можно одним из следующих способов.  
  
-   Одновременно просматривать в [Программа Service Trace Viewer \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) только два из трех журналов сообщений.  
  
-   Если требуется просматривать в [Программа Service Trace Viewer \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) одновременно все три журнала, можно изменить службу\-ретранслятор путем создания нового экземпляра класса <xref:System.ServiceModel.Channels.Message>.Этот экземпляр должен представлять собой копию текста входящего сообщения плюс все заголовки, за исключением заголовков `ActivityId` и `Action`.В следующем примере кода показано, как это сделать.  
  
```  
Message outgoingMessage = Message.CreateMessage(incomingMessage.Version, incomingMessage.Headers.Action, incomingMessage.GetReaderAtBodyContents());  
  
for (int i = 0; i < incomingMessage.Headers.Count; i++)  
{  
   if (incomingMessage.Headers[i].Name.Equals("ActivityId", StringComparison.InvariantCultureIgnoreCase) ||  
incomingMessage.Headers[i].Name.Equals("Action", StringComparison.InvariantCultureIgnoreCase))  
   {  
      continue;  
    }  
    outgoingMessage.Headers.CopyHeaderFrom(incomingMessage, i);  
}  
```  
  
## Исключительные случаи неточного воспроизведения содержимого сообщений в журналах  
 В следующих случаях сообщения, записываемые в журнал, могут не соответствовать в точности потоку октетов, передаваемому по линии связи.  
  
-   При использовании привязки BasicHttpBinding в журнал записываются заголовки конвертов входящих сообщений в пространстве имен \/addressing\/none.  
  
-   Пробелы в журнале могут не соответствовать пробелам в сообщении.  
  
-   Пустые элементы во входящих сообщениях могут быть представлены иначе.Например, \<tag\>\<\/tag\> вместо \<tag\/\>  
  
-   Когда отключена регистрация известных персональных данных \(по умолчанию или путем явного задания enableLoggingKnownPii\="true"\).  
  
-   Когда для преобразования в UTF\-8 включено кодирование.  
  
## См. также  
 [Программа Service Trace Viewer \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)   
 [Использование программы Service Trace Viewer для просмотра скоррелированных трассировок и устранения неполадок](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)   
 [Ведение журнала сообщений](../../../../docs/framework/wcf/diagnostics/message-logging.md)