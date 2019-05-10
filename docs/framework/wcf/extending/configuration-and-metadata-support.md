---
title: Конфигурация и поддержка метаданных
ms.date: 03/30/2017
ms.assetid: 27c240cb-8cab-472c-87f8-c864f4978758
ms.openlocfilehash: 74dab4528ae11b60fc930a826962b71595073a7f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64587728"
---
# <a name="configuration-and-metadata-support"></a>Конфигурация и поддержка метаданных
В этом разделе описывается, как включить поддержку конфигурации и метаданных для привязки и элементов привязки.  
  
## <a name="overview-of-configuration-and-metadata"></a>Общие сведения о конфигурации и метаданных  
 В этом разделе рассматриваются следующие задачи, которые представляют собой необязательные пункты 1, 2 и 4 в [каналы развивающихся](../../../../docs/framework/wcf/extending/developing-channels.md) списка задач.  
  
- включение поддержки файла конфигурации для элемента привязки.  
  
- включение поддержки файла конфигурации для привязки;  
  
- экспорт WSDL-кода и утверждений политики для элемента привязки;  
  
- определение вставляемых WSDL-кода и утверждений политики и настройка привязки или элемента привязки.  
  
 Сведения о создании пользовательских привязок и элементов привязки, см. в разделе [параметрах привязок](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md) и [Создание элемента привязки BindingElement](../../../../docs/framework/wcf/extending/creating-a-bindingelement.md), соответственно.  
  
## <a name="adding-configuration-support"></a>Добавление поддержки конфигурации  
 Чтобы включить поддержку файла конфигурации для канала, необходимо реализовать два раздела конфигурации: <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=nameWithType> для поддержки конфигурации для элементов привязки и <xref:System.ServiceModel.Configuration.StandardBindingElement?displayProperty=nameWithType> и <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602?displayProperty=nameWithType> для поддержки конфигурации для привязок.  
  
 Более простой способ сделать это является использование [ConfigurationCodeGenerator](../../../../docs/framework/wcf/samples/configurationcodegenerator.md) пример инструмента для формирования кода конфигурации для привязки и элементы привязки.  
  
### <a name="extending-bindingelementextensionelement"></a>Расширение класса BindingElementExtensionElement  
 В следующем примере кода берется из [транспорта: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) образца. Раздел `UdpTransportElement` - это элемент <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>, который предоставляет элемент привязки `UdpTransportBindingElement` к системе конфигурации. С помощью нескольких простых переопределений в образце определяется имя раздела конфигурации, тип элемента привязки и способ создания элемента привязки. Пользователи могут затем зарегистрировать раздел расширения в файле конфигурации следующим образом.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <extensions>  
      <bindingElementExtensions>  
      <add name="udpTransport" type="Microsoft.ServiceModel.Samples.UdpTransportElement, UdpTransport />  
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
 Разделе `SampleProfileUdpBindingCollectionElement` — <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> , предоставляющий `SampleProfileUdpBinding` системе конфигурации. Основная часть реализации делегируется классу `SampleProfileUdpBindingConfigurationElement`, наследуемому от класса <xref:System.ServiceModel.Configuration.StandardBindingElement>. `SampleProfileUdpBindingConfigurationElement` Имеет свойства, которые соответствуют свойствам в `SampleProfileUdpBinding`и обеспечивает сопоставление `ConfigurationElement` привязки. Наконец, метод `OnApplyConfiguration` в классе `SampleProfileUdpBinding` переопределяется, как показано в следующем образце кода.  
  
```csharp 
protected override void OnApplyConfiguration(string configurationName)  
{  
            if (binding == null)  
                throw new ArgumentNullException("binding");  
  
            if (binding.GetType() != typeof(SampleProfileUdpBinding))  
            {  
                throw new ArgumentException(string.Format(CultureInfo.CurrentCulture,  
                    "Invalid type for binding. Expected type: {0}. Type passed in: {1}.",  
                    typeof(SampleProfileUdpBinding).AssemblyQualifiedName,  
                    binding.GetType().AssemblyQualifiedName));  
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
                 <section name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport />  
         </sectionGroup>  
     </sectionGroup>  
  </configSections>  
</configuration>  
```  
  
 Затем можно ссылаться на [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) раздел конфигурации.  
  
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
 Для интеграции канала в систему метаданных он должен поддерживать как импорт, так и экспорт политики. Это позволяет средствам, такие как [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) , формировать клиенты элемента привязки.  
  
### <a name="adding-wsdl-support"></a>Добавление поддержки WSDL  
 За экспорт и импорт адресов в метаданных отвечает элемент привязки транспорта. При использовании привязки протокола SOAP элемент привязки транспорта должен также экспортировать в метаданных правильный URI (универсальный код ресурса) транспорта. В следующем примере кода берется из [транспорта: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) образца.  
  
#### <a name="wsdl-export"></a>Экспорт WSDL  
 Для экспорта адресов элемент привязки `UdpTransportBindingElement` реализует <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> интерфейс. <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A?displayProperty=nameWithType> Метод добавляет правильные адреса порта WSDL.  
  
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
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 При запуске Svcutil.exe существует два варианта обеспечить загрузку программой расширений импорта WSDL:  
  
1. Указать Svcutil.exe на файл конфигурации, с помощью параметра/svcutilconfig:\<файл >.  
  
2. добавить раздел конфигурации в файл Svcutil.exe.config, находящийся в том же каталоге, что и файл Svcutil.exe.  
  
 `UdpBindingElementImporter` Введите реализует <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> интерфейс. Метод `ImportEndpoint` импортирует адрес из порта WSDL:  
  
```csharp  
BindingElementCollection bindingElements = context.Endpoint.Binding.CreateBindingElements();  
TransportBindingElement transportBindingElement = bindingElements.Find<TransportBindingElement>();  
if (transportBindingElement is UdpTransportBindingElement)  
{  
    ImportAddress(context);  
}  
```  
  
### <a name="adding-policy-support"></a>Добавление поддержки политик  
 Пользовательский элемент привязки может экспортировать утверждения политики в привязке WSDL для конечной точки службы, чтобы показать возможности этого элемента привязки. В следующем примере кода берется из [транспорта: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) образца.  
  
#### <a name="policy-export"></a>Экспорт политики  
 `UdpTransportBindingElement` Введите реализует <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> для добавления поддержки экспорта политик. В результате класс <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> включает элемент `UdpTransportBindingElement` при формировании политики для любой привязки, в которую он входит.  
  
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
  
1. Указать Svcutil.exe на файл конфигурации с помощью параметра/svcutilconfig:\<файл >.  
  
2. добавить раздел конфигурации в файл Svcutil.exe.config, находящийся в том же каталоге, что и файл Svcutil.exe.  
  
### <a name="adding-a-custom-standard-binding-importer"></a>Добавление пользовательского импортера стандартной привязки  
 Svcutil.exe и тип <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> по умолчанию распознают и импортируют предоставляемые системой привязки. В противном случае привязка импортируется как экземпляр <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>. Чтобы Svcutil.exe и тип <xref:System.ServiceModel.Description.WsdlImporter> могли импортировать привязку `SampleProfileUdpBinding`, тип `UdpBindingElementImporter` также выступает в качестве пользовательского импортера стандартной привязки.  
  
 Пользовательский импортер стандартной привязки реализует `ImportEndpoint` метод <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> интерфейс изучаемый <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> экземпляра, импортированный из метаданных см. в разделе, если он может быть сформирован определенной стандартной привязкой.  
  
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
