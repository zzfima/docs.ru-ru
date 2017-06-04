---
title: "Конфигурация и поддержка метаданных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 27c240cb-8cab-472c-87f8-c864f4978758
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Конфигурация и поддержка метаданных
В этом разделе описывается, как включить поддержку конфигурации и метаданных для привязки и элементов привязки.  
  
## Общие сведения о конфигурации и метаданных  
 В этом разделе рассматриваются следующие задачи, которые представляют собой необязательные пункты 1, 2 и 4 в списке задач [Разработка каналов](../../../../docs/framework/wcf/extending/developing-channels.md):  
  
-   включение поддержки файла конфигурации для элемента привязки.  
  
-   включение поддержки файла конфигурации для привязки;  
  
-   экспорт WSDL\-кода и утверждений политики для элемента привязки;  
  
-   определение вставляемых WSDL\-кода и утверждений политики и настройка привязки или элемента привязки.  
  
 Дополнительные сведения о создании пользовательских привязок и элементов привязки см. в разделах [Создание пользовательских привязок](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md) и [Создание элемента привязки BindingElement](../../../../docs/framework/wcf/extending/creating-a-bindingelement.md) соответственно.  
  
## Добавление поддержки конфигурации  
 Чтобы включить поддержку файла конфигурации для канала, необходимо реализовать два раздела конфигурации: <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=fullName> для поддержки конфигурации для элементов привязки и <xref:System.ServiceModel.Configuration.StandardBindingElement?displayProperty=fullName> и <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602?displayProperty=fullName> для поддержки конфигурации для привязок.  
  
 Более простой способ это сделать — воспользоваться средством из образца [ConfigurationCodeGenerator](../../../../docs/framework/wcf/samples/configurationcodegenerator.md) для формирования кода конфигурации для привязок и элементов привязки.  
  
### Расширение класса BindingElementExtensionElement  
 Следующий фрагмент кода взят из образца [Транспорт: UDP](../../../../docs/framework/wcf/samples/transport-udp.md).Раздел `UdpTransportElement` — это элемент <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>, который предоставляет элемент привязки `UdpTransportBindingElement` к системе конфигурации.С помощью нескольких простых переопределений в образце определяется имя раздела конфигурации, тип элемента привязки и способ создания элемента привязки.Пользователи могут затем зарегистрировать раздел расширения в файле конфигурации следующим образом.  
  
```  
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
  
```  
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
  
### Добавление конфигурации для привязки  
 Раздел `SampleProfileUdpBindingCollectionElement` — это элемент <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602>, который предоставляет элемент `SampleProfileUdpBinding` системе конфигурации.Основная часть реализации делегируется классу `SampleProfileUdpBindingConfigurationElement`, наследуемому от класса <xref:System.ServiceModel.Configuration.StandardBindingElement>.Класс `SampleProfileUdpBindingConfigurationElement` имеет свойства, соответствующие свойствам класса `SampleProfileUdpBinding`, и обеспечивает сопоставление привязки `ConfigurationElement` .Наконец, метод `OnApplyConfiguration` в классе `SampleProfileUdpBinding` переопределяется, как показано в следующем образце кода.  
  
```  
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
  
```  
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
  
 После этого на него можно сослаться из раздела конфигурации [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md).  
  
```  
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
  
## Добавление поддержки метаданных для элемента привязки  
 Для интеграции канала в систему метаданных он должен поддерживать как импорт, так и экспорт политики.Это позволяет средствам, таким как [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), формировать клиенты элемента привязки.  
  
### Добавление поддержки WSDL  
 За экспорт и импорт адресов в метаданных отвечает элемент привязки транспорта.При использовании привязки SOAP элемент привязки транспорта должен также экспортировать в метаданных правильный URI \(универсальный код ресурса\) транспорта.Следующий фрагмент кода взят из образца [Транспорт: UDP](../../../../docs/framework/wcf/samples/transport-udp.md).  
  
#### Экспорт WSDL  
 Для экспорта адресов элемент привязки `UdpTransportBindingElement` реализует интерфейс <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=fullName>.Метод <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A?displayProperty=fullName> добавляет правильные адреса в порт WSDL.  
  
```  
if (context.WsdlPort != null)  
{  
    AddAddressToWsdlPort(context.WsdlPort, context.Endpoint.Address, encodingBindingElement.MessageVersion.Addressing);  
}  
```  
  
 Реализация метода <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A> в элементе `UdpTransportBindingElement` также экспортирует URI транспорта, когда конечная точка использует привязку SOAP:  
  
```  
WsdlNS.SoapBinding soapBinding = GetSoapBinding(context, exporter);  
if (soapBinding != null)  
{  
    soapBinding.Transport = UdpPolicyStrings.UdpNamespace;  
}  
```  
  
#### Импорт WSDL  
 Чтобы расширить систему импорта WSDL для обработки импорта адресов, добавьте в файл конфигурации Svcutil.exe следующую конфигурацию, как показано в файле Svcutil.exe.config:  
  
```  
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
  
1.  Указать Svcutil.exe на файл конфигурации с помощью параметра \/SvcutilConfig:\<file\>.  
  
2.  Добавить раздел конфигурации в файл Svcutil.exe.config, находящийся в том же каталоге, что и файл Svcutil.exe.  
  
 Тип `UdpBindingElementImporter` реализует интерфейс <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=fullName>.Метод `ImportEndpoint` импортирует адрес из порта WSDL:  
  
```  
BindingElementCollection bindingElements = context.Endpoint.Binding.CreateBindingElements();  
TransportBindingElement transportBindingElement = bindingElements.Find<TransportBindingElement>();  
if (transportBindingElement is UdpTransportBindingElement)  
{  
    ImportAddress(context);  
}  
```  
  
### Добавление поддержки политик  
 Пользовательский элемент привязки может экспортировать утверждения политики в привязке WSDL для конечной точки службы, чтобы показать возможности этого элемента привязки.Следующий фрагмент кода взят из образца [Транспорт: UDP](../../../../docs/framework/wcf/samples/transport-udp.md).  
  
#### Экспорт политики  
 Тип `UdpTransportBindingElement` реализует интерфейс ``<xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=fullName> для добавления поддержки экспорта политик.В результате класс <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=fullName> включает элемент `UdpTransportBindingElement` при формировании политики для любой привязки, в которую он входит.  
  
 В методе <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A?displayProperty=fullName> добавьте утверждение для UDP и еще одно утверждение, если канал находится в режиме многоадресной рассылки.Это связано с тем, что режим многоадресной рассылки влияет на построение стека связи и, следовательно, должен быть согласован обеими сторонами.  
  
```  
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
  
 Поскольку пользовательские элементы привязки транспорта отвечают за обработку адресов, реализация <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=fullName> в элементе `UdpTransportBindingElement` должна также обрабатывать экспорт соответствующих утверждений политики WS\-Addressing для указания используемой версии WS\-Addressing.  
  
```  
AddWSAddressingAssertion(context, encodingBindingElement.MessageVersion.Addressing);  
```  
  
#### Импорт политики  
 Чтобы расширить систему импорта политик, добавьте в файл конфигурации Svcutil.exe следующую конфигурацию, как показано в файле Svcutil.exe.config:  
  
```  
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
  
 Затем мы реализуем интерфейс <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=fullName> из зарегистрированного нами класса \(`UdpBindingElementImporter`\).В методе <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=fullName> рассмотрим утверждения в соответствующем пространстве имен и обработаем те из них, которые предназначены для формирования транспорта и проверки того, является ли он многоадресным.Кроме того, удалим утверждения, обрабатываемые импортером, из списка утверждений привязки.Снова\-таки, при запуске Svcutil.exe существует два варианта интеграции:  
  
1.  Указать Svcutil.exe на файл конфигурации с помощью параметра \/SvcutilConfig:\<file\>.  
  
2.  Добавить раздел конфигурации в файл Svcutil.exe.config, находящийся в том же каталоге, что и файл Svcutil.exe.  
  
### Добавление пользовательского импортера стандартной привязки  
 Svcutil.exe и тип <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=fullName> по умолчанию распознают и импортируют предоставляемые системой привязки.В противном случае привязка импортируется как экземпляр <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=fullName>.Чтобы Svcutil.exe и тип <xref:System.ServiceModel.Description.WsdlImporter> могли импортировать привязку `SampleProfileUdpBinding`, тип `UdpBindingElementImporter` также выступает в качестве пользовательского импортера стандартной привязки.  
  
 Пользовательский импортер стандартной привязки реализует метод `ImportEndpoint` в интерфейсе <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=fullName>, чтобы проверить импортированный из метаданных экземпляр класса <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=fullName> и определить, мог ли он быть сформирован определенной стандартной привязкой.  
  
```  
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
  
 Как правило, реализация пользовательского импортера стандартной привязки предусматривает проверку свойств импортированных элементов привязки на предмет того, что изменены только свойства, которые могли быть заданы стандартной привязкой, а все остальные свойства имеют значения по умолчанию.Простейшая стратегия для реализации импортера стандартной привязки — создать экземпляр стандартной привязки, распространить на экземпляр стандартной привязки свойства из элементов привязки, поддерживаемые стандартной привязкой, и затем сравнить элементы привязки из стандартной привязки с импортированными элементами привязки.