---
title: Использование стандартных конечных точек
ms.date: 03/30/2017
ms.assetid: ecd6a62f-9619-4778-a497-6f888087a9ea
ms.openlocfilehash: a2af1ae793166d1ed3742782b911ded30d0b9d35
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662395"
---
# <a name="usage-of-standard-endpoints"></a>Использование стандартных конечных точек

Этот образец демонстрирует использование стандартных конечных точек в файлах конфигурации службы. Стандартная конечная точка позволяет пользователю упростить определения конечных точек за счет использования единого свойства, описывающего комбинацию адреса, привязки и контракта вместе с дополнительными свойствами. Данный образец демонстрирует определение и реализацию пользовательской стандартной конечной точки, а также определение конкретных свойств в конечной точке.

## <a name="sample-details"></a>Подробные сведения об образце

Конечные точки службы могут быть заданы с использованием трех параметров: адреса, привязки и контракта. Кроме того, можно задать и другие параметры - конфигурацию поведения, заголовки, URI прослушивания и т. д. В некоторых случаях значения адресов, привязок или контрактов не могут меняться. В такой ситуации можно воспользоваться стандартными конечными точками. Среди примеров таких конечных точек - конечные точки обмена метаданными и конечные точки обнаружения. Стандартные конечные точки также повышают удобство использования, позволяя конфигурировать конечные точки службы, не предоставляя сведений фиксированного характера и не создавая для них собственных стандартных конечных точек. Это дает возможность, например, повысить удобство использования, предоставляя разумный набор значений по умолчанию и тем самым сокращая количество строк в файле конфигурации.

Данный образец состоит из двух проектов - службы, которая определяет две стандартных конечных точки, и клиента, который обращается к службе. Метод определения стандартных конечных точек для этой службы в файле конфигурации показан в следующем примере.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <extensions>
      <endpointExtensions>
        <add name="customEndpoint" type="Microsoft.Samples.StandardEndpoints.CustomEndpointCollectionElement, service" />
      </endpointExtensions>
    </extensions>
    <services>
      <service name="Microsoft.Samples.StandardEndpoints.CalculatorService">
        <endpoint address="http://localhost:8000/Samples/Service.svc/customEndpoint" contract="Microsoft.Samples.StandardEndpoints.ICalculator" kind="customEndpoint" />
        <endpoint kind="mexEndpoint" />
      </service>
    </services>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <serviceMetadata httpGetEnabled="True"/>
        </behavior>
      </serviceBehaviors>
    </behaviors>
    <standardEndpoints>
      <customEndpoint>
        <standardEndpoint property="True" />
      </customEndpoint>
    </standardEndpoints>
  </system.serviceModel>
</configuration>
```

Первая конечная точка, определенная для службы, имеет тип `customEndpoint`, ее определение можно увидеть в разделе `<standardEndpoints>`, в котором свойству `property` задано значение `true`. Это пример конечной точки, дополненной новым свойством. Вторая конечная точка соответствует конечной точке метаданных, и значения адреса, привязки и контракта в ней фиксированы.

Для определения элемента стандартной конечной точки необходимо создать класс, производный от класса `StandardEndpointElement`. В нашем образце класс `CustomEndpointElement` определен, как показано в следующем фрагменте кода.

```csharp
public class CustomEndpointElement : StandardEndpointElement
{
    public bool Property
    {
        get { return (bool)base["property"]; }
        set { base["property"] = value; }
    }

    protected override ConfigurationPropertyCollection Properties
    {
        get
        {
            ConfigurationPropertyCollection properties = base.Properties;
            properties.Add(new ConfigurationProperty("property", typeof(bool), false, ConfigurationPropertyOptions.None));
            return properties;
        }
    }

    protected override Type EndpointType
    {
        get { return typeof(CustomEndpoint); }
    }

    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contract)
    {
        return new CustomEndpoint();
    }

    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)
    {
    }

    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)
    {
    }
}
```

В функции `CreateServiceEndpoint` создается объект `CustomEndpoint`. Его определение показано в следующем примере:

```csharp
public class CustomEndpoint : ServiceEndpoint
{
    public CustomEndpoint()
        : this(string.Empty)
    {
    }

    public CustomEndpoint(string address)
        : this(address, ContractDescription.GetContract(typeof(ICalculator)))
    {
    }

    public CustomEndpoint(string address, ContractDescription contract)
        : base(contract)
    {
        this.Binding = new BasicHttpBinding();
        this.IsSystemEndpoint = false;
    }

    public bool Property
    {
        get;
        set;
    }
}
```

 Чтобы осуществить сообщение между службой и клиентом, в клиенте, обращающемся к службе, создается ссылка на службу. Когда образец построен и запущен, запускается и служба, и клиент сообщается с ней. Обратите внимание, что ссылку на службу следует обновлять при каждом изменении службы.

#### <a name="to-use-this-sample"></a>Использование этого образца

1. С помощью Visual Studio 2012, откройте файл StandardEndpoints.sln.

2. Разрешите запуск нескольких проектов.

    1. В **обозревателе решений**, щелкните правой кнопкой мыши решение стандартные конечные точки, а затем выберите **свойства**.

    2. В **общие свойства**выберите **запускаемым проектом**, а затем нажмите кнопку **несколько запускаемых проектов**.

    3. Переместить в начало списка, в проект службы с **действие** присвоено **запустить**.

    4. Переместить в клиентский проект после в проект службы, также с **действие** присвоено **запустить**.

         Это указывает, что проект «Client» выполняется после проекта «Service».

3. Чтобы запустить решение, нажмите клавишу F5.

> [!NOTE]
> Если эти шаги не работают, убедитесь в том, что вашей среде должным образом настроен, выполнив следующие действия:
>
> 1. Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).
> 2. Чтобы построить решение, следуйте инструкциям в [сборка образцов Windows Communication Foundation](building-the-samples.md).
> 3. Чтобы запустить пример одного или нескольких конфигураций компьютеров, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](running-the-samples.md).

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\StandardEndpoints`
