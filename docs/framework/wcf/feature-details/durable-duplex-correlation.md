---
title: Сохраняемая дуплексная корреляция
ms.date: 03/30/2017
ms.assetid: 8eb0e49a-6d3b-4f7e-a054-0d4febee2ffb
ms.openlocfilehash: bb73cef5190a0b146e713ef1adae24219dc2eed8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185172"
---
# <a name="durable-duplex-correlation"></a>Сохраняемая дуплексная корреляция
Сохраняемую дуплексную корреляцию, также называемую корреляцией обратных вызовов, удобно использовать, когда служба рабочего процесса должна отправлять обратный вызов исходному вызывающему объекту. В отличие от дуплекса WCF, обратный вызов может выполняться в любой момент в будущем и не связан с одним и тем же каналом или временем существования канала. Единственное требование - у вызывающего должна быть конечная точка, прослушивающая сообщение обратного вызова. Благодаря этому обеспечивается возможность взаимодействия двух служб рабочего процесса в долговременных диалогах. В данном разделе приведены общие сведения о сохраняемой дуплексной корреляции.  
  
## <a name="using-durable-duplex-correlation"></a>Использование сохраняемой дуплексной корреляции  
 Чтобы использовать сохраняемую дуплексную корреляцию, две службы должны использовать контекстную привязку, которая поддерживает двусторонние операции, такие как <xref:System.ServiceModel.NetTcpContextBinding> или <xref:System.ServiceModel.WSHttpContextBinding>. Вызывающая служба регистрирует <xref:System.ServiceModel.WSHttpContextBinding.ClientCallbackAddress%2A> с привязкой на их клиентской конечной точке <xref:System.ServiceModel.Endpoint>. Принимающая служба получает эти данные в первоначальном вызове, а затем использует их для собственных <xref:System.ServiceModel.Endpoint> в действии <xref:System.ServiceModel.Activities.Send>, выполняющем обратный вызов вызывающей службы. В этом примере две службы взаимодействуют друг с другом. Первая служба вызывает метод для второй службы, а затем ожидает ответа. Второй службе известно имя метода обратного вызова, но во время разработки конечная точка службы, реализующая этот метод, неизвестна.  
  
> [!NOTE]
> Сохраняемая дуплексная корреляция может быть использована только в случае, если параметр <xref:System.ServiceModel.Channels.AddressingVersion> конечной точки установлен в значение <xref:System.ServiceModel.Channels.AddressingVersion.WSAddressing10%2A>. Если это не так, то <xref:System.InvalidOperationException> исключение брошено со следующим сообщением: "Сообщение содержит заголовок контекста обратного вызова с конечной точкой ссылки для [AddressingVersion](http://schemas.xmlsoap.org/ws/2004/08/addressing). Контекст обратного вызова может передаваться только тогда, когда AddressingVersion настроен с 'WSAddressing10'.
  
 В следующем примере выполняется размещение службы рабочего процесса, с помощью которой создается обратный вызов <xref:System.ServiceModel.Endpoint> с помощью привязки <xref:System.ServiceModel.WSHttpContextBinding>.  
  
```csharp  
// Host WF Service 1.  
string baseAddress1 = "http://localhost:8080/Service1";  
WorkflowServiceHost host1 = new WorkflowServiceHost(GetWF1(), new Uri(baseAddress1));  
  
// Add the callback endpoint.  
WSHttpContextBinding Binding1 = new WSHttpContextBinding();  
host1.AddServiceEndpoint("ICallbackItemsReady", Binding1, "ItemsReady");  
  
// Add the service endpoint.  
host1.AddServiceEndpoint("IService1", Binding1, baseAddress1);  
  
// Open the first workflow service.  
host1.Open();  
Console.WriteLine("Service1 waiting at: {0}", baseAddress1);  
```  
  
 Рабочий процесс, реализующий эту службу рабочего процесса, инициализирует корреляцию обратного вызова со своим действием <xref:System.ServiceModel.Activities.Send> и ссылается на эту конечную точку обратного вызова из действия <xref:System.ServiceModel.Activities.Receive>, для которого выполнена корреляция с действием <xref:System.ServiceModel.Activities.Send>. В следующем примере представлен рабочий процесс, который возвращается из метода `GetWF1`.  
  
```csharp  
Variable<CorrelationHandle> CallbackHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = "IService1",  
    OperationName = "StartOrder"  
};  
  
Send GetItems = new Send  
{  
    CorrelationInitializers =
    {  
        new CallbackCorrelationInitializer  
        {  
            CorrelationHandle = CallbackHandle  
        }  
    },  
    ServiceContractName = "IService2",  
    OperationName = "StartItems",  
    Endpoint = new Endpoint  
    {  
        AddressUri = new Uri("http://localhost:8081/Service2"),  
        Binding = new WSHttpContextBinding  
        {  
            ClientCallbackAddress = new Uri("http://localhost:8080/Service1/ItemsReady")
        }  
    }  
};  
  
Receive ItemsReady = new Receive  
{  
    ServiceContractName = "ICallbackItemsReady",  
    OperationName = "ItemsReady",  
    CorrelatesWith = CallbackHandle,  
};  
  
Activity wf = new Sequence  
{  
    Variables =  
    {  
        CallbackHandle  
    },  
    Activities =  
    {  
        StartOrder,  
        new WriteLine  
        {  
            Text = "WF1 - Started"  
        },  
        GetItems,  
        new WriteLine  
        {  
            Text = "WF1 - Request Submitted"  
        },  
        ItemsReady,  
        new WriteLine  
        {  
            Text = "WF1 - Items Received"  
        }  
     }  
};  
```  
  
 Вторая служба рабочего процесса размещается с использованием предоставленной системой контекстной привязки.  
  
```csharp  
// Host WF Service 2.  
string baseAddress2 = "http://localhost:8081/Service2";  
WorkflowServiceHost host2 = new WorkflowServiceHost(GetWF2(), new Uri(baseAddress2));  
  
// Add the service endpoint.  
WSHttpContextBinding Binding2 = new WSHttpContextBinding();  
host2.AddServiceEndpoint("IService2", Binding2, baseAddress2);  
  
// Open the second workflow service.  
host2.Open();  
Console.WriteLine("Service2 waiting at: {0}", baseAddress2);  
```  
  
 Рабочий процесс, реализующий эту службу рабочего процесса, начинается с действия <xref:System.ServiceModel.Activities.Receive>. Это действие получения инициализирует корреляцию обратного вызова для этой службы, откладывает выполнение на определенный период времени для моделирования долгосрочных работ, а затем выполняет обратный вызов в первую службу с использованием контекста обратного вызова, переданного в первом вызове в службу. В следующем примере представлен рабочий процесс, который возвращается из вызова `GetWF2`. Обратите внимание, что в действии <xref:System.ServiceModel.Activities.Send> имеется адрес местозаполнителя `http://www.contoso.com`; фактический адрес, используемый во время выполнения, предоставляется обратным вызовом.  
  
```csharp  
Variable<CorrelationHandle> ItemsCallbackHandle = new Variable<CorrelationHandle>();  
  
Receive StartItems = new Receive  
{  
    CorrelationInitializers =
    {  
        new CallbackCorrelationInitializer  
        {  
            CorrelationHandle = ItemsCallbackHandle  
        }  
    },  
    CanCreateInstance = true,  
    ServiceContractName = "IService2",  
    OperationName = "StartItems"  
};  
  
Send ItemsReady = new Send  
{  
    CorrelatesWith = ItemsCallbackHandle,  
    Endpoint = new Endpoint  
    {  
        // The callback address on the binding is used  
        // instead of this placeholder address.  
        AddressUri = new Uri("http://www.contoso.com"),  
  
        Binding = new WSHttpContextBinding()  
    },  
    OperationName = "ItemsReady",  
    ServiceContractName = "ICallbackItemsReady"  
};  
  
Activity wf = new Sequence  
{  
    Variables =  
    {  
        ItemsCallbackHandle  
    },  
    Activities =  
    {  
        StartItems,  
        new WriteLine  
        {  
            Text = "WF2 - Request Received"  
        },  
        new Delay  
        {  
            Duration = TimeSpan.FromMinutes(90)  
        },  
        new WriteLine  
        {  
            Text = "WF2 - Sending items"  
        },  
        ItemsReady,  
        new WriteLine  
        {  
            Text = "WF2 - Items sent"  
        }  
     }  
};  
```  
  
 При вызове метода `StartOrder` в первом рабочем процессе отображается следующий результат, в котором показан ход выполнения с двумя рабочими процессами.  
  
```output  
Service1 waiting at: http://localhost:8080/Service1  
Service2 waiting at: http://localhost:8081/Service2  
Press enter to exit.
WF1 - Started  
WF2 - Request Received  
WF1 - Request Submitted  
WF2 - Sending items  
WF2 - Items sent  
WF1 - Items Received  
```  
  
 В этом примере оба рабочих процесса явно управляют корреляцией с помощью объекта <xref:System.ServiceModel.Activities.CallbackCorrelationInitializer>. Поскольку в этих образцах имеется только одна корреляция, настройки управления <xref:System.ServiceModel.Activities.CorrelationHandle>, заданные по умолчанию, не требуют изменений.
