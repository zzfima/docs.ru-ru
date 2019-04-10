---
title: Конфигурация и поддержка метаданных
ms.date: 03/30/2017
ms.assetid: 27c240cb-8cab-472c-87f8-c864f4978758
ms.openlocfilehash: abc9177fcc7b338a365d61721b63041ddcd68ab9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59298309"
---
# <a name="configuration-and-metadata-support"></a><span data-ttu-id="fe50d-102">Конфигурация и поддержка метаданных</span><span class="sxs-lookup"><span data-stu-id="fe50d-102">Configuration and Metadata Support</span></span>
<span data-ttu-id="fe50d-103">В этом разделе описывается, как включить поддержку конфигурации и метаданных для привязки и элементов привязки.</span><span class="sxs-lookup"><span data-stu-id="fe50d-103">This topic describes how to enable configuration and metadata support for bindings and binding elements.</span></span>  
  
## <a name="overview-of-configuration-and-metadata"></a><span data-ttu-id="fe50d-104">Общие сведения о конфигурации и метаданных</span><span class="sxs-lookup"><span data-stu-id="fe50d-104">Overview of Configuration and Metadata</span></span>  
 <span data-ttu-id="fe50d-105">В этом разделе рассматриваются следующие задачи, которые представляют собой необязательные пункты 1, 2 и 4 в [каналы развивающихся](../../../../docs/framework/wcf/extending/developing-channels.md) списка задач.</span><span class="sxs-lookup"><span data-stu-id="fe50d-105">This topic discusses the following tasks, which are optional items 1, 2, and 4 in the [Developing Channels](../../../../docs/framework/wcf/extending/developing-channels.md) task list.</span></span>  
  
-   <span data-ttu-id="fe50d-106">включение поддержки файла конфигурации для элемента привязки.</span><span class="sxs-lookup"><span data-stu-id="fe50d-106">Enabling configuration file support for a binding element.</span></span>  
  
-   <span data-ttu-id="fe50d-107">включение поддержки файла конфигурации для привязки;</span><span class="sxs-lookup"><span data-stu-id="fe50d-107">Enabling configuration file support for a binding.</span></span>  
  
-   <span data-ttu-id="fe50d-108">экспорт WSDL-кода и утверждений политики для элемента привязки;</span><span class="sxs-lookup"><span data-stu-id="fe50d-108">Exporting WSDL and policy assertions for a binding element.</span></span>  
  
-   <span data-ttu-id="fe50d-109">определение вставляемых WSDL-кода и утверждений политики и настройка привязки или элемента привязки.</span><span class="sxs-lookup"><span data-stu-id="fe50d-109">Identifying WSDL and policy assertions to insert and configure your binding or binding element.</span></span>  
  
 <span data-ttu-id="fe50d-110">Сведения о создании пользовательских привязок и элементов привязки, см. в разделе [параметрах привязок](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md) и [Создание элемента привязки BindingElement](../../../../docs/framework/wcf/extending/creating-a-bindingelement.md), соответственно.</span><span class="sxs-lookup"><span data-stu-id="fe50d-110">For information about creating user-defined bindings and binding elements, see [Creating User-Defined Bindings](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md) and [Creating a BindingElement](../../../../docs/framework/wcf/extending/creating-a-bindingelement.md), respectively.</span></span>  
  
## <a name="adding-configuration-support"></a><span data-ttu-id="fe50d-111">Добавление поддержки конфигурации</span><span class="sxs-lookup"><span data-stu-id="fe50d-111">Adding Configuration Support</span></span>  
 <span data-ttu-id="fe50d-112">Чтобы включить поддержку файла конфигурации для канала, необходимо реализовать два раздела конфигурации: <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=nameWithType> для поддержки конфигурации для элементов привязки и <xref:System.ServiceModel.Configuration.StandardBindingElement?displayProperty=nameWithType> и <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602?displayProperty=nameWithType> для поддержки конфигурации для привязок.</span><span class="sxs-lookup"><span data-stu-id="fe50d-112">To enable configuration file support for a channel, you must implement two configuration sections, <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=nameWithType>, which enables configuration support for binding elements, and the <xref:System.ServiceModel.Configuration.StandardBindingElement?displayProperty=nameWithType> and <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602?displayProperty=nameWithType>, which enable configuration support for bindings.</span></span>  
  
 <span data-ttu-id="fe50d-113">Более простой способ сделать это является использование [ConfigurationCodeGenerator](../../../../docs/framework/wcf/samples/configurationcodegenerator.md) пример инструмента для формирования кода конфигурации для привязки и элементы привязки.</span><span class="sxs-lookup"><span data-stu-id="fe50d-113">An easier way to do this is to use the [ConfigurationCodeGenerator](../../../../docs/framework/wcf/samples/configurationcodegenerator.md) sample tool to generate configuration code for your bindings and binding elements.</span></span>  
  
### <a name="extending-bindingelementextensionelement"></a><span data-ttu-id="fe50d-114">Расширение класса BindingElementExtensionElement</span><span class="sxs-lookup"><span data-stu-id="fe50d-114">Extending BindingElementExtensionElement</span></span>  
 <span data-ttu-id="fe50d-115">В следующем примере кода берется из [транспорта: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) образца.</span><span class="sxs-lookup"><span data-stu-id="fe50d-115">The following example code is taken from the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span> <span data-ttu-id="fe50d-116">Раздел `UdpTransportElement` - это элемент <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>, который предоставляет элемент привязки `UdpTransportBindingElement` к системе конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fe50d-116">The `UdpTransportElement` is a <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> that exposes `UdpTransportBindingElement` to the configuration system.</span></span> <span data-ttu-id="fe50d-117">С помощью нескольких простых переопределений в образце определяется имя раздела конфигурации, тип элемента привязки и способ создания элемента привязки.</span><span class="sxs-lookup"><span data-stu-id="fe50d-117">With a few basic overrides, the sample defines the configuration section name, the type of the binding element and how to create the binding element.</span></span> <span data-ttu-id="fe50d-118">Пользователи могут затем зарегистрировать раздел расширения в файле конфигурации следующим образом.</span><span class="sxs-lookup"><span data-stu-id="fe50d-118">Users can then register the extension section in a configuration file as follows.</span></span>  
  
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
  
 <span data-ttu-id="fe50d-119">На расширение можно ссылаться из пользовательских привязок, чтобы использовать в качестве транспорта протокол UDP.</span><span class="sxs-lookup"><span data-stu-id="fe50d-119">The extension can be referenced from custom bindings to use UDP as the transport.</span></span>  
  
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
  
### <a name="adding-configuration-for-a-binding"></a><span data-ttu-id="fe50d-120">Добавление конфигурации для привязки</span><span class="sxs-lookup"><span data-stu-id="fe50d-120">Adding Configuration for a Binding</span></span>  
 <span data-ttu-id="fe50d-121">Разделе `SampleProfileUdpBindingCollectionElement` — <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> , предоставляющий `SampleProfileUdpBinding` системе конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fe50d-121">The section `SampleProfileUdpBindingCollectionElement` is a <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> that exposes `SampleProfileUdpBinding` to the configuration system.</span></span> <span data-ttu-id="fe50d-122">Основная часть реализации делегируется классу `SampleProfileUdpBindingConfigurationElement`, наследуемому от класса <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="fe50d-122">The bulk of the implementation is delegated to the `SampleProfileUdpBindingConfigurationElement`, which derives from <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span></span> <span data-ttu-id="fe50d-123">`SampleProfileUdpBindingConfigurationElement` Имеет свойства, которые соответствуют свойствам в `SampleProfileUdpBinding`и обеспечивает сопоставление `ConfigurationElement` привязки.</span><span class="sxs-lookup"><span data-stu-id="fe50d-123">The `SampleProfileUdpBindingConfigurationElement` has properties that correspond to the properties on `SampleProfileUdpBinding`, and functions to map from the `ConfigurationElement` binding.</span></span> <span data-ttu-id="fe50d-124">Наконец, метод `OnApplyConfiguration` в классе `SampleProfileUdpBinding` переопределяется, как показано в следующем образце кода.</span><span class="sxs-lookup"><span data-stu-id="fe50d-124">Finally, the `OnApplyConfiguration` method is overridden in the `SampleProfileUdpBinding`, as shown in the following sample code.</span></span>  
  
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
  
 <span data-ttu-id="fe50d-125">Чтобы зарегистрировать этот обработчик в системе конфигурации, добавьте в соответствующий файл конфигурации следующий раздел.</span><span class="sxs-lookup"><span data-stu-id="fe50d-125">To register this handler with the configuration system, add the following section to the relevant configuration file.</span></span>  
  
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
  
 <span data-ttu-id="fe50d-126">Затем можно ссылаться на [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) раздел конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fe50d-126">It can then be referenced from the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) configuration section.</span></span>  
  
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
  
## <a name="adding-metadata-support-for-a-binding-element"></a><span data-ttu-id="fe50d-127">Добавление поддержки метаданных для элемента привязки</span><span class="sxs-lookup"><span data-stu-id="fe50d-127">Adding Metadata Support for a Binding Element</span></span>  
 <span data-ttu-id="fe50d-128">Для интеграции канала в систему метаданных он должен поддерживать как импорт, так и экспорт политики.</span><span class="sxs-lookup"><span data-stu-id="fe50d-128">To integrate a channel into the metadata system, it must support both the import and export of policy.</span></span> <span data-ttu-id="fe50d-129">Это позволяет средствам, такие как [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) , формировать клиенты элемента привязки.</span><span class="sxs-lookup"><span data-stu-id="fe50d-129">This allows tools such as [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate clients of the binding element.</span></span>  
  
### <a name="adding-wsdl-support"></a><span data-ttu-id="fe50d-130">Добавление поддержки WSDL</span><span class="sxs-lookup"><span data-stu-id="fe50d-130">Adding WSDL Support</span></span>  
 <span data-ttu-id="fe50d-131">За экспорт и импорт адресов в метаданных отвечает элемент привязки транспорта.</span><span class="sxs-lookup"><span data-stu-id="fe50d-131">The transport binding element in a binding is responsible for exporting and importing addressing information in metadata.</span></span> <span data-ttu-id="fe50d-132">При использовании привязки протокола SOAP элемент привязки транспорта должен также экспортировать в метаданных правильный URI (универсальный код ресурса) транспорта.</span><span class="sxs-lookup"><span data-stu-id="fe50d-132">When using a SOAP binding, the transport binding element should also export a correct transport URI in metadata.</span></span> <span data-ttu-id="fe50d-133">В следующем примере кода берется из [транспорта: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) образца.</span><span class="sxs-lookup"><span data-stu-id="fe50d-133">The following example code is taken from the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span>  
  
#### <a name="wsdl-export"></a><span data-ttu-id="fe50d-134">Экспорт WSDL</span><span class="sxs-lookup"><span data-stu-id="fe50d-134">WSDL Export</span></span>  
 <span data-ttu-id="fe50d-135">Для экспорта адресов элемент привязки `UdpTransportBindingElement` реализует <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> интерфейс.</span><span class="sxs-lookup"><span data-stu-id="fe50d-135">To export addressing information, the `UdpTransportBindingElement` implements the <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="fe50d-136"><xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A?displayProperty=nameWithType> Метод добавляет правильные адреса порта WSDL.</span><span class="sxs-lookup"><span data-stu-id="fe50d-136">The <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A?displayProperty=nameWithType> method adds the correct addressing information to the WSDL port.</span></span>  
  
```csharp  
if (context.WsdlPort != null)  
{  
    AddAddressToWsdlPort(context.WsdlPort, context.Endpoint.Address, encodingBindingElement.MessageVersion.Addressing);  
}  
```  
  
 <span data-ttu-id="fe50d-137">Реализация метода `UdpTransportBindingElement` в элементе <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A> также экспортирует URI транспорта, когда конечная точка использует привязку SOAP:</span><span class="sxs-lookup"><span data-stu-id="fe50d-137">The `UdpTransportBindingElement` implementation of the <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A> method also exports a transport URI when the endpoint uses a SOAP binding:</span></span>  
  
```csharp  
WsdlNS.SoapBinding soapBinding = GetSoapBinding(context, exporter);  
if (soapBinding != null)  
{  
    soapBinding.Transport = UdpPolicyStrings.UdpNamespace;  
}  
```  
  
#### <a name="wsdl-import"></a><span data-ttu-id="fe50d-138">Импорт WSDL</span><span class="sxs-lookup"><span data-stu-id="fe50d-138">WSDL Import</span></span>  
 <span data-ttu-id="fe50d-139">Чтобы расширить систему импорта WSDL для обработки импорта адресов, добавьте в файл конфигурации Svcutil.exe следующую конфигурацию, как показано в файле Svcutil.exe.config:</span><span class="sxs-lookup"><span data-stu-id="fe50d-139">To extend the WSDL import system to handle importing the addresses, add the following configuration to the configuration file for Svcutil.exe as shown in the Svcutil.exe.config file:</span></span>  
  
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
  
 <span data-ttu-id="fe50d-140">При запуске Svcutil.exe существует два варианта обеспечить загрузку программой расширений импорта WSDL:</span><span class="sxs-lookup"><span data-stu-id="fe50d-140">When running Svcutil.exe, there are two options for getting Svcutil.exe to load the WSDL import extensions:</span></span>  
  
1. <span data-ttu-id="fe50d-141">Указать Svcutil.exe на файл конфигурации, с помощью параметра/svcutilconfig:\<файл >.</span><span class="sxs-lookup"><span data-stu-id="fe50d-141">Point Svcutil.exe to the configuration file using the /SvcutilConfig:\<file>.</span></span>  
  
2. <span data-ttu-id="fe50d-142">добавить раздел конфигурации в файл Svcutil.exe.config, находящийся в том же каталоге, что и файл Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="fe50d-142">Add the configuration section to Svcutil.exe.config in the same directory as Svcutil.exe.</span></span>  
  
 <span data-ttu-id="fe50d-143">`UdpBindingElementImporter` Введите реализует <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> интерфейс.</span><span class="sxs-lookup"><span data-stu-id="fe50d-143">The `UdpBindingElementImporter` type implements the <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="fe50d-144">Метод `ImportEndpoint` импортирует адрес из порта WSDL:</span><span class="sxs-lookup"><span data-stu-id="fe50d-144">The `ImportEndpoint` method imports the address from the WSDL port:</span></span>  
  
```csharp  
BindingElementCollection bindingElements = context.Endpoint.Binding.CreateBindingElements();  
TransportBindingElement transportBindingElement = bindingElements.Find<TransportBindingElement>();  
if (transportBindingElement is UdpTransportBindingElement)  
{  
    ImportAddress(context);  
}  
```  
  
### <a name="adding-policy-support"></a><span data-ttu-id="fe50d-145">Добавление поддержки политик</span><span class="sxs-lookup"><span data-stu-id="fe50d-145">Adding Policy Support</span></span>  
 <span data-ttu-id="fe50d-146">Пользовательский элемент привязки может экспортировать утверждения политики в привязке WSDL для конечной точки службы, чтобы показать возможности этого элемента привязки.</span><span class="sxs-lookup"><span data-stu-id="fe50d-146">The custom binding element can export policy assertions in the WSDL binding for a service endpoint to express the capabilities of that binding element.</span></span> <span data-ttu-id="fe50d-147">В следующем примере кода берется из [транспорта: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) образца.</span><span class="sxs-lookup"><span data-stu-id="fe50d-147">The following example code is taken from the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span>  
  
#### <a name="policy-export"></a><span data-ttu-id="fe50d-148">Экспорт политики</span><span class="sxs-lookup"><span data-stu-id="fe50d-148">Policy Export</span></span>  
 <span data-ttu-id="fe50d-149">`UdpTransportBindingElement` Введите реализует <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> для добавления поддержки экспорта политик.</span><span class="sxs-lookup"><span data-stu-id="fe50d-149">The `UdpTransportBindingElement` type implements <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> to add support for exporting policy.</span></span> <span data-ttu-id="fe50d-150">В результате класс <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> включает элемент `UdpTransportBindingElement` при формировании политики для любой привязки, в которую он входит.</span><span class="sxs-lookup"><span data-stu-id="fe50d-150">As a result, <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> includes `UdpTransportBindingElement` in the generation of policy for any binding that includes it.</span></span>  
  
 <span data-ttu-id="fe50d-151">В методе <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A?displayProperty=nameWithType> добавьте утверждение для UDP и еще одно утверждение, если канал находится в режиме многоадресной рассылки.</span><span class="sxs-lookup"><span data-stu-id="fe50d-151">In <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A?displayProperty=nameWithType>, add an assertion for UDP and another assertion if the channel is in multicast mode.</span></span> <span data-ttu-id="fe50d-152">Это связано с тем, что режим многоадресной рассылки влияет на построение стека связи и, следовательно, должен быть согласован обеими сторонами.</span><span class="sxs-lookup"><span data-stu-id="fe50d-152">This is because multicast mode affects how the communication stack is constructed, and thus must be coordinated between both sides.</span></span>  
  
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
  
 <span data-ttu-id="fe50d-153">Поскольку пользовательские элементы привязки транспорта отвечают за обработку адресов, реализация <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> в элементе `UdpTransportBindingElement` должна также обрабатывать экспорт соответствующих утверждений политики WS-Addressing для указания используемой версии WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="fe50d-153">Because custom transport binding elements are responsible for handling addressing, the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> implementation on the `UdpTransportBindingElement` must also handle exporting the appropriate WS-Addressing policy assertions to indicate the version of WS-Addressing being used.</span></span>  
  
```csharp  
AddWSAddressingAssertion(context, encodingBindingElement.MessageVersion.Addressing);  
```  
  
#### <a name="policy-import"></a><span data-ttu-id="fe50d-154">Импорт политики</span><span class="sxs-lookup"><span data-stu-id="fe50d-154">Policy Import</span></span>  
 <span data-ttu-id="fe50d-155">Чтобы расширить систему импорта политик, добавьте в файл конфигурации Svcutil.exe следующую конфигурацию, как показано в файле Svcutil.exe.config:</span><span class="sxs-lookup"><span data-stu-id="fe50d-155">To extend the policy import system, add the following configuration to the configuration file for Svcutil.exe as shown in the Svcutil.exe.config file:</span></span>  
  
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
  
 <span data-ttu-id="fe50d-156">Затем мы реализуем интерфейс <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> из зарегистрированного нами класса (`UdpBindingElementImporter`).</span><span class="sxs-lookup"><span data-stu-id="fe50d-156">Then we implement <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> from our registered class (`UdpBindingElementImporter`).</span></span> <span data-ttu-id="fe50d-157">В методе <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType> рассмотрим утверждения в соответствующем пространстве имен и обработаем те из них, которые предназначены для формирования транспорта и проверки того, является ли он многоадресным.</span><span class="sxs-lookup"><span data-stu-id="fe50d-157">In <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType>, examine the assertions in the appropriate namespace and process the ones for generating the transport and checking if it is multicast.</span></span> <span data-ttu-id="fe50d-158">Кроме того, удалим утверждения, обрабатываемые импортером, из списка утверждений привязки.</span><span class="sxs-lookup"><span data-stu-id="fe50d-158">In addition, remove the assertions that the importer handles from the list of binding assertions.</span></span> <span data-ttu-id="fe50d-159">И опять при запуске Svcutil.exe существует два варианта интеграции:</span><span class="sxs-lookup"><span data-stu-id="fe50d-159">Again, when running Svcutil.exe, there are two options for integration:</span></span>  
  
1. <span data-ttu-id="fe50d-160">Указать Svcutil.exe на файл конфигурации с помощью параметра/svcutilconfig:\<файл >.</span><span class="sxs-lookup"><span data-stu-id="fe50d-160">Point Svcutil.exe to our configuration file using the /SvcutilConfig:\<file>.</span></span>  
  
2. <span data-ttu-id="fe50d-161">добавить раздел конфигурации в файл Svcutil.exe.config, находящийся в том же каталоге, что и файл Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="fe50d-161">Add the configuration section to Svcutil.exe.config in the same directory as Svcutil.exe.</span></span>  
  
### <a name="adding-a-custom-standard-binding-importer"></a><span data-ttu-id="fe50d-162">Добавление пользовательского импортера стандартной привязки</span><span class="sxs-lookup"><span data-stu-id="fe50d-162">Adding a Custom Standard Binding Importer</span></span>  
 <span data-ttu-id="fe50d-163">Svcutil.exe и тип <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> по умолчанию распознают и импортируют предоставляемые системой привязки.</span><span class="sxs-lookup"><span data-stu-id="fe50d-163">Svcutil.exe and the <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> type, by default, recognize and import system-provided bindings.</span></span> <span data-ttu-id="fe50d-164">В противном случае привязка импортируется как экземпляр <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fe50d-164">Otherwise, the binding gets imported as a <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="fe50d-165">Чтобы Svcutil.exe и тип <xref:System.ServiceModel.Description.WsdlImporter> могли импортировать привязку `SampleProfileUdpBinding`, тип `UdpBindingElementImporter` также выступает в качестве пользовательского импортера стандартной привязки.</span><span class="sxs-lookup"><span data-stu-id="fe50d-165">To enable Svcutil.exe and the <xref:System.ServiceModel.Description.WsdlImporter> to import the `SampleProfileUdpBinding` the `UdpBindingElementImporter` also acts as a custom standard binding importer.</span></span>  
  
 <span data-ttu-id="fe50d-166">Пользовательский импортер стандартной привязки реализует `ImportEndpoint` метод <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> интерфейс изучаемый <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> экземпляра, импортированный из метаданных см. в разделе, если он может быть сформирован определенной стандартной привязкой.</span><span class="sxs-lookup"><span data-stu-id="fe50d-166">A custom standard binding importer implements the `ImportEndpoint` method on the <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> interface to examine the <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> instance imported from metadata to see if it could have been generated by specific standard binding.</span></span>  
  
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
  
 <span data-ttu-id="fe50d-167">Как правило, реализация пользовательского импортера стандартной привязки предусматривает проверку свойств импортированных элементов привязки на предмет того, что изменены только свойства, которые могли быть заданы стандартной привязкой, а все остальные свойства имеют значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fe50d-167">Generally, implementing a custom standard binding importer involves checking the properties of the imported binding elements to verify that only properties that could have been set by the standard binding have changed and all other properties are their defaults.</span></span> <span data-ttu-id="fe50d-168">Простейшая стратегия для реализации импортера стандартной привязки - создать экземпляр стандартной привязки, распространить на экземпляр стандартной привязки свойства из элементов привязки, поддерживаемые стандартной привязкой, и затем сравнить элементы привязки из стандартной привязки с импортированными элементами привязки.</span><span class="sxs-lookup"><span data-stu-id="fe50d-168">A basic strategy for implementing a standard binding importer is to create an instance of the standard binding, propagate the properties from the binding elements to the standard binding instance that the standard binding supports, and the compare the binding elements from the standard binding with the imported binding elements.</span></span>
