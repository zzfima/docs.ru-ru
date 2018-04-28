---
title: Заголовки адресов
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b0c94d4a-3bde-4b4d-bb6d-9f12bc3a6940
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1392e06b0148ee24c9591839b58baf45da5109d4
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="address-headers"></a><span data-ttu-id="e1a12-102">Заголовки адресов</span><span class="sxs-lookup"><span data-stu-id="e1a12-102">Address Headers</span></span>
<span data-ttu-id="e1a12-103">В образце заголовков адреса показан процесс передачи клиентами ссылочных параметров в службу с помощью [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1a12-103">The Address Headers sample demonstrates how clients can pass reference parameters to a service using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e1a12-104">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="e1a12-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="e1a12-105">Спецификация WS-Addressing определяет понятие ссылки на конечную точку как способа обращения к определенной конечной точке веб-службы.</span><span class="sxs-lookup"><span data-stu-id="e1a12-105">The WS-Addressing specification defines the notion of an endpoint reference as a way to address a particular Web service endpoint.</span></span> <span data-ttu-id="e1a12-106">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ссылки на конечные точки моделируются с помощью класса `EndpointAddress`. `EndpointAddress` - это тип поля адреса класса `ServiceEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="e1a12-106">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], endpoint references are modeled using the `EndpointAddress` class - `EndpointAddress` is the type of the Address field of the `ServiceEndpoint` class.</span></span>  
  
 <span data-ttu-id="e1a12-107">Особенностью модели ссылки на конечную точку является то, что каждая ссылка может содержать несколько ссылочных параметров, которые добавляют дополнительные идентификационные сведения.</span><span class="sxs-lookup"><span data-stu-id="e1a12-107">Part of the endpoint reference model is that each reference can carry some reference parameters that add extra identifying information.</span></span> <span data-ttu-id="e1a12-108">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] эти ссылочные параметры моделируются как экземпляры класса `AddressHeader`.</span><span class="sxs-lookup"><span data-stu-id="e1a12-108">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], these reference parameters are modeled as instances of `AddressHeader` class.</span></span>  
  
 <span data-ttu-id="e1a12-109">В этом образце клиент добавляет ссылочный параметр в `EndpointAddress` конечной точки клиента.</span><span class="sxs-lookup"><span data-stu-id="e1a12-109">In this sample, the client adds a reference parameter to the `EndpointAddress` of the client endpoint.</span></span> <span data-ttu-id="e1a12-110">Служба ищет этот ссылочный параметр и использует его значение в логике операции службы "Привет".</span><span class="sxs-lookup"><span data-stu-id="e1a12-110">The service looks for this reference parameter and uses its value in the logic of its "Hello" service operation.</span></span>  
  
## <a name="client"></a><span data-ttu-id="e1a12-111">"Клиент";</span><span class="sxs-lookup"><span data-stu-id="e1a12-111">Client</span></span>  
 <span data-ttu-id="e1a12-112">Чтобы клиент мог отправить ссылочный параметр, он должен добавить заголовок `AddressHeader` в адрес `EndpointAddress` конечной точки `ServiceEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="e1a12-112">For the client to send a reference parameter, it must add an `AddressHeader` to the `EndpointAddress` of the `ServiceEndpoint`.</span></span> <span data-ttu-id="e1a12-113">Поскольку класс `EndpointAddress` является неизменным, изменение адреса конечной точки необходимо выполнить с помощью класса `EndpointAddressBuilder`.</span><span class="sxs-lookup"><span data-stu-id="e1a12-113">Because the `EndpointAddress` class is immutable, modification of an endpoint address must be done using the `EndpointAddressBuilder` class.</span></span> <span data-ttu-id="e1a12-114">В следующем коде клиент инициализируется для отправки ссылочного параметра как часть сообщения.</span><span class="sxs-lookup"><span data-stu-id="e1a12-114">The following code initializes the client to send a reference parameter as part of its message.</span></span>  
  
```csharp   
HelloClient client = new HelloClient();  
EndpointAddressBuilder builder =   
    new EndpointAddressBuilder(client.Endpoint.Address);  
AddressHeader header =   
    AddressHeader.CreateAddressHeader(IDName, IDNamespace, "John");  
builder.Headers.Add(header);  
client.Endpoint.Address = builder.ToEndpointAddress();  
```  
  
 <span data-ttu-id="e1a12-115">Код создает `EndpointAddressBuilder` с использованием исходного `EndpointAddress` в качестве первоначального значения.</span><span class="sxs-lookup"><span data-stu-id="e1a12-115">The code creates an `EndpointAddressBuilder` using the original `EndpointAddress` as an initial value.</span></span> <span data-ttu-id="e1a12-116">Затем он добавляет только что созданный заголовок адреса. Вызов `CreateAddressHeadercreates` создает заголовок с определенным именем, пространством имен и значением.</span><span class="sxs-lookup"><span data-stu-id="e1a12-116">It then adds a newly created address header; the call to `CreateAddressHeadercreates` a header with a particular name, namespace, and value.</span></span> <span data-ttu-id="e1a12-117">В этом случае значением является "John".</span><span class="sxs-lookup"><span data-stu-id="e1a12-117">Here the value is "John".</span></span> <span data-ttu-id="e1a12-118">После добавления заголовка в конструктор метод `ToEndpointAddress()` преобразовывает (изменяемый) конструктор назад в (неизменяемый) адрес конечной точки, который снова присваивается полю адреса конечной точки клиента.</span><span class="sxs-lookup"><span data-stu-id="e1a12-118">Once the header is added to the builder, the `ToEndpointAddress()` method converts the (mutable) builder back into an (immutable) endpoint address, which is assigned back to the client endpoint's Address field.</span></span>  
  
 <span data-ttu-id="e1a12-119">Теперь при вызове `Console.WriteLine(client.Hello());` клиентом служба может получить значение этого параметра адреса, как показано в результирующих выходных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="e1a12-119">Now when the client calls `Console.WriteLine(client.Hello());`, the service is able to get the value of this address parameter, as seen in the resulting output of the client.</span></span>  
  
 `Hello, John`  
  
## <a name="server"></a><span data-ttu-id="e1a12-120">Сервер</span><span class="sxs-lookup"><span data-stu-id="e1a12-120">Server</span></span>  
 <span data-ttu-id="e1a12-121">Реализация операции службы `Hello()` использует текущий `OperationContext` для проверки значений заголовков входящего сообщения.</span><span class="sxs-lookup"><span data-stu-id="e1a12-121">The implementation of the service operation `Hello()` uses the current `OperationContext` to inspect the values of the headers on the incoming message.</span></span>  
  
```csharp   
string id = null;  
// look at headers on incoming message  
for (int i = 0;   
     i < OperationContext.Current.IncomingMessageHeaders.Count;   
     ++i)  
{  
    MessageHeaderInfo h = OperationContext.Current.IncomingMessageHeaders[i];  
    // for any reference parameters with the correct name & namespace  
    if (h.IsReferenceParameter &&   
        h.Name == IDName &&   
        h.Namespace == IDNamespace)  
    {  
        // read the value of that header  
        XmlReader xr = OperationContext.Current.IncomingMessageHeaders.GetReaderAtHeader(i);  
        id = xr.ReadElementContentAsString();  
    }  
}  
return "Hello, " + id;  
```  
  
 <span data-ttu-id="e1a12-122">Код выполняет итерацию всех заголовков входящего сообщения, выполняя поиск заголовок, которые являются ссылочными параметрами с определенным именем.</span><span class="sxs-lookup"><span data-stu-id="e1a12-122">The code iterates over all the headers on the incoming message, looking for headers that are reference parameters with the particular name and.</span></span> <span data-ttu-id="e1a12-123">При нахождении параметра он считывает значение параметра и сохраняет его в переменной "id".</span><span class="sxs-lookup"><span data-stu-id="e1a12-123">When the parameter is found, it reads the value of the parameter and stores it in the "id" variable.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e1a12-124">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="e1a12-124">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="e1a12-125">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e1a12-125">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="e1a12-126">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e1a12-126">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="e1a12-127">Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e1a12-127">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e1a12-128">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e1a12-128">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e1a12-129">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e1a12-129">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e1a12-130">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) Чтобы загрузить все [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="e1a12-130">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e1a12-131">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="e1a12-131">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\AddressHeaders`  
  
## <a name="see-also"></a><span data-ttu-id="e1a12-132">См. также</span><span class="sxs-lookup"><span data-stu-id="e1a12-132">See Also</span></span>
