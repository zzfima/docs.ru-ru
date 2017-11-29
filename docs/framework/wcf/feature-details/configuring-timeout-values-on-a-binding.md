---
title: "Настройка значений времени ожидания для привязки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5c825a2-b48f-444a-8659-61751ff11d34
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 458f2143021ac40bfcaddbe957113e400bd5f3c5
ms.sourcegitcommit: 5d0e069655439984862a835f400058b7e8bbadc6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2017
---
# <a name="configuring-timeout-values-on-a-binding"></a>Настройка значений времени ожидания для привязки
Существует ряд настроек параметров времени ожидания, доступных в привязках WCF. Правильная установка этих параметров времени ожидания может не только повысить производительность службы, но и внести вклад в удобство использования и безопасность службы. Доступны следующие значения времени ожидания для привязок WCF.  
  
1.  OpenTimeout  
  
2.  CloseTimeout  
  
3.  SendTimeout  
  
4.  ReceiveTimeout  
  
## <a name="wcf-binding-timeouts"></a>Время ожидания привязок WCF  
 Каждый из параметров, описанный в этом разделе, применяется к самой привязке, в коде или в конфигурации. В следующем примере кода показано, как программно задать время ожидания для привязки WCF в контексте резидентной службы.  
  
```csharp  
public static void Main()
{
    Uri baseAddress = new Uri("http://localhost/MyServer/MyService");
    
    try
    {
        ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService));
        
        WSHttpBinding binding = new WSHttpBinding();
        binding.OpenTimeout = new TimeSpan(0, 10, 0);
        binding.CloseTimeout = new TimeSpan(0, 10, 0);
        binding.SendTimeout = new TimeSpan(0, 10, 0);
        binding.ReceiveTimeout = new TimeSpan(0, 10, 0);
        
        serviceHost.AddServiceEndpoint("ICalculator", binding, baseAddress);
        serviceHost.Open();
        
        // The service can now be accessed.
        Console.WriteLine("The service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();
    }
    catch (CommunicationException ex)
    {
        // Handle exception ...
    }
}
```  
  
 В следующем примере показано, как настроить время ожидания привязки в файле конфигурации приложения.  
  
```xml  
<configuration>
  <system.serviceModel>
    <bindings>
      <wsHttpBinding>
        <binding openTimeout="00:10:00" 
                 closeTimeout="00:10:00" 
                 sendTimeout="00:10:00" 
                 receiveTimeout="00:10:00">
        </binding>
      </wsHttpBinding>
    </bindings>
  </system.serviceModel>
</configuration>
```  
  
 Дополнительные сведения об этих параметрах можно найти в документации по классу <xref:System.ServiceModel.Channels.Binding>.  
  
### <a name="client-side-timeouts"></a>Время ожидания на стороне клиента  
 На стороне клиента:  
  
1.  Значение SendTimeout используется для инициализации значения OperationTimeout, которое управляет всем процессом отправки сообщения, включая получение ответного сообщения для операции службы типа «запрос-ответ». Это время ожидания применяется также при отправке ответного сообщения из метода обратного вызова контракта.  
  
2.  Значение OpenTimeout используется при открытии каналов, если для этого процесса не указано явное значение времени ожидания.  
  
3.  Значение CloseTimeout используется при закрытии каналов, если для этого процесса не указано явное значение времени ожидания.  
  
4.  Значение ReceiveTimeout не используется.  
  
### <a name="service-side-timeouts"></a>Время ожидания на стороне службы  
 На стороне службы:  
  
1.  Значения времени ожидания SendTimeout, OpentTimeout, CloseTimeout такие же, как и на стороне клиента  
  
2.  Значение ReceiveTimeout используется на уровне платформы службы для инициализации времени ожидания бездействующего сеанса. Это время ожидания определяет, как долго сеанс может находиться в бездействии до истечения времени ожидания.
