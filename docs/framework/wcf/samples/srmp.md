---
title: SRMP
ms.date: 03/30/2017
ms.assetid: cf37078c-dcb4-45e0-acaf-2f196521b226
ms.openlocfilehash: 51b0e0513ba20bf7aeae461dee6ac864f1d55897
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73417098"
---
# <a name="srmp"></a>SRMP
В этом образце показано, как осуществлять транзакционное взаимодействие с использованием очередей с помощью очереди сообщений (MSMQ) по HTTP.  
  
 При использовании очередей клиент взаимодействует со службой посредством очереди. Конкретно, клиент отправляет сообщения в очередь. Служба получает сообщения из очереди. Поэтому клиенту и службе не обязательно выполняться одновременно, чтобы взаимодействовать посредством очереди.  
  
 MSMQ обеспечивает использование HTTP (включая HTTPS) для отправки сообщений в очередь. В этом примере демонстрируется использование взаимодействия в очереди Windows Communication Foundation (WCF) и отправка сообщений по протоколу HTTP. MSMQ использует протокол под названием SRMP, являющийся протоколом на основе SOAP для взаимодействия по HTTP.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
4. Перед запуском примера в окне " **Установка и удаление компонентов Windows**" убедитесь, что служба MSMQ установлена с поддержкой HTTP. При установке поддержки HTTP автоматически устанавливаются службы IIS и в них добавляется поддержка протокола для MSMQ.  
  
5. Чтобы гарантировать использование HTTP для взаимодействия, можно включить ужесточенный режим MSMQ. Это позволит предотвратить получение сообщений в любую очередь, размещенную на компьютере, посредством транспорта, отличного от HTTP.  
  
6. После выбора ужесточенного режима MSMQ требуется перезагрузка компьютера с ОС [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].  
  
7. Запустите службу.  
  
8. Запустите клиент. Измените адрес конечной точки клиента, указав имя компьютера или IP-адрес вместо "localhost". Клиент отправляет сообщение, и выполняется выход.  
  
## <a name="requirements"></a>Требования  
 Чтобы запустить этот образец, кроме MSMQ на компьютерах службы и клиента должны быть установлены службы IIS.  
  
## <a name="demonstrates"></a>Демонстрации  
 В примере демонстрируется отправка сообщений в очереди WCF с помощью MSMQ по протоколу HTTP. Это также называется обменом сообщениями SRMP. Когда отправляется сообщение в очереди, MSMQ на отправляющем компьютере передает сообщения диспетчеру принимающей очереди по транспорту TCP или HTTP. Закрывая SRMP, пользователь указывает, что HTTP должен использоваться в качестве транспорта для передачи очередей. Безопасный SRMP (SRMP Secure) обеспечивает использование HTTPS.  
  
## <a name="example"></a>Пример  
 Образец кода основан на образце с транзакциями. Отправка сообщения в очередь и его получение из нее с помощью SRMP аналогичны отправке и получению сообщений с помощью собственного протокола.  
  
 Конфигурация клиента изменяется, что указать выбранный протокол передачи между очередями. Протокол передачи между очередями может быть собственным, SRMP или SrmpSecure. По умолчанию используется собственный протокол. В этом примере в конфигурации клиента и службы отмечено использование SRMP.  
  
 Существуют некоторые ограничения SRMP в отношении безопасности транспорта. Для безопасности транспорта MSMQ по умолчанию необходима Active Directory, требующая, чтобы диспетчер передающей и принимающей очереди находились в одном и том же домене Windows. Это невозможно при отправке сообщений по HTTP. По существу, безопасность транспорта по умолчанию не работает. Для безопасности транспорта необходимо задать "Certificate" (Сертификат), если она необходима. Для защиты сообщений можно также использовать безопасность сообщений. В этом образце безопасность транспорта и сообщений отключена, чтобы продемонстрировать обмен сообщениями SRMP.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  
  <system.serviceModel>  
  
    <client>  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint name="OrderProcessorEndpoint"  
           address=  
          "net.msmq://localhost/private/ServiceModelSamplesSrmp"   
           bindingConfiguration="srmpBinding"   
           binding="netMsmqBinding"   
           contract="IOrderProcessor" />  
    </client>  
    <bindings>  
      <netMsmqBinding>  
        <binding name="srmpBinding"  
                 queueTransferProtocol="Srmp">  
          <security mode="None" />  
        </binding>  
      </netMsmqBinding>  
    </bindings>  
  </system.serviceModel>  
  
</configuration>  
```  
  
 Этот код будет приводить к следующему результату.  
  
```console  
Processing Purchase Order: 556b70be-31ee-4a3b-8df4-ed5e538015a4   
Customer: somecustomer.com   
OrderDetails   
    Order LineItem: 54 of Blue Widget @unit price: $29.99   
    Order LineItem: 890 of Red Widget @unit price: $45.89   
    Total cost of this order: $42461.56   
    Order status: Pending  
```  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\SRMP`  
