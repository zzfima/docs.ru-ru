---
title: Распространение
ms.date: 03/30/2017
ms.assetid: f8181e75-d693-48d1-b333-a776ad3b382a
ms.openlocfilehash: 680f732fa4e75eb1eaa82a861f0a0021dc9c974c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54686339"
---
# <a name="propagation"></a><span data-ttu-id="3f200-102">Распространение</span><span class="sxs-lookup"><span data-stu-id="3f200-102">Propagation</span></span>
<span data-ttu-id="3f200-103">В этом разделе описывается распространение действий в модели трассировки Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="3f200-103">This topic describes activity propagation in the Windows Communication Foundation (WCF) tracing model.</span></span>  
  
## <a name="using-propagation-to-correlate-activities-across-endpoints"></a><span data-ttu-id="3f200-104">Использование распространения для корреляции действий между конечными точками</span><span class="sxs-lookup"><span data-stu-id="3f200-104">Using Propagation to Correlate Activities Across Endpoints</span></span>  
 <span data-ttu-id="3f200-105">Распространение позволяет пользователю получить непосредственную корреляцию трассировок ошибок для одного и того же блока обработки в разных конечных точках приложения, например, для запроса.</span><span class="sxs-lookup"><span data-stu-id="3f200-105">Propagation provides the user with direct correlation of error traces for the same unit of processing across application endpoints, for example, a request.</span></span> <span data-ttu-id="3f200-106">Ошибки, выданные в разных конечных точках для одного и того же блока обработки, группируются в одном действии, даже если они возникли в разных доменах приложения.</span><span class="sxs-lookup"><span data-stu-id="3f200-106">Errors emitted at different endpoints for the same unit of processing are grouped in the same activity, even across application domains.</span></span> <span data-ttu-id="3f200-107">Это делается путем распространения идентификатора действия в заголовках сообщений.</span><span class="sxs-lookup"><span data-stu-id="3f200-107">This is done through propagation of the activity ID in the message headers.</span></span> <span data-ttu-id="3f200-108">Следовательно, если время ожидания клиента истекает из-за внутренней ошибки на сервере, обе ошибки появляются в одном и том же действии, что позволяет непосредственно их скоррелировать.</span><span class="sxs-lookup"><span data-stu-id="3f200-108">Therefore, if a client times out because of an internal error in the server, both errors appear in the same activity for direct correlation.</span></span>  
  
 <span data-ttu-id="3f200-109">Чтобы использовать распространение, задайте параметр `ActivityTracing`, как показано в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="3f200-109">To do this, use the `ActivityTracing` setting as demonstrated in the previous example.</span></span> <span data-ttu-id="3f200-110">Кроме того, задайте атрибут `propagateActivity` для источника трассировки `System.ServiceModel` во всех конечных точках.</span><span class="sxs-lookup"><span data-stu-id="3f200-110">In addition, set the `propagateActivity` attribute for the `System.ServiceModel` trace source at all endpoints.</span></span>  
  
```xml  
<source name="System.ServiceModel" switchValue="Verbose,ActivityTracing" propagateActivity="true" >  
```  
  
 <span data-ttu-id="3f200-111">Распространение действий — настраиваемая функция, вызывающая WCF для добавления заголовков исходящих сообщений, который включает в себя идентификатор действия из локальной памяти ПОТОКА.</span><span class="sxs-lookup"><span data-stu-id="3f200-111">Activity propagation is a configurable capability that causes WCF to add a header to outbound messages, which includes the activity ID on the TLS.</span></span> <span data-ttu-id="3f200-112">Включая этот идентификатор в последующие трассировки на стороне сервера, можно коррелировать действия клиента и сервера.</span><span class="sxs-lookup"><span data-stu-id="3f200-112">By including this on subsequent traces on the server side, we can correlate client and server activities.</span></span>  
  
## <a name="propagation-definition"></a><span data-ttu-id="3f200-113">Определение распространения</span><span class="sxs-lookup"><span data-stu-id="3f200-113">Propagation Definition</span></span>  
 <span data-ttu-id="3f200-114">Идентификатор gAId действия M распространяется на действие N, если выполняются все следующие условия.</span><span class="sxs-lookup"><span data-stu-id="3f200-114">Activity M’s gAId is propagated to activity N if all of the following conditions apply.</span></span>  
  
-   <span data-ttu-id="3f200-115">N создается из-за M.</span><span class="sxs-lookup"><span data-stu-id="3f200-115">N is created because of M</span></span>  
  
-   <span data-ttu-id="3f200-116">Идентификатор gAId M известен N.</span><span class="sxs-lookup"><span data-stu-id="3f200-116">M’s gAId is known to N</span></span>  
  
-   <span data-ttu-id="3f200-117">Идентификатор gAId N равен идентификатору gAId M.</span><span class="sxs-lookup"><span data-stu-id="3f200-117">N's gAId is equal to M’s gAId.</span></span>  
  
 <span data-ttu-id="3f200-118">Идентификатор gAId распространяется через заголовок сообщения ActivityId, как показано в следующей схеме XML.</span><span class="sxs-lookup"><span data-stu-id="3f200-118">The gAId is propagated through the ActivityId message header, as illustrated in the following XML schema.</span></span>  
  
```xml  
<xsd:element name="ActivityId" type="integer" minOccurs="0">  
  <xsd:attribute name="CorrelationId" type="integer" minOccurs="0"/>  
</xsd:element>  
```  
  
 <span data-ttu-id="3f200-119">Ниже приведен пример заголовка сообщения.</span><span class="sxs-lookup"><span data-stu-id="3f200-119">The following is an example of the message header.</span></span>  
  
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
          <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>  
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
  
## <a name="propagation-and-activity-boundaries"></a><span data-ttu-id="3f200-120">Распространение и границы действия</span><span class="sxs-lookup"><span data-stu-id="3f200-120">Propagation and Activity Boundaries</span></span>  
 <span data-ttu-id="3f200-121">Когда идентификатор действия распространяется на конечные точки, получатель сообщения выдает трассировки Start и Stop с этим (распространенным) идентификатором действия.</span><span class="sxs-lookup"><span data-stu-id="3f200-121">When the activity ID is propagated across endpoints, the message receiver emits a Start and Stop traces with that (propagated) activity ID.</span></span> <span data-ttu-id="3f200-122">Следовательно, будет присутствовать трассировка Start и Stop с этим идентификатором gAId из каждого источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="3f200-122">Therefore, there is a Start and Stop trace with that gAId from each trace source.</span></span> <span data-ttu-id="3f200-123">Если конечные точки выполняются в одном и том же процессе и имеют одно и то же имя источника трассировки, создается несколько трассировок Start и Stop с одинаковым идентификатором lAId (одинаковый gAId, одинаковый источник, одинаковый процесс).</span><span class="sxs-lookup"><span data-stu-id="3f200-123">If the endpoints are in the same process and use the same trace source name, multiple Start and Stop with the same lAId (same gAId, same trace source, same process) are created.</span></span>  
  
## <a name="synchronization"></a><span data-ttu-id="3f200-124">Синхронизация</span><span class="sxs-lookup"><span data-stu-id="3f200-124">Synchronization</span></span>  
 <span data-ttu-id="3f200-125">Чтобы синхронизировать события между конечными точками, выполняемыми на разных компьютерах, к заголовку ActivityId, распространяемому в сообщениях, добавляется заголовок CorrelationId.</span><span class="sxs-lookup"><span data-stu-id="3f200-125">To synchronize events across endpoints that run on different machines, a CorrelationId is added to the ActivityId header that is propagated in messages.</span></span> <span data-ttu-id="3f200-126">Средства могут использовать этот идентификатор для синхронизации событий между компьютерами с разным системным временем.</span><span class="sxs-lookup"><span data-stu-id="3f200-126">Tools can use this ID to synchronize events across machines with clock discrepancy.</span></span> <span data-ttu-id="3f200-127">В частности, программа Service Trace Viewer использует этот идентификатор для отображения потоков сообщений между конечными точками.</span><span class="sxs-lookup"><span data-stu-id="3f200-127">Specifically, the Service Trace Viewer tool uses this ID for showing message flows between endpoints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f200-128">См. также</span><span class="sxs-lookup"><span data-stu-id="3f200-128">See also</span></span>
- [<span data-ttu-id="3f200-129">Настройка трассировки</span><span class="sxs-lookup"><span data-stu-id="3f200-129">Configuring Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)
- [<span data-ttu-id="3f200-130">Использование программы Service Trace Viewer для просмотра скоррелированных трассировок и устранения неполадок</span><span class="sxs-lookup"><span data-stu-id="3f200-130">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [<span data-ttu-id="3f200-131">Сценарии сквозной трассировки</span><span class="sxs-lookup"><span data-stu-id="3f200-131">End-To-End Tracing Scenarios</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)
- [<span data-ttu-id="3f200-132">Средство просмотра трассировки служб (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="3f200-132">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
