---
title: Просмотр журналов сообщений
ms.date: 03/30/2017
ms.assetid: 3012fa13-f650-45fb-aaea-c5cca8c7d372
ms.openlocfilehash: c926833a48331f191b6dcc3323f0dfda329b7014
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968668"
---
# <a name="viewing-message-logs"></a>Просмотр журналов сообщений
В этом разделе описывается порядок просмотра журналов сообщений.  
  
## <a name="viewing-message-logs-in-the-service-trace-viewer"></a>Просмотр журналов сообщений с помощью программы Service Trace Viewer  
 Сообщение будет преобразовано в том виде, в котором оно обрабатывается WCF. Следовательно, заносимое в журнал сообщение отражает только содержимое сообщения в точке его регистрации (записи в журнал), но не содержимое, передаваемое по линии связи.  
  
 Поскольку формат записи сообщения в журнал никак не связан с форматом передачи сообщения, в журнал сообщения всегда заносятся в раскодированном виде. Если ведение журнала сообщений настроено надлежащим образом, все сообщения в журнале должны быть представлены в виде обычного текста. Например, на формат (обычный текст) сообщений в журнале никак не влияет использование двоичного кодировщика сообщений.  
  
 Выходные данные прослушивателя XmlWriterTraceListener представляют собой файл, содержащий последовательность XML-фрагментов. Необходимо иметь в виду, что этот файл не является допустимым файлом XML. Для просмотра файлов журнала сообщений рекомендуется использовать [средство Service Trace Viewer (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) . Дополнительные сведения об использовании этого средства см. в разделе [Использование Service Trace Viewer для просмотра коррелированных трассировок и устранения неполадок](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).  
  
 В средстве просмотра трассировки служб сообщения отображаются на вкладке **сообщение** . Сообщения, которые вызвали ошибку обработки или связаны с ошибкой обработки, выделяются желтым (уровень предупреждения) или красным (уровень ошибки) цветом, в зависимости от серьезности ошибки. При двойном щелчке на сообщении открывается трассировка сообщения в контексте запроса на обработку.  
  
> [!NOTE]
> Если сообщение не имеет заголовка, тег `<header/>` в журнал не записывается.  
  
## <a name="viewing-messages-logged-by-a-client-a-relay-and-a-service"></a>Просмотр сообщений, записанных в журнал клиентом, ретранслятором и службой  
 Конкретная среда может содержать клиент, который отправляет сообщение ретранслятору, который в свою очередь пересылает сообщение службе. Если ведение журнала сообщений включено для всех трех расположений и все три журнала сообщений просматриваются в средстве [Service Trace Viewer (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) одновременно, то обмен сообщениями журнала сообщений будет неверно сформирован. Это связано с тем, что идентификаторы `CorrelationId` и `ActivityId` в заголовке сообщения не являются уникальными для каждой пары "отправка-получение".  
  
 Решить эту проблему можно одним из следующих способов.  
  
- Только два из трех журналов сообщений в средстве [просмотра трассировки службы (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) следует просматривать в любое время.  
  
- Если необходимо одновременно просмотреть все три журнала в [средстве просмотра трассировки службы (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) , можно изменить службу ретрансляции, создав новый <xref:System.ServiceModel.Channels.Message> экземпляр. Этот экземпляр должен представлять собой копию тела входящего сообщения плюс все заголовки, за исключением заголовков `ActivityId` и `Action`. В следующем примере кода показано, как это сделать.  
  
```csharp
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
  
- При использовании привязки BasicHttpBinding в журнал записываются заголовки конвертов входящих сообщений в пространстве имен /addressing/none.  
  
- Пробелы могут быть несовпадающими.  
  
- Пустые элементы во входящих сообщениях могут быть представлены иначе. Например, \<Tag >\</Таг > вместо \<Tag/>  
  
- Когда отключена регистрация известных персональных данных (по умолчанию или путем явного задания enableLoggingKnownPii="true").  
  
- Когда для преобразования в UTF-8 включено кодирование.  
  
## <a name="see-also"></a>См. также

- [Средство просмотра трассировки служб (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
- [Использование программы Service Trace Viewer для просмотра скоррелированных трассировок и устранения неполадок](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [Ведение журналов сообщений](../../../../docs/framework/wcf/diagnostics/message-logging.md)
