---
title: Объекты обнаружения Find и FindCriteria
ms.date: 03/30/2017
ms.assetid: 99016fa4-1778-495b-b4cc-0e22fbec42c6
ms.openlocfilehash: c95f8e1b48c4e58c6d521bd06df4a470999fa375
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59095780"
---
# <a name="discovery-find-and-findcriteria"></a>Объекты обнаружения Find и FindCriteria
Операция поиска объектов обнаружения инициируется клиентом для обнаружения одной или нескольких служб и является одним из основных действий, выполняемых при обнаружении. При операции поиска выполняется отправка сообщения зонда WS-Discovery по сети. Службы, которые соответствуют указанному критерию, отвечают сообщениями WS-Discovery ProbeMatch. Дополнительные сведения о сообщениях обнаружения см. в разделе [спецификации WS-Discovery](https://go.microsoft.com/fwlink/?LinkID=122347).  
  
## <a name="discoveryclient"></a>DiscoveryClient  
 Класс <xref:System.ServiceModel.Discovery.DiscoveryClient> обеспечивает механизм выполнения операции поиска и упрощает выполнение операций клиентов обнаружений. Он содержит метод <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>, который выполняет операцию синхронного поиска с блокировкой, и метод <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A>, который инициирует асинхронную операцию поиска без блокировки. Оба метода используют параметр <xref:System.ServiceModel.Discovery.FindCriteria> и передают результаты пользователю с помощью объекта <xref:System.ServiceModel.Discovery.FindResponse>.  
  
## <a name="findcriteria"></a>FindCriteria  
 <xref:System.ServiceModel.Discovery.FindCriteria> имеет несколько свойств, которые могут быть сгруппированы в критерии поиска, которые определяют, какие службы вы ищете, и найти критерии завершения (в том, как долго должен длиться поиск данных). Параметр <xref:System.ServiceModel.Discovery.FindCriteria> может содержать несколько критериев поиска. По умолчанию служба должна соответствовать всем компонентам, в противном случае она не будет считаться службой, которая соответствует критериям. Если необходимо найти службы, которые соответствуют только части критериев, для службы можно реализовать пользовательскую логику поиска или использовать несколько критериев.  
  
 К критериям поиска относятся следующие.  
  
-   <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement> -Необязательно. Имя контракта службы, поиск которой выполняется, и критерий, который обычно используется при поиске служб. Если указано несколько имен контрактов, будет получен ответ только от конечных точек службы, соответствующих всем контрактам. Обратите внимание на то, что в WCF конечной точки поддерживает только один контракт.  
  
-   <xref:System.ServiceModel.Discovery.Configuration.ScopeElement> -Необязательно. Области представляют собой абсолютные идентификаторы URI, которые используются для категоризации отдельных конечных точек служб. Их можно использовать в случаях, когда несколько конечных точек используется для предоставления одного контракта и необходим способ поиска подмножества конечных точек. Если указано более одной области, будет получен ответ только от конечных точек службы, соответствующих всем областям.  
  
-   <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchBy%2A> — Указывает алгоритм сопоставления, который используется для сопоставления областей в сообщении зонда с конечной точкой. Существует пять поддерживаемых правил сопоставления областей.  
  
    -   <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByExact?displayProperty=nameWithType> с учетом регистра базовое сравнение строк.  
  
    -   <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByPrefix?displayProperty=nameWithType> выполняет сопоставление по сегментам, разделенных точкой «/». Поиск `http://contoso/building1` со службой с областью `http://contoso/building/floor1`. Обратите внимание, что он не соответствует `http://contoso/building100` поскольку двух последних сегментов не совпадают.  
  
    -   <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByLdap?displayProperty=nameWithType> Сопоставляет области по сегментам, используя URL-адресом LDAP.  
  
    -   <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByUuid?displayProperty=nameWithType> Сопоставляет области точно с помощью строки UUID.  
  
    -   <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByNone?displayProperty=nameWithType> соответствует только те службы, которые задают области.  
  
     Если правило сопоставления областей не указано, используется <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByPrefix>.  
  
 К критериям прекращения относятся следующие.  
  
1.  <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> -Максимальное время ожидания ответов от служб в сети. Значение времени ожидания по умолчанию - 20 секунд.  
  
2.  <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> -Максимальное количество ожидаемых ответов. Если ответы <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> получены до истечения <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A>, операция поиска завершается.  
  
## <a name="findresponse"></a>FindResponse  
 <xref:System.ServiceModel.Discovery.FindResponse> имеет <xref:System.ServiceModel.Discovery.FindResponse.Endpoints%2A> свойство коллекции, в котором содержатся все ответы, отправленные соответствующими службами в сети. Если ни одна служба не отправила ответ, коллекция пустая. Если ответила одна или несколько служб, все ответы сохраняются в объекте <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>, в котором содержится адрес, контракт и дополнительные сведения о службе.  
  
 В следующем примере описывается выполнение операции поиска в коде.  
  
```  
// Create DiscoveryClient  
DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
  
// Create FindCriteria  
FindCriteria findCriteria = new FindCriteria(typeof(IPrinterService));  
findCriteria.Scopes.Add(new Uri("http://www.contoso.com/building1/floor1"));  
findCriteria.Duration = TimeSpan.FromSeconds(10);   
  
// Find ICalculatorService endpoints              
FindResponse findResponse = discoveryClient.Find(findCriteria);  
  
Console.WriteLine("Found {0} ICalculatorService endpoint(s).", findResponse.Endpoints.Count)  
```  
  
## <a name="see-also"></a>См. также

- [Общие сведения об обнаружении WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)
- [Использование клиентского канала обнаружения](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)
- [Обнаружение с помощью областей](../../../../docs/framework/wcf/samples/discovery-with-scopes-sample.md)
- [Basic](../../../../docs/framework/wcf/samples/basic-sample.md)
