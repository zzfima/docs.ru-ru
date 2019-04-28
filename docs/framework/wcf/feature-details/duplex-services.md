---
title: Дуплексные службы
ms.date: 05/09/2018
dev_langs:
- csharp
- vb
ms.assetid: 396b875a-d203-4ebe-a3a1-6a330d962e95
ms.openlocfilehash: 33cfcb765b93309d365a85e679107405a55a91f9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61858043"
---
# <a name="duplex-services"></a>Дуплексные службы

Дуплексный контракт службы - это шаблон обмена сообщениями, в котором обе конечные точки могут отправлять сообщения друг другу независимо друг от друга. Следовательно, дуплексная служба может отправлять сообщения обратно конечной точке клиента, обеспечивая поведение, аналогичное событийному. Дуплексная связь имеет место, когда клиент подключается к службе и предоставляет службе канал, по которому служба может отправлять сообщения обратно клиенту. Обратите внимание, что событийное поведение дуплексных служб используется только в сеансе.

Создание дуплексного контракта предполагает создание двух интерфейсов. Первый - интерфейс контракта службы, описывающий операции, которые может вызывать клиент. Необходимо указать этот контракт службы *контракт обратного вызова* в <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> свойство. Контракт обратного вызова представляет собой интерфейс, определяющий операции, которые служба может вызывать в конечной точке клиента. Дуплексный контракт не требует сеанса, хотя дуплексные привязки, предоставляемые системой, используют их.

Ниже приведен пример дуплексного контракта.

[!code-csharp[c_DuplexServices#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/service.cs#0)]
[!code-vb[c_DuplexServices#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/service.vb#0)]

Класс `CalculatorService` реализует основной интерфейс `ICalculatorDuplex`. Служба использует режим экземпляра <xref:System.ServiceModel.InstanceContextMode.PerSession> для поддержания результата для каждого сеанса. Закрытое свойство `Callback` обращается к клиенту по каналу обратного вызова. Служба использует обратный вызов для отправки сообщений обратно клиенту через интерфейс обратного вызова, как показано в следующем примере кода.

[!code-csharp[c_DuplexServices#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/service.cs#1)]
[!code-vb[c_DuplexServices#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/service.vb#1)]

Для получения сообщений от службы клиент обязан предоставить класс, который реализует интерфейс обратного вызова дуплексного контракта. В следующем примере кода демонстрируется класс `CallbackHandler`, реализующий интерфейс `ICalculatorDuplexCallback`.

[!code-csharp[c_DuplexServices#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/client.cs#2)]
[!code-vb[c_DuplexServices#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/client.vb#2)]

Клиент WCF, создаваемый для дуплексного контракта требуется <xref:System.ServiceModel.InstanceContext> предоставления при создании класса. Этот класс <xref:System.ServiceModel.InstanceContext> используется в качестве сайта для объекта, реализующего интерфейс обратного вызова и обрабатывающего сообщения, которые отправляются службой обратно. Класс <xref:System.ServiceModel.InstanceContext> создается с экземпляром класса `CallbackHandler`. Этот объект обрабатывает сообщения, отправляемые службой клиенту в интерфейсе обратного вызова.

[!code-csharp[c_DuplexServices#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/client.cs#3)]
[!code-vb[c_DuplexServices#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/client.vb#3)]

Необходимо настроить конфигурацию для службы таким образом, чтобы предоставлялась привязка, которая поддерживает как сеансовую, так и дуплексную связь. Элемент `wsDualHttpBinding` поддерживает сеансовую и дуплексную связь, предоставляя двойные соединения HTTP (по одному для каждого направления).

На стороне клиента необходимо настроить адрес, который будет использоваться сервером для подключения к клиенту, как показано в следующем примере конфигурации.

> [!NOTE]
> Недуплексные клиенты, которые не смогли пройти проверку с помощью защищенного диалога, как правило, создают исключение <xref:System.ServiceModel.Security.MessageSecurityException>. Однако если дуплексному клиенту, использующему защищенный диалог, не удается пройти проверку, клиент получает вместо этого исключение <xref:System.TimeoutException>.

Если при создании клиента/службы с использованием элемента `WSHttpBinding` не будет включена конечная точка обратного вызова клиента, будет получена следующая ошибка.

```
HTTP could not register URL
htp://+:80/Temporary_Listen_Addresses/<guid> because TCP port 80 is being used by another application.
```

В следующем примере кода показано, как указать его адрес конечной точки программным способом.

```csharp
WSDualHttpBinding binding = new WSDualHttpBinding();
EndpointAddress endptadr = new EndpointAddress("http://localhost:12000/DuplexTestUsingCode/Server");
binding.ClientBaseAddress = new Uri("http://localhost:8000/DuplexTestUsingCode/Client/");
```

```vb
Dim binding As New WSDualHttpBinding()
Dim endptadr As New EndpointAddress("http://localhost:12000/DuplexTestUsingCode/Server")
binding.ClientBaseAddress = New Uri("http://localhost:8000/DuplexTestUsingCode/Client/")
```

В следующем образце кода показано, как задавать в конфигурации адрес конечной точки клиента.

```xml
<client>
    <endpoint name ="ServerEndpoint"
          address="http://localhost:12000/DuplexTestUsingConfig/Server"
          bindingConfiguration="WSDualHttpBinding_IDuplexTest"
            binding="wsDualHttpBinding"
           contract="IDuplexTest" />
</client>
<bindings>
    <wsDualHttpBinding>
        <binding name="WSDualHttpBinding_IDuplexTest"
          clientBaseAddress="http://localhost:8000/myClient/" >
            <security mode="None"/>
         </binding>
    </wsDualHttpBinding>
</bindings>
```

> [!WARNING]
> Дуплексная модель не выполняет автоматического обнаружения закрытия службой или клиентом своего канала. Поэтому в случае неожиданного завершения работы клиента по умолчанию служба не будет уведомлена. Клиенты и службы могут реализовать собственный протокол для уведомления друг друга по усмотрению.

## <a name="see-also"></a>См. также

- [Дуплекс](../../../../docs/framework/wcf/samples/duplex.md)
- [Указание поведения клиента во время выполнения](../../../../docs/framework/wcf/specifying-client-run-time-behavior.md)
- [Практическое руководство. Создание фабрики каналов и использовать его для создания каналов и управления ими](../../../../docs/framework/wcf/feature-details/how-to-create-a-channel-factory-and-use-it-to-create-and-manage-channels.md)
