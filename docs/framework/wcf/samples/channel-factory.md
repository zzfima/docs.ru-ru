---
title: Фабрика каналов
ms.date: 03/30/2017
ms.assetid: 09b53aa1-b13c-476c-a461-e82fcacd2a8b
ms.openlocfilehash: eac315cf88b2ecc7471f194ef6c3be902b3ccbaa
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716043"
---
# <a name="channel-factory"></a>Фабрика каналов

В этом образце показано, как клиентское приложение может создать канал с помощью <xref:System.ServiceModel.ChannelFactory>, вместо использования созданного клиента. Этот образец основан на [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md) , который реализует службу калькулятора.

> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.

Чтобы создать канал для конечной точки службы, в этом образце используется класс <xref:System.ServiceModel.ChannelFactory%601>. Как правило, для создания канала к конечной точке службы создается тип клиента с помощью [средства служебной программы метаданных ServiceModel (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) и создается экземпляр созданного типа. Кроме того, канал можно создать с помощью класса <xref:System.ServiceModel.ChannelFactory%601>, как показано в этом образце. Служба, созданная с помощью следующего примера кода, идентична службе в [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md).

```csharp
EndpointAddress address = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");
WSHttpBinding binding = new WSHttpBinding();
ChannelFactory<ICalculator> factory = new
                    ChannelFactory<ICalculator>(binding, address);
ICalculator channel = factory.CreateChannel();
```

> [!IMPORTANT]
> Если этот образец выполняется на нескольких компьютерах, в предыдущем фрагменте кода необходимо заменить localhost на полное имя компьютера, на котором выполняется служба. В этом образце для задания адреса конечной точки конфигурация не используется, поэтому это необходимо сделать в коде.

После создания канала можно вызывать операции службы, как это можно было бы делать с помощью созданного клиента.

```csharp
// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = channel.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
```

Чтобы закрыть канал, его необходимо сначала привести к интерфейсу <xref:System.ServiceModel.IClientChannel>. Это связано с тем, что канал обычно объявляется в клиентском приложении с помощью интерфейса `ICalculator`, имеющего методы `Add` и `Subtract`, но не имеющего метода `Close`. Метод `Close` наследуется от интерфейса <xref:System.ServiceModel.ICommunicationObject>.

```csharp
// Close the channel.
 ((IClientChannel)client).Close();
```

При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. Чтобы закрыть клиентское приложение, нажмите клавишу ВВОД в окне клиента.

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца

1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md). Обратите внимание, что этот в этом образце не включается публикация метаданных. Чтобы заново создать тип клиента, необходимо включить в образце публикацию метаданных.

3. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).

### <a name="to-run-the-sample-cross-machine"></a>Запуск образца на нескольких компьютерах

1. В следующем фрагменте кода замените localhost на полное имя компьютера, на котором выполняется служба.

    ```csharp
    EndpointAddress address = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");
    ```

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\ChannelFactory`
