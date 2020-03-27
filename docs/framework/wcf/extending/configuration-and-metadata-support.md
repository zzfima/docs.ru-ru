---
title: Конфигурация и поддержка метаданных
ms.date: 03/30/2017
ms.assetid: 27c240cb-8cab-472c-87f8-c864f4978758
ms.openlocfilehash: fb4e1cc51b827f083e580362f57df27ced770179
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345287"
---
# <a name="configuration-and-metadata-support"></a>Конфигурация и поддержка метаданных
В этом разделе описывается, как включить поддержку конфигурации и метаданных для привязки и элементов привязки.  
  
## <a name="overview-of-configuration-and-metadata"></a>Общие сведения о конфигурации и метаданных  
 На этой теме обсуждаются следующие задачи, которые являются дополнительными пунктами 1, 2 и 4 в списке задач [«Развивающиеся каналы».](developing-channels.md)  
  
- включение поддержки файла конфигурации для элемента привязки.  
  
- включение поддержки файла конфигурации для привязки;  
  
- экспорт WSDL-кода и утверждений политики для элемента привязки;  
  
- определение вставляемых WSDL-кода и утверждений политики и настройка привязки или элемента привязки.  
  
 Для получения информации о создании пользовательских связей и связывающих элементов [см.](creating-user-defined-bindings.md) [Creating a BindingElement](creating-a-bindingelement.md)  
  
## <a name="adding-configuration-support"></a>Добавление поддержки конфигурации  
 Чтобы включить поддержку файла конфигурации для канала, необходимо реализовать два раздела конфигурации: <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=nameWithType> для поддержки конфигурации для элементов привязки и <xref:System.ServiceModel.Configuration.StandardBindingElement?displayProperty=nameWithType> и <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602?displayProperty=nameWithType> для поддержки конфигурации для привязок.  
  
 Проще всего сделать это , это использовать образец инструмента [ConfigurationCodeGenerator](../samples/configurationcodegenerator.md) для генерации кода конфигурации для привязок и связывающих элементов.  
  
### <a name="extending-bindingelementextensionelement"></a>Расширение класса BindingElementExtensionElement  
 Следующий пример кода взят из образца [Транспорта: UDP.](../samples/transport-udp.md) Раздел `UdpTransportElement` - это элемент <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>, который предоставляет элемент привязки `UdpTransportBindingElement` к системе конфигурации. С помощью нескольких простых переопределений в образце определяется имя раздела конфигурации, тип элемента привязки и способ создания элемента привязки. Пользователи могут затем зарегистрировать раздел расширения в файле конфигурации следующим образом.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <extensions>  
      <bindingElementExtensions>  
      <add name="udpTransport" type="Microsoft.ServiceModel.Samples.UdpTransportElement, UdpTransport" />  
      </bindingElementExtensions>  
    </extensions>  
  </system.serviceModel>  
</configuration>  
```  
  
 На расширение можно ссылаться из пользовательских привязок, чтобы использовать в качестве транспорта протокол UDP.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <customBinding>  
       <binding configurationName="UdpCustomBinding">  
         <udpTransport/>  
       </binding>  
      </customBinding>  
    </bindings>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="adding-configuration-for-a-binding"></a>Добавление конфигурации для привязки  
 Раздел `SampleProfileUdpBindingCollectionElement` представляет <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> собой систему конфигурации. `SampleProfileUdpBinding` Основная часть реализации делегируется классу `SampleProfileUdpBindingConfigurationElement`, наследуемому от класса <xref:System.ServiceModel.Configuration.StandardBindingElement>. Обладает `SampleProfileUdpBindingConfigurationElement` свойствами, которые соответствуют свойствам `SampleProfileUdpBinding`на, `ConfigurationElement` и функции для отображения из связывания. Наконец, метод `OnApplyConfiguration` в классе `SampleProfileUdpBinding` переопределяется, как показано в следующем образце кода.  
  
```csharp
protected override void OnApplyConfiguration(string configurationName)  
{  
            if (binding == null)  
                throw new ArgumentNullException("binding");  
  
            if (binding.GetType() != typeof(SampleProfileUdpBinding))  
            {  
                var expectedType = typeof(SampleProfileUdpBinding).AssemblyQualifiedName;
                var typePassedIn = binding.GetType().AssemblyQualifiedName;
                throw new ArgumentException($"Invalid type for binding. Expected type: {expectedType}. Type passed in: {typePassedIn}.");  
            }  
            SampleProfileUdpBinding udpBinding = (SampleProfileUdpBinding)binding;  
  
            udpBinding.OrderedSession = this.OrderedSession;  
            udpBinding.ReliableSessionEnabled = this.ReliableSessionEnabled;  
            udpBinding.SessionInactivityTimeout = this.SessionInactivityTimeout;  
            if (this.ClientBaseAddress != null)  
                   udpBinding.ClientBaseAddress = ClientBaseAddress;  
}  
```  
  
 Чтобы зарегистрировать этот обработчик в системе конфигурации, добавьте в соответствующий файл конфигурации следующий раздел.  
  
```xml  
<configuration>  
  <configSections>  
     <sectionGroup name="system.serviceModel">  
         <sectionGroup name="bindings">  
                 <section name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport" />  
         </sectionGroup>  
     </sectionGroup>  
  </configSections>  
</configuration>  
```  
  
 Затем на него можно ссылаться из [ \<раздела system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) конфигурации.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <endpoint configurationName="calculator"  
                address="soap.udp://localhost:8001/"
                bindingConfiguration="CalculatorServer"  
                binding="sampleProfileUdpBinding"
                contract= "Microsoft.ServiceModel.Samples.ICalculatorContract">  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="adding-metadata-support-for-a-binding-element"></a>Добавление поддержки метаданных для элемента привязки  
 Для интеграции канала в систему метаданных он должен поддерживать как импорт, так и экспорт политики. Это позволяет таким инструментам, как [ServiceModel Metadata Utility Tool (Svcutil.exe),](../servicemodel-metadata-utility-tool-svcutil-exe.md) генерировать клиентов связывающего элемента.  
  
### <a name="adding-wsdl-support"></a>Добавление поддержки WSDL  
 За экспорт и импорт адресов в метаданных отвечает элемент привязки транспорта. При использовании привязки протокола SOAP элемент привязки транспорта должен также экспортировать в метаданных правильный URI (универсальный код ресурса) транспорта. Следующий пример кода взят из образца [Транспорта: UDP.](../samples/transport-udp.md)  
  
#### <a name="wsdl-export"></a>Экспорт WSDL  
 Для экспорта адресной информации `UdpTransportBindingElement` интерфейс реализуется. <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> Метод <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A?displayProperty=nameWithType> добавляет правильную информацию адресации в порт WSDL.  
  
```csharp  
if (context.WsdlPort != null)  
{  
    AddAddressToWsdlPort(context.WsdlPort, context.Endpoint.Address, encodingBindingElement.MessageVersion.Addressing);  
}  
```  
  
 Реализация метода `UdpTransportBindingElement` в элементе <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A> также экспортирует URI транспорта, когда конечная точка использует привязку SOAP:  
  
```csharp  
WsdlNS.SoapBinding soapBinding = GetSoapBinding(context, exporter);  
if (soapBinding != null)  
{  
    soapBinding.Transport = UdpPolicyStrings.UdpNamespace;  
}  
```  
  
#### <a name="wsdl-import"></a>Импорт WSDL  
 Чтобы расширить систему импорта WSDL для обработки импорта адресов, добавьте в файл конфигурации Svcutil.exe следующую конфигурацию, как показано в файле Svcutil.exe.config:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <wsdlImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </wsdlImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 При запуске Svcutil.exe существует два варианта обеспечить загрузку программой расширений импорта WSDL:  
  
1. Точка Svcutil.exe к файлу конфигурации с помощью\</SvcutilConfig: файл>.  
  
2. добавить раздел конфигурации в файл Svcutil.exe.config, находящийся в том же каталоге, что и файл Svcutil.exe.  
  
 Тип `UdpBindingElementImporter` реализует <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> интерфейс. Метод `ImportEndpoint` импортирует адрес из порта WSDL:  
  
```csharp  
BindingElementCollection bindingElements = context.Endpoint.Binding.CreateBindingElements();  
TransportBindingElement transportBindingElement = bindingElements.Find<TransportBindingElement>();  
if (transportBindingElement is UdpTransportBindingElement)  
{  
    ImportAddress(context);  
}  
```  
  
### <a name="adding-policy-support"></a>Добавление поддержки политик  
 Пользовательский элемент привязки может экспортировать утверждения политики в привязке WSDL для конечной точки службы, чтобы показать возможности этого элемента привязки. Следующий пример кода взят из образца [Транспорта: UDP.](../samples/transport-udp.md)  
  
#### <a name="policy-export"></a>Экспорт политики  
 Тип `UdpTransportBindingElement` реализует <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> для добавления поддержки экспортной политики. В результате класс <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> включает элемент `UdpTransportBindingElement` при формировании политики для любой привязки, в которую он входит.  
  
 В методе <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A?displayProperty=nameWithType> добавьте утверждение для UDP и еще одно утверждение, если канал находится в режиме многоадресной рассылки. Это связано с тем, что режим многоадресной рассылки влияет на построение стека связи и, следовательно, должен быть согласован обеими сторонами.  
  
```csharp  
ICollection<XmlElement> bindingAssertions = context.GetBindingAssertions();  
XmlDocument xmlDocument = new XmlDocument();  
bindingAssertions.Add(xmlDocument.CreateElement(  
UdpPolicyStrings.Prefix, UdpPolicyStrings.TransportAssertion, UdpPolicyStrings.UdpNamespace));  
if (Multicast)  
{  
    bindingAssertions.Add(xmlDocument.CreateElement(  
UdpPolicyStrings.Prefix, UdpPolicyStrings.MulticastAssertion,     UdpPolicyStrings.UdpNamespace));  
}  
```  
  
 Поскольку пользовательские элементы привязки транспорта отвечают за обработку адресов, реализация <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> в элементе `UdpTransportBindingElement` должна также обрабатывать экспорт соответствующих утверждений политики WS-Addressing для указания используемой версии WS-Addressing.  
  
```csharp  
AddWSAddressingAssertion(context, encodingBindingElement.MessageVersion.Addressing);  
```  
  
#### <a name="policy-import"></a>Импорт политики  
 Чтобы расширить систему импорта политик, добавьте в файл конфигурации Svcutil.exe следующую конфигурацию, как показано в файле Svcutil.exe.config:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <policyImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 Затем мы реализуем интерфейс <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> из зарегистрированного нами класса (`UdpBindingElementImporter`). В методе <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType> рассмотрим утверждения в соответствующем пространстве имен и обработаем те из них, которые предназначены для формирования транспорта и проверки того, является ли он многоадресным. Кроме того, удалим утверждения, обрабатываемые импортером, из списка утверждений привязки. И опять при запуске Svcutil.exe существует два варианта интеграции:  
  
1. Точка Svcutil.exe к нашему файлу конфигурации с\<помощью /SvcutilConfig: файл>.  
  
2. добавить раздел конфигурации в файл Svcutil.exe.config, находящийся в том же каталоге, что и файл Svcutil.exe.  
  
### <a name="adding-a-custom-standard-binding-importer"></a>Добавление пользовательского импортера стандартной привязки  
 Svcutil.exe и тип <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> по умолчанию распознают и импортируют предоставляемые системой привязки. В противном случае привязка импортируется как экземпляр <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>. Чтобы Svcutil.exe и тип <xref:System.ServiceModel.Description.WsdlImporter> могли импортировать привязку `SampleProfileUdpBinding`, тип `UdpBindingElementImporter` также выступает в качестве пользовательского импортера стандартной привязки.  
  
 Пользовательский стандартный обязательный `ImportEndpoint` импортер реализует <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> метод на <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> интерфейсе для изучения экземпляра, импортируемого из метаданных, чтобы увидеть, можно ли было ли его сгенерировать с помощью конкретного стандартного привязки.  
  
```csharp  
if (context.Endpoint.Binding is CustomBinding)  
{  
    Binding binding;  
    if (transportBindingElement is UdpTransportBindingElement)  
    {  
        //if TryCreate is true, the CustomBinding will be replace by a SampleProfileUdpBinding in the  
        //generated config file for better typed generation.  
        if (SampleProfileUdpBinding.TryCreate(bindingElements, out binding))  
        {  
            binding.Name = context.Endpoint.Binding.Name;  
            binding.Namespace = context.Endpoint.Binding.Namespace;  
            context.Endpoint.Binding = binding;  
        }  
    }  
}  
```  
  
 Как правило, реализация пользовательского импортера стандартной привязки предусматривает проверку свойств импортированных элементов привязки на предмет того, что изменены только свойства, которые могли быть заданы стандартной привязкой, а все остальные свойства имеют значения по умолчанию. Простейшая стратегия для реализации импортера стандартной привязки - создать экземпляр стандартной привязки, распространить на экземпляр стандартной привязки свойства из элементов привязки, поддерживаемые стандартной привязкой, и затем сравнить элементы привязки из стандартной привязки с импортированными элементами привязки.
