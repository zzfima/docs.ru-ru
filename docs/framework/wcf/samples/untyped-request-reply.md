---
title: Нетиповый запрос-ответ
ms.date: 03/30/2017
ms.assetid: 0bf0f9d9-7caf-4d3d-8c9e-2d468cca16a5
ms.openlocfilehash: a526837b9bccf7a6287972e482a189a53ecadaf8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183291"
---
# <a name="untyped-requestreply"></a>Нетипизированный запрос/ответ
В этом образце показано, как определять контракты операций, использующие класс Message.  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Этот пример основан на [получении начала](../../../../docs/framework/wcf/samples/getting-started-sample.md). Контракт службы определяет одну операцию, которая принимает в качестве аргумента тип сообщения и возвращает сообщение. Операция собирает необходимые данные, чтобы вычислять сумму на основе тела сообщения, а затем отправляет эту сумму в виде тела ответного сообщения.  
  
```csharp
[OperationContract(Action = CalculatorService.RequestAction, ReplyAction = CalculatorService.ReplyAction)]  
Message ComputeSum(Message request);  
```  
  
 На стороне службы операция извлекает массив целых значений, переданный в качестве входного сообщения, и вычисляет сумму. Чтобы отправить ответное сообщение, образец создает новое сообщение с соответствующей версией сообщения и параметром Action и добавляет в качестве тела сообщения вычисленную сумму. Это показано в следующем образце кода.  
  
```csharp
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
  
 Клиент использует код, генерируемый [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания прокси-сервера для удаленного сервиса. Чтобы отправить сообщение запроса, клиенту требуется версия сообщения, которая зависит от соответствующего канала. Таким образом, он создает новую область <xref:System.ServiceModel.OperationContextScope>, соответствующую созданному каналу прокси и создающую контекст <xref:System.ServiceModel.OperationContext> с правильной версией сообщения, подставленной в свойство `OutgoingMessageHeaders.MessageVersion`. Клиент передает входящий массив в виде тела сообщения запроса, а затем вызывает метод `ComputeSum` прокси. После этого клиент извлекает сумму входных данных через метод `GetBody<T>` ответного сообщения. Это показано в следующем образце кода.  
  
```csharp
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
  
 Этот образец размещается на веб-сервере, поэтому нужно запускать только клиентский исполняемый файл. Ниже показан образец вывода клиента.  
  
```console  
Prompt>Client.exe  
Sum of numbers passed (1,2,3,4,5) = 15  
  
Press <ENTER> to terminate client.  
```  
  
 Этот образец размещается на веб-сервере, поэтому проверьте указанную на шаге 3 ссылку, чтобы узнать, как выполнять построение и запуск образца.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Чтобы запустить образец в одно- или кросс-машинной конфигурации, следуйте инструкциям в [Запуске образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/running-the-samples.md)  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\Untyped`  
