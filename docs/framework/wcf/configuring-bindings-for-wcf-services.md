---
title: Настройка привязок для служб Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- binding configuration [WCF]
ms.assetid: 99a85fd8-f7eb-4a84-a93e-7721b37d415c
ms.openlocfilehash: e7ee1a8ce358c77e46db39af67bd9dc20114fb3b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174827"
---
# <a name="configuring-bindings-for-windows-communication-foundation-services"></a>Настройка привязок для служб Windows Communication Foundation
При создании приложения часто нужно отложить решения для администратора после развертывания приложения. Например, часто нет способа узнать заранее, какими будут адрес службы или универсальный код ресурса (URI). Вместо жестко запрограммированного адреса желательно разрешить администратору ввести его после создания службы. Такая гибкость достигается благодаря конфигурации.  
  
> [!NOTE]
> Используйте [инструмент Utility Tool ServiceModel Metadata (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) с переходом `/config` для быстрого создания файлов конфигурации.  
  
## <a name="major-sections"></a>Основные разделы  
 Схема конфигурации Windows Communication Foundation (WCF) включает`serviceModel` `bindings`в `services`себя следующие три основных раздела (, и):  
  
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
 Раздел, ограниченный `system.ServiceModel` элементом, можно настроить тип службы с одной или более конечными точками, а также настройками службы. После этого каждая конечная точка может быть настроена с адресом, контрактом и привязкой. Для получения дополнительной информации о конечных точках, см [Endpoint Создание Обзор](endpoint-creation-overview.md). Если конечные точки не указаны, то среда выполнения добавит конечные точки по умолчанию. Дополнительные сведения о конечных точках по умолчанию, привязках и режимах работы см. в разделах [Упрощенная конфигурация](simplified-configuration.md) и [Упрощенная конфигурация служб WCF](./samples/simplified-configuration-for-wcf-services.md).  
  
 Привязка задает транспорт (HTTP, TCP, каналы, очередь сообщений) и протоколы (безопасность, надежность, потоки транзакций) и состоит из элементов привязки, каждый из которых задает определенный аспект способа связи конечной точки с миром.  
  
 Например, указание [ \<элемента basicHttpBinding>](../configure-apps/file-schema/wcf/basichttpbinding.md) указывает на использование HTTP в качестве переноса для конечных точек. Это используется для подключения конечной точки во время выполнения, когда открыта служба, использующая данную конечную точку.  
  
 Существует два вида привязок: предопределенная и пользовательская. Предопределенные привязки содержат полезные комбинации элементов, которые используются в общих сценариях. Для списка предопределенных типов связывания, [System-Provided Bindings](system-provided-bindings.md)которые предоставляет WCF, см. Если ни одна из стандартных коллекций привязок не имеет нужного для приложения службы сочетания возможностей, для соответствия требованиям приложения можно создать специальные привязки. Для получения дополнительной информации о пользовательских привязок, см [ \<пользовательскихОбязательные>](../configure-apps/file-schema/wcf/custombinding.md).  
  
 Следующие четыре примера иллюстрируют наиболее распространенные обязательные конфигурации, используемые для настройки службы WCF.  
  
#### <a name="specifying-an-endpoint-to-use-a-binding-type"></a>Указание конечной точки для использования типа привязки  
 В первом примере показано, как указать конечную точку, настроенную по адресу, контракту и привязке.  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <!-- This section is optional with the default configuration introduced  
       in .NET Framework 4. -->  
  <endpoint
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />
</service>  
```  
  
 В данном примере атрибут `name` указывает на тип службы, для которой предназначена конфигурация. При создании в коде при помощи контракта `HelloWorld` служба инициализируется со всеми конечными точками, указанными в конфигурации примера. Если сборка выполняет только один `name` контракт службы, атрибут может быть опущен, поскольку служба использует единственный доступный тип. Атрибут принимает строку, которая должна иметь формат `Namespace.Class, AssemblyName, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null`  
  
 Атрибут `address` указывает универсальный код ресурса (URI), который другие конечные точки используют для связи со службой. Универсальный код ресурса (URI) может быть как абсолютным, так и относительным путем. Если указан относительный адрес, от узла ожидается предоставление базового адреса, подходящего для используемой в привязке схемы транспорта. Если адрес не настроен, в качестве базового адреса используется адрес соответствующей конечной точки.  
  
 Атрибут `contract` задает контракт, который предоставляет данная конечная точка. Тип реализации службы должен реализовывать тип контракта. Если реализация службы реализует один тип контракта, это свойство может быть опущено.  
  
 Атрибут `binding` выбирает предопределенную или специальную привязку для использования в данной конкретной конечной точке. Конечная точка, которая не выбирает привязку явным образом, использует выбор привязки по умолчанию, т. е. `BasicHttpBinding`.  
  
#### <a name="modifying-a-predefined-binding"></a>Изменение предопределенной привязки  
 В следующем примере изменяется заранее заданная привязка. После этого ее можно использовать для настройки любой конечной точки в службе. Привязка изменяется настройкой значения <xref:System.ServiceModel.Configuration.IBindingConfigurationElement.ReceiveTimeout%2A> на 1 секунду. Обратите внимание, что свойство возвращает объект <xref:System.TimeSpan>.  
  
 Эта измененная привязка находится в разделе привязок. Теперь эта измененная привязка может использоваться при создании любой конечной точки путем установки атрибута `binding` в элементе `endpoint`.  
  
> [!NOTE]
> Если задать определенное имя для привязки, то значение `bindingConfiguration`, указанное в конечной точке службы, должно совпадать с этим именем.  
  
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
 В следующем примере специальное поведение настраивается для типа службы. Элемент `ServiceMetadataBehavior` используется для того, чтобы позволить [Utility Tool ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) задать запрос службы и создать документы языка описания web-сервисов (WSDL) из метаданных.  
  
> [!NOTE]
> Если задать определенное имя для поведения, то значение `behaviorConfiguration`, указанное в разделе службы или конечной точки, должно совпадать с этим именем.  
  
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
 В последнем примере две конечные точки настраиваются для типа службы `HelloWorld`. Каждая конечная точка `bindingConfiguration` использует различные индивидуальные атрибуты `basicHttpBinding`одного и того же типа связывания (каждая изменяет).  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Упрощенная конфигурация](simplified-configuration.md)
- [Привязки, предоставляемые системой](system-provided-bindings.md)
- [Общие сведения о создании конечных точек](endpoint-creation-overview.md)
- [Использование привязок для настройки служб и клиентов](using-bindings-to-configure-services-and-clients.md)
