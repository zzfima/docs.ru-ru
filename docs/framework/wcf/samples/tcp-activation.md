---
title: Активация TCP
ms.date: 03/30/2017
ms.assetid: bf8c215c-0228-4f4f-85c2-e33794ec09a7
ms.openlocfilehash: c1a2c0de5fbb666ec3b68ec3da31cc27f8234cbd
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716600"
---
# <a name="tcp-activation"></a>Активация TCP

Этот образец демонстрирует размещение службы, использующей службу активации Windows (WAS) для активации службы, которая осуществляет взаимодействие по протоколу net.tcp. Этот образец основан на [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md).

> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WASHost\TCPActivation`

Пример содержит консольную программу клиента (EXE) и библиотеку службы (DLL), размещаемую в рабочем процессе, активируемом службой WAS. Действия клиента отображаются в окне консоли.

Служба реализует контракт, определяющий шаблон взаимодействия "запрос-ответ". Контракт определяется интерфейсом `ICalculator`, который предоставляет математические операции (сложение, вычитание, умножение и деление), как показано ниже в образце кода:

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

Реализация службы выполняет вычисления и возвращает соответствующий результат:

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

В этом образце используется вариант привязки net.tcp с включенным совместным использованием порта TCP и отключенным механизмом безопасности. Если требуется использовать безопасную привязку TCP, измените режим безопасности сервера на требуемое значение и снова запустите svcutil.exe на клиенте, чтобы получить обновленный файл конфигурации клиента.

В следующем образце показана конфигурация для службы:

```xml
<system.serviceModel>

    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <!-- This endpoint is exposed at the base address provided by host: net.tcp://localhost/servicemodelsamples/service.svc  -->
        <endpoint binding="netTcpBinding" bindingConfiguration="PortSharingBinding"
          contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- the mex endpoint is exposed at net.tcp://localhost/servicemodelsamples/service.svc/mex -->
        <endpoint address="mex"
                  binding="mexTcpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <bindings>
      <netTcpBinding>
        <binding name="PortSharingBinding" portSharingEnabled="true">
          <security mode="None" />
        </binding>
      </netTcpBinding>
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

Конечная точка клиента настраивается так, как показано в следующем образце кода:

```xml
<system.serviceModel>
    <bindings>
        <netTcpBinding>
          <binding name="NetTcpBinding_ICalculator">
            <security mode="None"/>
          </binding>
        </netTcpBinding>
    </bindings>
    <client>
        <endpoint address="net.tcp://localhost/servicemodelsamples/service.svc"
            binding="netTcpBinding" bindingConfiguration="NetTcpBinding_ICalculator"
            contract="Microsoft.ServiceModel.Samples.ICalculator" name="NetTcpBinding_ICalculator" />
    </client>
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

3. Настройте службу WAS на поддержку активации по протоколу TCP.

    Для удобства два нижеописанных действия выполняются в пакетом файле AddNetTcpSiteBinding.cmd, расположенном в каталоге с образцами.

    1. Для поддержки активации по net.tcp веб-узел по умолчанию необходимо сначала привязать к порту net.tcp. Сделать это позволяет программа Appcmd.exe, которая устанавливается с набором инструментов управления IIS 7.0. В командной строке с правами администратора выполните следующую команду:

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']
        ```

        > [!TIP]
        > Эта команда представляет собой одну строку текста. Она добавляет привязку сайта к протоколу net.tcp в веб-сайт по умолчанию, ожидающий передачи данных по протоколу TCP на порту 808 с любым именем узла.

    2. Несмотря на то что все приложения в узле имеют общую привязку к протоколу net.tcp, включать поддержку net.tcp можно для каждого приложения отдельно. Для включения протокола net.tcp для приложения /servicemodelsample необходимо выполнить следующую команду из командной строки с правами администратора:

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app
        "Default Web Site/servicemodelsamples" /enabledProtocols:http,net.tcp
        ```

        > [!NOTE]
        > Эта команда представляет собой одну строку текста. Эта команда позволяет получить доступ к приложению/сервицемоделсамплес, используя как `http://localhost/servicemodelsamples`, так `net.tcp://localhost/servicemodelsamples`.

4. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).

5. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).

    Удалите привязку сайта к протоколу net.tcp, добавленную ранее для данного образца.

    Для удобства два нижеописанных действия выполняются в пакетом файле RemoveNetTcpSiteBinding.cmd, расположенном в каталоге с образцами.

    1. Удалите протокол net.tcp из списка разрешенных протоколов, выполнив следующую команду в окне командной строки с правами администратора:

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app
        "Default Web Site/servicemodelsamples" /enabledProtocols:http
        ```

        > [!NOTE]
        > Эта команда вводится как одна строка текста.

    2. Удалите привязку узла к протоколу net.tcp, выполнив следующую команду в окне командной строки с правами администратора:

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        --bindings.[protocol='net.tcp',bindingInformation='808:*']
        ```

        > [!NOTE]
        > Эта команда должна вводиться как одна строка текста.

## <a name="see-also"></a>См. также:

- [Примеры размещения и сохраняемости AppFabric](https://go.microsoft.com/fwlink/?LinkId=193961)
