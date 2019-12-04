---
title: Неустойчивое взаимодействие с использованием очереди
ms.date: 03/30/2017
ms.assetid: 0d012f64-51c7-41d0-8e18-c756f658ee3d
ms.openlocfilehash: 8ed10262d319664d404e6beb630593cb93748a7d
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715279"
---
# <a name="volatile-queued-communication"></a>Неустойчивое взаимодействие с использованием очереди

В этом образце показано, как осуществлять неустойчивое взаимодействие с использованием очередей с помощью транспорта очереди сообщений (MSMQ). В этом образце используется привязка <xref:System.ServiceModel.NetMsmqBinding>. В данном случае служба представляет собой резидентное консольное приложение, позволяющее наблюдать за тем, как служба получает сообщения из очереди.

> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.

При использовании очередей клиент взаимодействует со службой посредством очереди. Конкретно, клиент отправляет сообщения в очередь. Служба получает сообщения из очереди. Поэтому клиенту и службе не обязательно выполняться одновременно, чтобы взаимодействовать посредством очереди.

При отправке сообщения без подтверждения MSMQ лишь делает все возможно для отправки сообщения в отличие от подтверждений "ровно один раз", при которых MSMQ проверяет, что сообщение было доставлено, или, если доставить его не удалось, уведомляет об этом.

В некоторых сценариях неустойчивое сообщение может быть отправлено через очередь без подтверждения, если своевременность доставки важнее, чем возможная потеря сообщения. Неустойчивые сообщения не сохраняются в случае сбоя диспетчера очереди. Поэтому при сбое диспетчера очереди нетранзакционная очередь, в которой содержатся неустойчивые сообщения, сохраняется, но сами сообщения исчезают, поскольку они не хранятся на диске.

> [!NOTE]
> Неустойчивые сообщения невозможно отправлять с помощью MSMQ без подтверждений в пределах области транзакции. Кроме того, для отправки неустойчивых сообщений необходимо создавать нетранзакционные очереди.

В этом образце используется контракт службы `IStockTicker`, определяющий односторонние службы, которые лучше всего подходят для работы с очередями.

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
public interface IStockTicker
{
    [OperationContract(IsOneWay = true)]
    void StockTick(string symbol, float price);
}
```

Операция службы отображает биржевой символ и цену, как показано в следующем образце кода:

```csharp
public class StockTickerService : IStockTicker
{
    public void StockTick(string symbol, float price)
    {
        Console.WriteLine("Stock Tick {0}:{1} ", symbol, price);
     }
     …
}
```

Служба является резидентной. При работе с транспортом MSMQ используемую очередь следует создавать заранее. Это можно сделать вручную или с помощью кода. В данном образце служба содержит код для проверки наличия очереди и ее создания, если это необходимо. Имя очереди считывается из файла конфигурации. Базовый адрес используется [средством служебной программы метаданных ServiceModel (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания учетной записи-посредника для службы.

```csharp
// Host the service within this EXE console application.
public static void Main()
{
    // Get MSMQ queue name from app settings in configuration.
    string queueName = ConfigurationManager.AppSettings["queueName"];

    // Create the transacted MSMQ queue if necessary.
    if (!MessageQueue.Exists(queueName))
        MessageQueue.Create(queueName);

    // Create a ServiceHost for the StockTickerService type.
    using (ServiceHost serviceHost = new ServiceHost(typeof(StockTickerService)))
    {
        // Open the ServiceHost to create listeners and start listening for messages.
        serviceHost.Open();

        // The service can now be accessed.
        Console.WriteLine("The service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();

        // Close the ServiceHost to shutdown the service.
        serviceHost.Close();
    }
}
```

Имя очереди MSMQ задается в разделе appSettings файла конфигурации. Конечная точка для службы задается в разделе system.serviceModel файла конфигурации и определяет привязку `netMsmqBinding`.

> [!NOTE]
> В имени очереди для определения локального компьютера используется точка (.), а при создании очереди с помощью <xref:System.Messaging> в пути в качестве разделителей используются символы обратной косой черты. Адрес конечной точки Windows Communication Foundation (WCF) указывает схему "net. msmq:", использует "localhost" для локального компьютера и косую черту в пути.

Подтверждения устойчивости или неустойчивости сообщений также задаются в конфигурации.

```xml
<appSettings>
  <!-- use appSetting to configure MSMQ queue name -->
  <add key="queueName" value=".\private$\ServiceModelSamplesVolatile" />
</appSettings>

<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.StockTickerService"
             behaviorConfiguration="CalculatorServiceBehavior">
    ...
      <!-- Define NetMsmqEndpoint -->
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesVolatile"
                binding="netMsmqBinding"
                bindingConfiguration="volatileBinding"
                contract="Microsoft.ServiceModel.Samples.IStockTicker" />
    ...
    </service>
  </services>

  <bindings>
    <netMsmqBinding>
      <binding name="volatileBinding"
             durable="false"
           exactlyOnce="false"/>
    </netMsmqBinding>
  </bindings>
  ...
</system.serviceModel>
```

Поскольку в этом образце поддерживающие очередь сообщения отправляются с помощью нетранзакционной очереди, передавать через эту очередь сообщения транзакций невозможно.

```csharp
// Create a client.
Random r = new Random(137);

StockTickerClient client = new StockTickerClient();

float price = 43.23F;
for (int i = 0; i < 10; i++)
{
    float increment = 0.01f * (r.Next(10));
    client.StockTick("zzz" + i, price + increment);
}

//Closing the client gracefully cleans up resources.
client.Close();
```

При выполнении образца действия клиента и службы отображаются в окнах консоли как службы, так и клиента. Можно видеть, как служба получает сообщения от клиента. Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент. Обратите внимание, что поскольку используется очередь, клиенту и службе не обязательно быть запущенными и работать одновременно. Можно запустить клиент, выключить его, а затем запустить службу, которая все равно получит сообщения клиента.

```console
The service is ready.
Press <ENTER> to terminate service.

Stock Tick zzz0:43.25
Stock Tick zzz1:43.23
Stock Tick zzz2:43.28
Stock Tick zzz3:43.3
Stock Tick zzz4:43.23
Stock Tick zzz5:43.25
Stock Tick zzz6:43.25
Stock Tick zzz7:43.24
Stock Tick zzz8:43.32
Stock Tick zzz9:43.3
```

### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца

1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).

3. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).

По умолчанию с привязкой <xref:System.ServiceModel.NetMsmqBinding> безопасность транспорта включена. Существует два соответствующих свойства безопасности транспорта MSMQ, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> и <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` по умолчанию устанавливается режим проверки подлинности `Windows`, а для уровня защиты устанавливается значение `Sign`. Чтобы служба MSMQ обеспечивала возможности проверки подлинности и подписывания, она должна входить в домен, а также должна быть установлена возможность интеграции MSMQ со службой каталогов Active Directory. Если запустить данный образец на компьютере, который не удовлетворяет этому условию, возникнет ошибка.

### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a>Запуск образца на компьютере, входящем в рабочую группу, или без интеграции с Active Directory

1. Если компьютер не входит в домен или не установлена интеграция с Active Directory, отключите безопасность транспорта, задав для режима проверки подлинности и уровня защиты значения `None`, как показано в следующем образце кода конфигурации:

    ```xml
    <system.serviceModel>
        <services>
          <service name="Microsoft.ServiceModel.Samples.StockTickerService"
                   behaviorConfiguration="StockTickerServiceBehavior">
            <host>
              <baseAddresses>
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
              </baseAddresses>
            </host>

            <!-- Define NetMsmqEndpoint -->
            <endpoint address="net.msmq://localhost/private/ServiceModelSamplesVolatile"
                      binding="netMsmqBinding"
                      bindingConfiguration="volatileBinding"
                      contract="Microsoft.ServiceModel.Samples.IStockTicker" />
            <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
            <endpoint address="mex"
                      binding="mexHttpBinding"
                      contract="IMetadataExchange" />

          </service>
        </services>

        <bindings>
          <netMsmqBinding>
            <binding name="volatileBinding"
                  durable="false"
                  exactlyOnce="false">
              <security mode="None" />
            </binding>
          </netMsmqBinding>
        </bindings>

        <behaviors>
          <serviceBehaviors>
            <behavior name="StockTickerServiceBehavior">
              <serviceMetadata httpGetEnabled="True"/>
            </behavior>
          </serviceBehaviors>
        </behaviors>

      </system.serviceModel>
    ```

2. Перед выполнением примера убедитесь, что изменена конфигурация как сервера, так и клиента.

    > [!NOTE]
    > Задание для `security mode` значения `None` эквивалентно заданию для параметров безопасности <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> и `Message` значения `None`.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Volatile`
