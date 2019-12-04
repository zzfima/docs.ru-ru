---
title: Пример для начала работы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- basic samples [WCF], getting started
ms.assetid: 967a3d94-0261-49ff-b85a-20bb07f1af20
ms.openlocfilehash: 3282daff166a8fe56841a41bfe8bd9dd69f9d4c8
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716940"
---
# <a name="getting-started-sample"></a>Пример для начала работы

В начало работы примере демонстрируется реализация типичной службы и стандартного клиента с помощью Windows Communication Foundation (WCF). Этот образец является основой для всех остальных базовых образцов технологий.

> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\GettingStarted\GettingStarted`

Служба описывает операции, выполняемые ею в контракте службы, который она открыто предоставляет как метаданные. Служба также содержит код для реализации операций.

Клиент содержит определение контракта службы и прокси-класс для доступа к службе. Код прокси-сервера создается на основе метаданных службы с помощью [средства служебной программы метаданных ServiceModel (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).

В [!INCLUDE[wv](../../../../includes/wv-md.md)] служба размещается в службе активации Windows (WAS). В [!INCLUDE[wxp](../../../../includes/wxp-md.md)] и [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] она размещается в службах IIS и ASP.NET. Размещение службы в IIS или WAS позволяет активировать службу автоматически при первом доступе к ней.

> [!NOTE]
> Если вы предпочитаете приступить к работе с примером, в котором размещена служба, в консольном приложении, а не IIS, см. пример с помощью [узла для самостоятельного размещения](../../../../docs/framework/wcf/samples/self-host.md) .

Служба и клиент указывают данные для доступа в параметрах файла конфигурации, что обеспечивает гибкость при развертывании. Эти данные включают определение конечной точки, задающей адрес, привязку и контракт. Привязка определяет транспорт и детали обеспечения безопасности, касающиеся доступа к службе.

Служба настраивает среду выполнения на публикацию ее метаданных.

Служба реализует контракт, определяющий шаблон взаимодействия "запрос-ответ". Контракт определяется интерфейсом `ICalculator`, который предоставляет математические операции (сложение, вычитание, умножение и деление). Клиент осуществляет вызовы заданной математической операции, а служба отправляет в ответ результат. Служба реализует контракт `ICalculator`, определенный в следующем коде.

```vb
' Define a service contract.
    <ServiceContract(Namespace:="http://Microsoft.Samples.GettingStarted")>
     Public Interface ICalculator
        <OperationContract()>
        Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()>
        Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()>
        Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()>
        Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double
    End Interface
```

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

Реализация службы вычисляет и возвращает соответствующий результат, как показано в следующем примере кода.

```vb
' Service class which implements the service contract.
Public Class CalculatorService
Implements ICalculator
Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add
Return n1 + n2
End Function

Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract
Return n1 - n2
End Function

Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply
Return n1 * n2
End Function

Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide
Return n1 / n2
End Function
End Class
```

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

Служба предоставляет конечную точку для взаимодействия с ней; конечная точка определяется в файле конфигурации (Web.config). См. следующий образец конфигурации.

```xaml
<services>
    <service
        name="Microsoft.ServiceModel.Samples.CalculatorService"
        behaviorConfiguration="CalculatorServiceBehavior">
        <!-- ICalculator is exposed at the base address provided by
         host: http://localhost/servicemodelsamples/service.svc.  -->
       <endpoint address=""
              binding="wsHttpBinding"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />
       ...
    </service>
</services>
```

Служба предоставляет конечную точку по базовому адресу, который предоставляется узлом IIS или WAS. Привязка настраивается с использованием стандартного объекта <xref:System.ServiceModel.WSHttpBinding>, обеспечивающего взаимодействие по протоколу HTTP и стандартному протоколу веб-служб для адресации и безопасности. Контрактом является интерфейс `ICalculator`, реализуемый службой.

Как настроено, доступ к службе можно получить на `http://localhost/servicemodelsamples/service.svc` клиентом на том же компьютере. Чтобы к службе могли получить доступ клиенты на удаленных компьютерах, вместо имени localhost необходимо указать полное имя домена.

По умолчанию платформа не предоставляет никаких метаданных. Таким образом, служба включает <xref:System.ServiceModel.Description.ServiceMetadataBehavior> и предоставляет конечную точку обмена метаданными (MEX) на `http://localhost/servicemodelsamples/service.svc/mex`. Это демонстрируется в следующей конфигурации.

```xaml
<system.serviceModel>
  <services>
    <service
        name="Microsoft.ServiceModel.Samples.CalculatorService"
        behaviorConfiguration="CalculatorServiceBehavior">
      ...
      <!-- the mex endpoint is exposed at
       http://localhost/servicemodelsamples/service.svc/mex -->
      <endpoint address="mex"
                binding="mexHttpBinding"
                contract="IMetadataExchange" />
    </service>
  </services>

  <!--For debugging purposes set the includeExceptionDetailInFaults
   attribute to true-->
  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceMetadata httpGetEnabled="True"/>
        <serviceDebug includeExceptionDetailInFaults="False" />
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```

Клиент обменивается данными с использованием заданного типа контракта с помощью клиентского класса, созданного [средством служебной программы метаданных ServiceModel (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Этот созданный клиент содержится в файлах generatedClient.cs или generatedClient.vb. Это средство извлекает метаданные для заданной службы и создает клиент, который будет использоваться клиентским приложением для взаимодействия по заданному контракту. Размещенная служба должна быть доступна для создания кода клиента, поскольку служба используется для извлечения обновленных метаданных.

 Чтобы создать типизированный прокси, выполните следующую команду из командной строки SDK в каталоге клиента.

```console
svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs
```

Чтобы создать клиент на языке Visual Basic, введите следующую команду в командной строке SDK.

`Svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb`

С помощью созданного клиента можно получить доступ к заданной конечной точке службы, настроив соответствующий адрес и привязку. Как и служба, клиент использует файл конфигурации (App.config), чтобы задать конечную точку для взаимодействия. Конфигурация конечной точки клиента состоит из абсолютного адреса конечной точки службы, привязки и контракта, как показано в следующем примере.

```xaml
<client>
     <endpoint
         address="http://localhost/servicemodelsamples/service.svc"
         binding="wsHttpBinding"
         contract=" Microsoft.ServiceModel.Samples.ICalculator" />
</client>
```

Реализация клиента создает клиент и использует интерфейс, чтобы начать взаимодействие со службой, как показано в следующем примере кода.

```vb
' Create a client
Dim client As New CalculatorClient()

' Call the Add service operation.
            Dim value1 = 100.0R
            Dim value2 = 15.99R
            Dim result = client.Add(value1, value2)
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)

' Call the Subtract service operation.
value1 = 145.00R
value2 = 76.54R
result = client.Subtract(value1, value2)
Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)

' Call the Multiply service operation.
value1 = 9.00R
value2 = 81.25R
result = client.Multiply(value1, value2)
Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)

' Call the Divide service operation.
value1 = 22.00R
value2 = 7.00R
result = client.Divide(value1, value2)
Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)

'Closing the client gracefully closes the connection and cleans up resources
```

```csharp
// Create a client.
CalculatorClient client = new CalculatorClient();

// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = client.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

// Call the Subtract service operation.
value1 = 145.00D;
value2 = 76.54D;
result = client.Subtract(value1, value2);
Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

// Call the Multiply service operation.
value1 = 9.00D;
value2 = 81.25D;
result = client.Multiply(value1, value2);
Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

// Call the Divide service operation.
value1 = 22.00D;
value2 = 7.00D;
result = client.Divide(value1, value2);
Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);

//Closing the client releases all communication resources.
client.Close();
```

При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.

```output
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

В образце "Начало работы" показан стандартный способ создания службы и клиента. Другой [базовый](../../../../docs/framework/wcf/samples/basic-sample.md) пример сборки этого образца для демонстрации конкретных функций продукта.

### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца

1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).

3. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).

## <a name="see-also"></a>См. также:

- [Практическое руководство. Размещение службы WCF в управляемом приложении](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)
- [Практическое руководство. Размещение службы WCF в IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)
