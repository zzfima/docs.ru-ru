---
title: "Заголовки адресов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b0c94d4a-3bde-4b4d-bb6d-9f12bc3a6940
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Заголовки адресов
В образце заголовков адреса показан процесс передачи клиентами ссылочных параметров в службу с помощью [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Спецификация WS\-Addressing определяет понятие ссылки на конечную точку как способа обращения к определенной конечной точке веб\-службы.В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ссылки на конечные точки моделируются с помощью класса `EndpointAddress`. `EndpointAddress` — это тип поля адреса класса `ServiceEndpoint`.  
  
 Особенностью модели ссылки на конечную точку является то, что каждая ссылка может содержать несколько ссылочных параметров, которые добавляют дополнительные идентификационные сведения.В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] эти ссылочные параметры моделируются как экземпляры класса `AddressHeader`.  
  
 В этом образце клиент добавляет ссылочный параметр в `EndpointAddress` конечной точки клиента.Служба ищет этот ссылочный параметр и использует его значение в логике операции службы "Привет".  
  
## Клиент  
 Чтобы клиент мог отправить ссылочный параметр, он должен добавить заголовок `AddressHeader` в адрес `EndpointAddress` конечной точки `ServiceEndpoint`.Поскольку класс `EndpointAddress` является неизменным, изменение адреса конечной точки необходимо выполнить с помощью класса `EndpointAddressBuilder`.В следующем коде клиент инициализируется для отправки ссылочного параметра как часть сообщения.  
  
```  
HelloClient client = new HelloClient();  
EndpointAddressBuilder builder =   
    new EndpointAddressBuilder(client.Endpoint.Address);  
AddressHeader header =   
    AddressHeader.CreateAddressHeader(IDName, IDNamespace, "John");  
builder.Headers.Add(header);  
client.Endpoint.Address = builder.ToEndpointAddress();  
```  
  
 Код создает `EndpointAddressBuilder` с использованием исходного `EndpointAddress` в качестве первоначального значения.Затем он добавляет только что созданный заголовок адреса. Вызов `CreateAddressHeadercreates` создает заголовок с определенным именем, пространством имен и значением.В этом случае значением является "John".После добавления заголовка в конструктор метод `ToEndpointAddress()` преобразовывает \(изменяемый\) конструктор назад в \(неизменяемый\) адрес конечной точки, который снова присваивается полю адреса конечной точки клиента.  
  
 Теперь при вызове `Console.WriteLine(client.Hello());` клиентом служба может получить значение этого параметра адреса, как показано в результирующих выходных данных клиента.  
  
 `Hello, John`  
  
## Сервер  
 Реализация операции службы `Hello()` использует текущий `OperationContext` для проверки значений заголовков входящего сообщения.  
  
```  
string id = null;  
// look at headers on incoming message  
for (int i = 0;   
     i < OperationContext.Current.IncomingMessageHeaders.Count;   
     ++i)  
{  
    MessageHeaderInfo h =   
        OperationContext.Current.IncomingMessageHeaders[i];  
    // for any reference parameters with the correct name & namespace  
    if (h.IsReferenceParameter &&   
        h.Name == IDName &&   
        h.Namespace == IDNamespace)  
    {  
        // read the value of that header  
        XmlReader xr =   
OperationContext.Current.IncomingMessageHeaders.GetReaderAtHeader(i);  
        id = xr.ReadElementContentAsString();  
    }  
}  
return "Hello, " + id;  
```  
  
 Код выполняет итерацию всех заголовков входящего сообщения, выполняя поиск заголовок, которые являются ссылочными параметрами с определенным именем.При нахождении параметра он считывает значение параметра и сохраняет его в переменной "id".  
  
#### Настройка, построение и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в разделе [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Client\AddressHeaders`  
  
## См. также