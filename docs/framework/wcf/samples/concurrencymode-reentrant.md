---
title: Повторный вход ConcurrencyMode
ms.date: 03/30/2017
ms.assetid: b2046c38-53d8-4a6c-a084-d6c7091d92b1
ms.openlocfilehash: 613a1ed827173b3915892dda54dd20ebabdf6dcf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183894"
---
# <a name="concurrencymode-reentrant"></a>Повторный вход ConcurrencyMode
Этот образец демонстрирует необходимость и последствия использования ConcurrencyMode.Reentrant в реализации службы. Поведение ConcurrencyMode.Reentrant подразумевает, что служба (или обратный вызов) обрабатывает только одно сообщение в данный момент времени (аналогично `ConcurencyMode.Single`). Чтобы обеспечить безопасность потока, Windows Communication Foundation `InstanceContext` (WCF) блокирует обработку сообщения, чтобы не было других сообщений. В режиме Reentrant объект `InstanceContext` разблокируется непосредственно перед тем, как служба делает исходящий вызов, что делает возможным последующий вызов (который может быть реентерабельным, как показано в этом образце), и снова блокируется при следующем его поступлении в службу. Для демонстрации этого поведения в образце показано, как клиент и служба могут отправлять сообщения друг другу, используя дуплексный контракт.  
  
 Определенный в примере контракт является дуплексным: метод `Ping` реализуется службой, а метод обратного вызова `Pong` реализуется клиентом. Клиент вызывает метод `Ping` сервера со счетчиком тактов, тем самым инициируя вызов. Служба проверяет, отличен ли счетчик тактов от нуля, и затем вызывает метод обратного вызова `Pong`, одновременно уменьшая на единицу счетчик тактов. Это делает следующий код в образце.  
  
```csharp
public void Ping(int ticks)  
{  
     Console.WriteLine("Ping: Ticks = " + ticks);  
     //Keep pinging back and forth till Ticks reaches 0.  
     if (ticks != 0)  
     {  
         OperationContext.Current.GetCallbackChannel<IPingPongCallback>().Pong((ticks - 1));  
     }  
}  
```  
  
 Реализация метода `Pong` обратного вызова имеет ту же логику, что и реализация метода `Ping`. Это значит, что она сравнивает значение счетчика тактов с нулем, а затем вызывает метод `Ping` по каналу обратного вызова (в данном случае это канал, который использовался для отправки исходного сообщения `Ping`), уменьшая счетчик тактов на 1. Когда счетчик тактов достигает 0, метод завершает работу, возвращая все ответы в первый вызов, выполненный клиентом, который запустил вызов. Это показано в реализации обратного вызова.  
  
```csharp
public void Pong(int ticks)  
{  
    Console.WriteLine("Pong: Ticks = " + ticks);  
    if (ticks != 0)  
    {  
        //Retrieve the Callback  Channel (in this case the Channel which was used to send the  
        //original message) and make an outgoing call until ticks reaches 0.  
        IPingPong channel = OperationContext.Current.GetCallbackChannel<IPingPong>();  
        channel.Ping((ticks - 1));  
    }  
}  
```  
  
 И метод `Ping`, и метод `Pong` работают по шаблону "запрос-ответ", что означает, что первый вызов метода `Ping` не возвращается, пока не будет возвращен вызов метода `CallbackChannel<T>.Pong()`. На стороне клиента метод `Pong` не может возвратиться до тех пор, пока не будет возвращен следующий сделанный им вызов метода `Ping`. Поскольку и обратный вызов, и служба должны делать исходящие вызовы "запрос-ответ", прежде чем они смогут ответить на ожидающий запрос, обе реализации должны быть отмечены поведением ConcurrencyMode.Reentrant.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Чтобы запустить образец в одно- или кросс-машинной конфигурации, следуйте инструкциям в [Запуске образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/running-the-samples.md)  
  
## <a name="demonstrates"></a>Что демонстрирует  
 Чтобы выполнить образец, постройте клиентский и серверный проекты. Затем откройте два командных окна \<и измените каталоги на образец \<> »CS-Service-bin-debug и образец> »CS-Client-bin-debug каталоги. Затем запустите службу, введя, `service.exe` а затем вызвать Client.exe с начальной стоимостью тиков, пройдено в качестве входиного аргумента. Ниже показаны результаты выполнения для количества тактов, равного 10.  
  
```console  
Prompt>Service.exe  
ServiceHost Started. Press Enter to terminate service.  
Ping: Ticks = 10  
Ping: Ticks = 8  
Ping: Ticks = 6  
Ping: Ticks = 4  
Ping: Ticks = 2  
Ping: Ticks = 0  
  
Prompt>Client.exe 10  
Pong: Ticks = 9  
Pong: Ticks = 7  
Pong: Ticks = 5  
Pong: Ticks = 3  
Pong: Ticks = 1  
```  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Reentrant`  
