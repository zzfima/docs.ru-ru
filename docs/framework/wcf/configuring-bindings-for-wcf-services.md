---
title: Настройка привязок для служб Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- binding configuration [WCF]
ms.assetid: 99a85fd8-f7eb-4a84-a93e-7721b37d415c
ms.openlocfilehash: 8fcb2fbf49984ce2b6aaf1f112575d05a3d7d038
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="configuring-bindings-for-windows-communication-foundation-services"></a>Настройка привязок для служб Windows Communication Foundation
При создании приложения часто нужно отложить решения для администратора после развертывания приложения. Например, часто нет способа узнать заранее, какими будут адрес службы или универсальный код ресурса (URI). Вместо жестко запрограммированного адреса желательно разрешить администратору ввести его после создания службы. Такая гибкость достигается благодаря конфигурации.  
  
> [!NOTE]
>  Используйте [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) с `/config` коммутатора для быстрого создания файлов конфигурации.  
  
## <a name="major-sections"></a>Основные разделы  
 Схема конфигурации Windows Communication Foundation (WCF) включает три основных раздела (`serviceModel`, `bindings`, и `services`):  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <bindings>  
        </bindings>  
        <services>  
        </services>  
        <behaviors>  
        </behaviors>  
    </system.serviceModel>  
</configuration>  
```  
  
### <a name="servicemodel-elements"></a>Элементы ServiceModel  
 Можно использовать раздел, связанный с `system.ServiceModel` элемент, чтобы настроить тип службы с одной или несколькими конечными точками, а также параметры службы. После этого каждая конечная точка может быть настроена с адресом, контрактом и привязкой. Дополнительные сведения о конечных точках см. в разделе [Общие сведения о создании конечной точки](../../../docs/framework/wcf/endpoint-creation-overview.md). Если конечные точки не указаны, то среда выполнения добавит конечные точки по умолчанию. Дополнительные сведения о конечных точек по умолчанию, привязок и поведений см. в разделе [упрощенной конфигурации](../../../docs/framework/wcf/simplified-configuration.md) и [упрощенной конфигурации для служб WCF](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
 Привязка задает транспорт (HTTP, TCP, каналы, очередь сообщений) и протоколы (безопасность, надежность, потоки транзакций) и состоит из элементов привязки, каждый из которых задает определенный аспект способа связи конечной точки с миром.  
  
 Например, при указании [ \<basicHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) элемент указывает на использование протокола HTTP для транспорта для конечной точки. Это используется для подключения конечной точки во время выполнения, когда открыта служба, использующая данную конечную точку.  
  
 Существует два вида привязок: предопределенная и пользовательская. Предопределенные привязки содержат полезные комбинации элементов, которые используются в общих сценариях. Список предварительно определенные привязки типы, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] предоставляет, см. [привязка, предоставляемая системой](../../../docs/framework/wcf/system-provided-bindings.md). Если ни одна из стандартных коллекций привязок не имеет нужного для приложения службы сочетания возможностей, для соответствия требованиям приложения можно создать специальные привязки. Дополнительные сведения о пользовательских привязок см. в разделе [ \<customBinding >](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  
  
 В следующих четырех примерах проиллюстрированы наиболее общие конфигурации привязок, используемые для настройки службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
#### <a name="specifying-an-endpoint-to-use-a-binding-type"></a>Указание конечной точки для использования типа привязки  
 В первом примере показано, как указать конечную точку, настроенную по адресу, контракту и привязке.  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <!—- This section is optional with the default configuration introduced  
       in .NET Framework 4. -->  
  <endpoint   
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />
</service>  
```  
  
 В данном примере атрибут `name` указывает на тип службы, для которой предназначена конфигурация. При создании в коде при помощи контракта `HelloWorld` служба инициализируется со всеми конечными точками, указанными в конфигурации примера. Если сборка реализует только один контракт службы, `name` атрибута может быть опущено, поскольку служба использует единственный имеющийся тип. Атрибут принимает строку, которая должна иметь формат `Namespace.Class, AssemblyName, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null`  
  
 Атрибут `address` указывает универсальный код ресурса (URI), который другие конечные точки используют для связи со службой. Универсальный код ресурса (URI) может быть как абсолютным, так и относительным путем. Если указан относительный адрес, от узла ожидается предоставление базового адреса, подходящего для используемой в привязке схемы транспорта. Если адрес не настроен, в качестве базового адреса используется адрес соответствующей конечной точки.  
  
 Атрибут `contract` задает контракт, который предоставляет данная конечная точка. Тип реализации службы должен реализовывать тип контракта. Если реализация службы реализует один тип контракта, это свойство может быть опущено.  
  
 Атрибут `binding` выбирает предопределенную или специальную привязку для использования в данной конкретной конечной точке. Конечная точка, которая не выбирает привязку явным образом, использует выбор привязки по умолчанию, т. е. `BasicHttpBinding`.  
  
#### <a name="modifying-a-predefined-binding"></a>Изменение предопределенной привязки  
 В следующем примере изменяется заранее заданная привязка. После этого ее можно использовать для настройки любой конечной точки в службе. Привязка изменяется настройкой значения <xref:System.ServiceModel.Configuration.IBindingConfigurationElement.ReceiveTimeout%2A> на 1 секунду. Обратите внимание, что свойство возвращает объект <xref:System.TimeSpan>.  
  
 Эта измененная привязка находится в разделе привязок. Теперь эта измененная привязка может использоваться при создании любой конечной точки путем установки атрибута `binding` в элементе `endpoint`.  
  
> [!NOTE]
>  Если задать определенное имя для привязки, то значение `bindingConfiguration`, указанное в конечной точке службы, должно совпадать с этим именем.  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <endpoint   
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />
</service>  
<bindings>  
    <basicHttpBinding   
        receiveTimeout="00:00:01"  
    />  
</bindings>  
```  
  
## <a name="configuring-a-behavior-to-apply-to-a-service"></a>Настройка поведения для применения к службе  
 В следующем примере специальное поведение настраивается для типа службы. `ServiceMetadataBehavior` Элемент используется для включения [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для запроса к службе и создания документов языка описания веб-служб (WSDL) из метаданных.  
  
> [!NOTE]
>  Если задать определенное имя для поведения, то значение `behaviorConfiguration`, указанное в разделе службы или конечной точки, должно совпадать с этим именем.  
  
```xml  
<behaviors>  
    <behavior>  
        <ServiceMetadata httpGetEnabled="true" />   
    </behavior>  
</behaviors>  
<services>  
    <service   
       name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">
       <endpoint   
          address="http://computer:8080/Hello"  
          contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
          binding="basicHttpBinding" />
    </service>  
</services>  
```  
  
 Предыдущая конфигурация позволяет клиенту вызывать и получать метаданные типизированной службы HelloWorld.  
  
 `svcutil /config:Client.exe.config http://computer:8080/Hello?wsdl`  
  
## <a name="specifying-a-service-with-two-endpoints-using-different-binding-values"></a>Указание службы с двумя конечными точками при помощи различных значений привязки  
 В последнем примере две конечные точки настраиваются для типа службы `HelloWorld`. Каждая конечная точка использует другой настроенные `bindingConfiguration` атрибут того же типа привязки (каждый изменяет `basicHttpBinding`).  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
    <endpoint  
        address="http://computer:8080/Hello1"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="shortTimeout" />
    <endpoint  
        address="http://computer:8080/Hello2"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="Secure" />
</service>  
<bindings>  
    <basicHttpBinding   
        name="shortTimeout"  
        timeout="00:00:00:01"   
     />  
     <basicHttpBinding   
        name="Secure">  
        <Security mode="Transport" />  
     </basicHttpBinding>
</bindings>  
```  
  
 Можно добиться того же поведения с помощью конфигурации по умолчанию, добавив раздел `protocolMapping` и настроив привязки, как показано в следующем примере.  
  
```xml  
<protocolMapping>  
    <add scheme="http" binding="basicHttpBinding" bindingConfiguration="shortTimeout" />  
    <add scheme="https" binding="basicHttpBinding" bindingConfiguration="Secure" />  
</protocolMapping>  
<bindings>  
    <basicHttpBinding   
        name="shortTimeout"  
        timeout="00:00:00:01"   
     />  
     <basicHttpBinding   
        name="Secure" />  
        <Security mode="Transport" />  
</bindings>  
```  
  
## <a name="see-also"></a>См. также  
 [Упрощенная конфигурация](../../../docs/framework/wcf/simplified-configuration.md)  
 [Привязки, предоставляемые системой](../../../docs/framework/wcf/system-provided-bindings.md)  
 [Общие сведения о создании конечных точек](../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [Использование привязок для настройки служб и клиентов](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
