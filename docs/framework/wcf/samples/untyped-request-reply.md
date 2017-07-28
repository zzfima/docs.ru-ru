---
title: "Нетипизированный запрос/ответ | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0bf0f9d9-7caf-4d3d-8c9e-2d468cca16a5
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Нетипизированный запрос/ответ
В этом образце показано, как определять контракты операций, использующие класс Message.  
  
> [!NOTE]
>  Процедура установки и инструкции по построению для данного образца расположены в конце этого раздела.  
  
 Данный образец основан на образце [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md).Контракт службы определяет одну операцию, которая принимает в качестве аргумента тип сообщения и возвращает сообщение.Операция собирает необходимые данные, чтобы вычислять сумму на основе тела сообщения, а затем отправляет эту сумму в виде тела ответного сообщения.  
  
```  
  
[OperationContract(Action = CalculatorService.RequestAction, ReplyAction = CalculatorService.ReplyAction)]  
Message ComputeSum(Message request);  
  
```  
  
 На стороне службы операция извлекает массив целых значений, переданный в качестве входного сообщения, и вычисляет сумму.Чтобы отправить ответное сообщение, образец создает новое сообщение с соответствующей версией сообщения и параметром Action и добавляет в качестве тела сообщения вычисленную сумму.Это показано в следующем образце кода.  
  
```  
  
public Message ComputeSum(Message request)  
{  
    //The body of the message contains a list of numbers which will be   
    //read as a int[] using GetBody<T>  
    int result = 0;  
  
    int[] inputs = request.GetBody<int[]>();  
    foreach (int i in inputs)  
    {  
        result += i;  
    }  
  
    Message response = Message.CreateMessage(request.Version,   
                                      ReplyAction, result);  
    return response;  
}  
  
```  
  
 Клиент использует код, созданный с помощью средства [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), чтобы создать прокси для удаленной службы.Чтобы отправить сообщение запроса, клиенту требуется версия сообщения, которая зависит от соответствующего канала.Таким образом, он создает новую область <xref:System.ServiceModel.OperationContextScope>, соответствующую созданному каналу прокси и создающую контекст <xref:System.ServiceModel.OperationContext> с правильной версией сообщения, подставленной в свойство `OutgoingMessageHeaders.MessageVersion`.Клиент передает входящий массив в виде тела сообщения запроса, а затем вызывает метод `ComputeSum` прокси.После этого клиент извлекает сумму входных данных через метод `GetBody<T>` ответного сообщения.Это показано в следующем образце кода.  
  
```  
  
using (new OperationContextScope(client.InnerChannel))  
{  
    // Call the Sum service operation.  
    int[] values = { 1, 2, 3, 4, 5 };  
    Message request = Message.CreateMessage(  
        OperationContext.Current.OutgoingMessageHeaders.MessageVersion,   
        RequestAction, values);  
    Message reply = client.ComputeSum(request);  
    int response = reply.GetBody<int>();  
  
    Console.WriteLine("Sum of numbers passed (1,2,3,4,5) = {0}",   
                                                       response);  
}  
  
```  
  
 Этот образец размещается на веб\-сервере, поэтому нужно запускать только клиентский исполняемый файл.Ниже показан образец вывода клиента.  
  
```  
  
Prompt>Client.exe  
Sum of numbers passed (1,2,3,4,5) = 15  
  
Press <ENTER> to terminate client.  
  
```  
  
 Этот образец размещается на веб\-сервере, поэтому проверьте указанную на шаге 3 ссылку, чтобы узнать, как выполнять построение и запуск образца.  
  
### Настройка, построение и выполнение образца  
  
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
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Contract\Message\Untyped`  
  
## См. также