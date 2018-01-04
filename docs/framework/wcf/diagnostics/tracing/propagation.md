---
title: "Распространение"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8181e75-d693-48d1-b333-a776ad3b382a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 17b20b76d4932272c8e2a9e26603dc8483505242
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="propagation"></a>Распространение
В этом разделе описывается распространение действий в модели трассировки [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
## <a name="using-propagation-to-correlate-activities-across-endpoints"></a>Использование распространения для корреляции действий между конечными точками  
 Распространение позволяет пользователю получить непосредственную корреляцию трассировок ошибок для одного и того же блока обработки в разных конечных точках приложения, например, для запроса. Ошибки, выданные в разных конечных точках для одного и того же блока обработки, группируются в одном действии, даже если они возникли в разных доменах приложения. Это делается путем распространения идентификатора действия в заголовках сообщений. Следовательно, если время ожидания клиента истекает из-за внутренней ошибки на сервере, обе ошибки появляются в одном и том же действии, что позволяет непосредственно их скоррелировать.  
  
 Чтобы использовать распространение, задайте параметр `ActivityTracing`, как показано в предыдущем примере. Кроме того, задайте атрибут `propagateActivity` для источника трассировки `System.ServiceModel` во всех конечных точках.  
  
```xml  
<source name="System.ServiceModel" switchValue="Verbose,ActivityTracing" propagateActivity="true" >  
```  
  
 Распространение действий — настраиваемая функция, при использовании которой [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] добавляет в исходящие сообщения заголовок, содержащий идентификатор действия из локальной памяти потока. Включая этот идентификатор в последующие трассировки на стороне сервера, можно коррелировать действия клиента и сервера.  
  
## <a name="propagation-definition"></a>Определение распространения  
 Идентификатор gAId действия M распространяется на действие N, если выполняются все следующие условия.  
  
-   N создается из-за M.  
  
-   Идентификатор gAId M известен N.  
  
-   Идентификатор gAId N равен идентификатору gAId M.  
  
 Идентификатор gAId распространяется через заголовок сообщения ActivityId, как показано в следующей схеме XML.  
  
```xml  
<xsd:element name="ActivityId" type="integer" minOccurs="0">  
  <xsd:attribute name="CorrelationId" type="integer" minOccurs="0"/>  
</xsd:element>  
```  
  
 Ниже приведен пример заголовка сообщения.  
  
```xml  
<MessageLogTraceRecord>  
  <s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope"     
                      xmlns:a="http://www.w3.org/2005/08/addressing">  
    <s:Header>  
      <a:Action s:mustUnderstand="1">http://Microsoft.ServiceModel.Samples/ICalculator/Subtract  
      </a:Action>  
      <a:MessageID>urn:uuid:f0091eae-d339-4c7e-9408-ece34602f1ce  
      </a:MessageID>  
      <ActivityId CorrelationId="f94c6af1-7d5d-4295-b693-4670a8a0ce34"   
  
               xmlns="http://schemas.microsoft.com/2004/09/ServiceModel/Diagnostics">  
        17f59a29-b435-4a15-bf7b-642ffc40eac8  
      </ActivityId>  
      <a:ReplyTo>  
          <a:Address>http://www.w3.org/2005/08/addressing/anonymous  
          </a:Address>  
      </a:ReplyTo>  
      <a:To s:mustUnderstand="1">net.tcp://localhost/servicemodelsamples/service</a:To>  
   </s:Header>  
   <s:Body>  
     <Subtract xmlns="http://Microsoft.ServiceModel.Samples">  
       <n1>145</n1>  
       <n2>76.54</n2>  
     </Subtract>  
   </s:Body>  
  </s:Envelope>  
</MessageLogTraceRecord>  
```  
  
## <a name="propagation-and-activity-boundaries"></a>Распространение и границы действия  
 Когда идентификатор действия распространяется на конечные точки, получатель сообщения выдает трассировки Start и Stop с этим (распространенным) идентификатором действия. Следовательно, будет присутствовать трассировка Start и Stop с этим идентификатором gAId из каждого источника трассировки. Если конечные точки выполняются в одном и том же процессе и имеют одно и то же имя источника трассировки, создается несколько трассировок Start и Stop с одинаковым идентификатором lAId (одинаковый gAId, одинаковый источник, одинаковый процесс).  
  
## <a name="synchronization"></a>Синхронизация  
 Чтобы синхронизировать события между конечными точками, выполняемыми на разных компьютерах, к заголовку ActivityId, распространяемому в сообщениях, добавляется заголовок CorrelationId. Средства могут использовать этот идентификатор для синхронизации событий между компьютерами с разным системным временем. В частности, программа Service Trace Viewer использует этот идентификатор для отображения потоков сообщений между конечными точками.  
  
## <a name="see-also"></a>См. также  
 [Настройка трассировки](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)  
 [Использование программы Service Trace Viewer для просмотра скоррелированных трассировок и устранения неполадок](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
 [Сценарии сквозной трассировки](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)  
 [Средство просмотра трассировки служб (SvcTraceViewer.exe)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
