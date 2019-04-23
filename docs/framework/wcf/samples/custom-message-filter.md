---
title: Пользовательский фильтр сообщений
ms.date: 03/30/2017
ms.assetid: 98dd0af8-fce6-4255-ac32-42eb547eea67
ms.openlocfilehash: 34e6d851bd0aa3515c5c43521be6213451b7ed12
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59773081"
---
# <a name="custom-message-filter"></a>Пользовательский фильтр сообщений
В этом примере показано, как заменить фильтры сообщений, используемые для перенаправления сообщений в конечные точки Windows Communication Foundation (WCF).  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 При поступлении на сервер первого сообщения из канала сервер должен определить, какие конечные точки, связанные с данным URI, должны получить сообщение. Этот процесс контролируется объектами <xref:System.ServiceModel.Dispatcher.MessageFilter> присоединенными к диспетчеру <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>.  
  
 У каждой конечной точки службы имеется один диспетчер <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>. У диспетчера <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> имеются как фильтр <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A>, так и фильтр <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A>. Объединение этих двух фильтров является фильтром сообщений, используемым для данной конечной точки.  
  
 По умолчанию фильтр <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> для конечной точки соответствует любому сообщению, передаваемому по адресу, который соответствует адресу <xref:System.ServiceModel.EndpointAddress> конечной точки службы. По умолчанию <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> для конечной точки проверяет действие входящего сообщения и сопоставляет любое сообщение с действием, которое соответствует одному из действий операций контракта конечной точки службы (только `IsInitiating` = `true`считаются действия). В результате по умолчанию соответствие фильтру для конечной точки обеспечивается, только если в заголовках "To" обоих сообщений задан адрес <xref:System.ServiceModel.EndpointAddress> конечной точки и действие сообщения соответствует одному из действий операции конечной точки.  
  
 Эти фильтры можно изменить с помощью поведения. В этом образце служба создает интерфейс <xref:System.ServiceModel.Description.IEndpointBehavior>, который заменяет фильтры <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> и <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> в диспетчере <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>:  
  
```  
class FilteringEndpointBehavior : IEndpointBehavior …  
```  
  
 Определяется два фильтра адресов:  
  
```  
// Matches any message whose To address contains the letter 'e'  
class MatchEAddressFilter : MessageFilter …  
// Matches any message whose To address does not contain the letter 'e'  
class MatchNoEAddressFilter : MessageFilter  
```  
  
 Поведение `FilteringEndpointBehavior` делается настраиваемым и предусматривает два различных варианта.  
  
```  
public class FilteringEndpointBehaviorExtension : BehaviorExtensionElement  
```  
  
 Вариант 1 соответствует только адресам, в которых содержится буква 'e' (и которые имеют любое действие), а вариант 2 соответствует только адресам, в которых отсутствует буква 'e':  
  
```  
if (Variation == 1)  
    return new FilteringEndpointBehavior(  
        new MatchEAddressFilter(), new MatchAllMessageFilter());  
else  
    return new FilteringEndpointBehavior(  
        new MatchNoEAddressFilter(), new MatchAllMessageFilter());  
```  
  
 В файле конфигурации служба регистрирует новое поведение:  
  
```xml  
<extensions>  
    <behaviorExtensions>  
        <add name="filteringEndpointBehavior" type="Microsoft.ServiceModel.Samples.FilteringEndpointBehaviorExtension, service" />  
    </behaviorExtensions>  
</extensions>      
```  
  
 Затем служба создает конфигурации `endpointBehavior` для каждого варианта:  
  
```xml  
<endpointBehaviors>  
    <behavior name="endpoint1">  
        <filteringEndpointBehavior variation="1" />  
    </behavior>  
    <behavior name="endpoint2">  
        <filteringEndpointBehavior variation="2" />  
    </behavior>  
</endpointBehaviors>  
```  
  
 Наконец, конечная точка службы ссылается на одну из конфигураций `behaviorConfigurations`:  
  
```xml  
<endpoint address=""  
        bindingConfiguration="ws"  
        listenUri=""   
        binding="wsHttpBinding"  
        contract="Microsoft.ServiceModel.Samples.IHello"   
        behaviorConfiguration="endpoint2" />  
```  
  
 Реализация клиентского приложения является прямолинейной; она создает два канала к URI службы (передавая заданное значение в качестве второго параметра (`via`) методу <xref:System.ServiceModel.Channels.IChannelFactory%601.CreateChannel%28System.ServiceModel.EndpointAddress%29>) и отправляет одно сообщение по каждому каналу, но использует в каждом случае различные адреса конечной точки. В результате исходящие сообщения клиента имеют разные адреса назначения в поле "To" и сервер реагирует соответствующим образом, как показано в выходных данных клиента:  
  
```  
Sending message to urn:e...  
Exception: The message with To 'urn:e' cannot be processed at the receiver, due to an AddressFilter mismatch at the EndpointDispatcher.  Check that the sender and receiver's EndpointAddresses agree.  
  
Sending message to urn:a...  
Hello  
```  
  
 Переключение варианта в файле конфигурации сервера приводит к перестановке фильтров, и на клиенте наблюдается противоположное поведение (доставка сообщения по адресу `urn:e` является успешной, а доставка сообщения по адресу `urn:a` — неудачной).  
  
```xml  
<endpoint address=""  
          bindingConfiguration="ws"  
          listenUri=""   
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.IHello"   
          behaviorConfiguration="endpoint1" />  
```  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageFilter`  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Чтобы построить решение, следуйте инструкциям в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2. Чтобы выполнить образец на одном компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
3. Чтобы выполнить образец на нескольких компьютерах, следуйте инструкциям, приведенным в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md) и измените следующую строку в файле Client.cs.  
  
    ```  
    Uri serviceVia = new Uri("http://localhost/ServiceModelSamples/service.svc");  
    ```  
  
     Замените localhost именем сервера.  
  
    ```  
    Uri serviceVia = new Uri("http://servermachinename/ServiceModelSamples/service.svc");  
    ```  
