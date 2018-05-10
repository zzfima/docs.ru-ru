---
title: Просмотр журналов сообщений
ms.date: 03/30/2017
ms.assetid: 3012fa13-f650-45fb-aaea-c5cca8c7d372
ms.openlocfilehash: 4fa205b52e3d19d2421d93297b5689422775f719
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="viewing-message-logs"></a>Просмотр журналов сообщений
В этом разделе описывается порядок просмотра журналов сообщений.  
  
## <a name="viewing-message-logs-in-the-service-trace-viewer"></a>Просмотр журналов сообщений с помощью программы Service Trace Viewer  
 Сообщение будет преобразован, обрабатывается WCF. Следовательно, заносимое в журнал сообщение отражает только содержимое сообщения в точке его регистрации (записи в журнал), но не содержимое, передаваемое по линии связи.  
  
 Поскольку формат записи сообщения в журнал никак не связан с форматом передачи сообщения, в журнал сообщения всегда заносятся в раскодированном виде. Если ведение журнала сообщений настроено надлежащим образом, все сообщения в журнале должны быть представлены в виде обычного текста. Например, на формат (обычный текст) сообщений в журнале никак не влияет использование двоичного кодировщика сообщений.  
  
 Выходные данные прослушивателя XmlWriterTraceListener представляют собой файл, содержащий последовательность XML-фрагментов. Необходимо иметь в виду, что этот файл не является допустимым файлом XML. Рекомендуется использовать [программы Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) для просмотра файлов журнала сообщений. Дополнительные сведения об использовании этого средства см. в разделе [с помощью программы Service Trace Viewer для просмотра корреляцию трассировок и устранения неполадок](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).  
  
 В программе Service Trace Viewer сообщения содержатся на **сообщение** вкладки. Сообщения, которые вызвали ошибку обработки или связаны с ошибкой обработки, выделяются желтым (уровень предупреждения) или красным (уровень ошибки) цветом, в зависимости от серьезности ошибки. При двойном щелчке на сообщении открывается трассировка сообщения в контексте запроса на обработку.  
  
> [!NOTE]
>  Если сообщение не имеет заголовка, тег `<header/>` в журнал не записывается.  
  
## <a name="viewing-messages-logged-by-a-client-a-relay-and-a-service"></a>Просмотр сообщений, записанных в журнал клиентом, ретранслятором и службой  
 Конкретная среда может содержать клиент, который отправляет сообщение ретранслятору, который в свою очередь пересылает сообщение службе. Если включено ведение журнала сообщений для всех трех местах и просмотре всех трех журналов сообщений в [программы Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) одновременно, обмен сообщениями журнала неправильно отображается. Это связано с тем, что идентификаторы `CorrelationId` и `ActivityId` в заголовке сообщения не являются уникальными для каждой пары "отправка-получение".  
  
 Решить эту проблему можно одним из следующих способов.  
  
-   Просмотр только два из трех журналов сообщений в [программы Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) в любое время.  
  
-   Если необходимо просмотреть все три журналы [программы Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) в то же время служба ретрансляции можно изменить, создав новую <xref:System.ServiceModel.Channels.Message> экземпляра. Этот экземпляр должен представлять собой копию тела входящего сообщения плюс все заголовки, за исключением заголовков `ActivityId` и `Action`. В следующем примере кода показано, как это сделать.  
  
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
  
## <a name="exceptional-cases-for-inaccurate-message-logging-content"></a>Исключительные случаи неточного воспроизведения содержимого сообщений в журналах  
 В следующих случаях сообщения, записываемые в журнал, могут не соответствовать в точности потоку октетов, передаваемому по линии связи.  
  
-   При использовании привязки BasicHttpBinding в журнал записываются заголовки конвертов входящих сообщений в пространстве имен /addressing/none.  
  
-   Пробелы в журнале могут не соответствовать пробелам в сообщении.  
  
-   Пустые элементы во входящих сообщениях могут быть представлены иначе. Например \<тега >\</tag > вместо \<tag / >  
  
-   Когда отключена регистрация известных персональных данных (по умолчанию или путем явного задания enableLoggingKnownPii="true").  
  
-   Когда для преобразования в UTF-8 включено кодирование.  
  
## <a name="see-also"></a>См. также  
 [Средство просмотра трассировки служб (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)  
 [Использование программы Service Trace Viewer для просмотра скоррелированных трассировок и устранения неполадок](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
 [Ведение журналов сообщений](../../../../docs/framework/wcf/diagnostics/message-logging.md)
