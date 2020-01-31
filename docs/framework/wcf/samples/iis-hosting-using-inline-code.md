---
title: Размещение в службах IIS с использованием встроенного кода
ms.date: 03/30/2017
helpviewer_keywords:
- Web hosted service
- IIS Hosting Using Inline Code Sample [Windows Communication Foundation]
ms.assetid: 56fe3687-a34b-4661-8e30-b33770f413fa
ms.openlocfilehash: 304da4fa7d2bb48899cdec864fb2dc1f9fdfb9ef
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746433"
---
# <a name="iis-hosting-using-inline-code"></a>Размещение в службах IIS с использованием встроенного кода

Этот образец демонстрирует реализацию службы, размещенной в службах IIS, когда код службы находится в строках файла SVC и компилируется по требованию. Код службы может также быть реализован непосредственно в файлах исходного кода, расположенных в каталоге \App_Code приложения, или он может быть скомпилирован в сборку, развернутую в каталоге \bin. В этом примере такие приемы не демонстрируются.

> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\InlineCode`

В этом примере показана типичная служба, которая реализует контракт, определяющий шаблон взаимодействия "запрос-ответ". Служба размещается в службах IIS, а весь код службы полностью содержится в файле Service.svc. Служба активируется ведущим приложением и компилируется по требованию при поступлении первого сообщения, отправленного этой службе. Предварительная компиляция не требуется. Служба реализует контракт `ICalculator`, как показано в следующем примере кода:

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
    public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    [OperationContract]
    double Subtract(double n1, double n2);
    [OperationContract]
    double Multiply(double n1, double n2);
    [OperationContract]
    double Divide(double n1, double n2);
}
```

Реализация службы выполняет вычисления и возвращает соответствующий результат.

`<%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService" %>`

```csharp
// Service class that implements the service contract.
public class CalculatorService : ICalculator
{
    public double Add(double n1, double n2)
    {
        return n1 + n2;
    }
    public double Subtract(double n1, double n2)
    {
        return n1 - n2;
    }
    public double Multiply(double n1, double n2)
    {
        return n1 * n2;
    }
    public double Divide(double n1, double n2)
    {
        return n1 / n2;
    }
}
```

При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца

1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).

3. После построения решения запустите программу Setup. bat, чтобы настроить приложение ServiceModelSamples в IIS 7,0. Теперь каталог ServiceModelSamples должен отображаться как приложение IIS 7,0.

4. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md). Пример создания клиентского приложения, который может вызывать эту службу, см. в разделе [как создать клиент](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).

## <a name="see-also"></a>См. также:

- [Примеры размещения и сохраняемости AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))
