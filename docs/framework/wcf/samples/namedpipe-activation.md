---
title: Активация NamedPipe
ms.date: 03/30/2017
ms.assetid: f3c0437d-006c-442e-bfb0-6b29216e4e29
ms.openlocfilehash: 78073ca222cab07bbc9cee5c1976cf7a6ee46295
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714696"
---
# <a name="namedpipe-activation"></a>Активация NamedPipe

Этот пример демонстрирует размещение службы, которая использует службу активации Windows (WAS), чтобы активировать службу, которая взаимодействует через именованные каналы. Этот образец основан на [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md) и требует [!INCLUDE[wv](../../../../includes/wv-md.md)] для запуска.

> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WASHost\NamedPipeActivation`

## <a name="sample-details"></a>Подробные сведения об образце

Пример содержит консольную программу клиента (EXE) и библиотеку службы (DLL), размещаемую в рабочем процессе, активируемом службой активации процесса Windows (WAS). Действия клиента отображаются в окне консоли.

Служба реализует контракт, определяющий шаблон взаимодействия "запрос-ответ". Контракт определяется интерфейсом `ICalculator`, который предоставляет математические операции (сложить, вычесть, умножить и разделить), как это показано ниже в образце кода.

```csharp
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

Клиент осуществляет синхронные вызовы заданной математической операции, а реализация службы вычисляет и возвращает соответствующий результат.

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

Образец использует изменяемую привязку `netNamedPipeBinding` без использования безопасности. Привязка задается в файлах конфигурации для клиента и службы. Тип привязки для службы задается в атрибуте `binding` элемента конечной точки, как показано в следующем образце конфигурации.

Если требуется использовать безопасную привязку именованного канала, измените настройку режима безопасности для требуемого параметра безопасности и снова запустите svcutil.exe на клиенте, чтобы получить обновленный файл конфигурации клиента.

```xml
<system.serviceModel>
        <services>
            <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">

        <!-- This endpoint is exposed at the base address provided by host: net.pipe://localhost/servicemodelsamples/service.svc  -->
        <endpoint address=""
                  binding="netNamedPipeBinding"
                  bindingConfiguration="Binding1"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- the mex endpoint is exposed at net.pipe://localhost/servicemodelsamples/service.svc/mex -->
        <endpoint address="mex"
                  binding="mexNamedPipeBinding"
                  contract="IMetadataExchange" />
      </service>
        </services>
        <bindings>
            <netNamedPipeBinding>
                <binding name="Binding1" >
                    <security mode = "None">
                    </security>
                </binding >
            </netNamedPipeBinding>
        </bindings>

    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceMetadata />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>

  </system.serviceModel>
```

Информация конечной точки клиента настраивается, как показано в следующем образце кода.

```xml
<system.serviceModel>

    <client>
      <endpoint name=""
                          address="net.pipe://localhost/servicemodelsamples/service.svc"
                          binding="netNamedPipeBinding"
                          bindingConfiguration="Binding1"
                          contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </client>

    <bindings>

      <!--  Following is the expanded configuration section for a NetNamedPipeBinding.
            Each property is configured with the default value. -->

      <netNamedPipeBinding>
        <binding name="Binding1"
                         maxBufferSize="65536"
                         maxConnections="10">
          <security mode = "None">
          </security>
        </binding >

      </netNamedPipeBinding>
    </bindings>

  </system.serviceModel>
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

1. Убедитесь, что установлен сервер IIS 7,0. Для активации WAS требуется IIS 7,0.

2. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

    Кроме того, необходимо установить компоненты активации WCF, отличные от HTTP:

    1. В меню **Пуск** выберите **Панель управления**.

    2. Выберите **программы и компоненты**.

    3. Щелкните **Включение или отключение компонентов Windows**.

    4. Разверните узел **Microsoft .NET Framework 3,0** и установите флажок **Windows Communication Foundation активации, отличной от HTTP** .

3. Настройка службы активации Windows (WAS) для поддержки активации именованных каналов.

    Для удобства два нижеописанных действия выполняются в пакетном файле AddNetPipeSiteBinding.cmd, расположенном в каталоге с примерами.

    1. Чтобы поддерживать активацию по net.pipe, веб-узел по умолчанию должен прежде быть привязан к протоколу net.pipe. Сделать это позволяет файл Appcmd.exe, который устанавливается с помощью набора инструментов управления IIS 7.0. В командной строке с повышенными привилегиями (с правами администратора) выполните следующую команду.

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        -+bindings.[protocol='net.pipe',bindingInformation='*']
        ```

        > [!NOTE]
        > Эта команда представляет собой одну строку текста.

        Эта команда добавит для веб-сайта по умолчанию привязку сайта к протоколу net.pipe.

    2. Несмотря на то что все приложения в узле имеют общую привязку к протоколу net.pipe, включать поддержку net.pipe можно для каждого приложения отдельно. Чтобы включить протокол net.pipe для приложения /servicemodelsamples, необходимо выполнить следующую команду из командной строки с повышенными привилегиями.

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http,net.pipe
        ```

        > [!NOTE]
        > Эта команда представляет собой одну строку текста.

        Эта команда позволяет получить доступ к приложению/сервицемоделсамплес, используя как `http://localhost/servicemodelsamples`, так `net.tcp://localhost/servicemodelsamples`.

4. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).

5. Удалите привязку узла к протоколу net.pipe, добавленную ранее для этого образца.

    Для удобства выполняются два следующих действия в пакетном файле RemoveNetPipeSiteBinding.cmd, расположенном в каталоге с образцами.

    1. Удалите протокол net.tcp из списка включенных протоколов, выполнив следующую команду из командной строки с повышенными привилегиями.

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http
        ```

        > [!NOTE]
        > Эта команда вводится как одна строка текста.

    2. Удалите привязку узла к протоколу net.tcp, выполнив следующую команду из командной строки с повышенными привилегиями.

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" --bindings.[protocol='net.pipe',bindingInformation='*']
        ```

        > [!NOTE]
        > Эта команда должна вводиться как одна строка текста.

## <a name="see-also"></a>См. также:

- [Примеры размещения и сохраняемости AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))
