---
title: "Настройка привязок для служб Windows Communication Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "конфигурация привязки [WCF]"
ms.assetid: 99a85fd8-f7eb-4a84-a93e-7721b37d415c
caps.latest.revision: 36
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 36
---
# Настройка привязок для служб Windows Communication Foundation
При создании приложения часто нужно отложить решения для администратора после развертывания приложения.Например, часто нет способа узнать заранее, какими будут адрес службы или универсальный код ресурса \(URI\).Вместо жестко запрограммированного адреса желательно разрешить администратору ввести его после создания службы.Такая гибкость достигается благодаря конфигурации.  
  
> [!NOTE]
>  [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) с параметром `/config` для быстрого создания файлов конфигурации.  
  
## Основные разделы  
 Схема конфигурации [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] включает три основных раздела \(`serviceModel`, `bindings` и `services`\).  
  
```  
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
  
### Элементы ServiceModel  
 Данный раздел, связанный элементом `system.ServiceModel` , можно использовать для конфигурации типа службы с одной или несколькими конечными точками, а также как параметры службы.После этого каждая конечная точка может быть настроена с адресом, контрактом и привязкой.[!INCLUDE[crabout](../../../includes/crabout-md.md)] конечных точках см. в разделе [Общие сведения о создании конечных точек](../../../docs/framework/wcf/endpoint-creation-overview.md).Если конечные точки не указаны, среда выполнения добавляет конечные точки по умолчанию.[!INCLUDE[crabout](../../../includes/crabout-md.md)] о конечных точках по умолчанию, привязках и поведениях см. в разделах [Упрощенная конфигурация](../../../docs/framework/wcf/simplified-configuration.md) и [Упрощенная конфигурация служб WCF](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
 Привязка задает транспорт \(HTTP, TCP, каналы, очередь сообщений\) и протоколы \(безопасность, надежность, потоки транзакций\) и состоит из элементов привязки, каждый из которых задает определенный аспект способа связи конечной точки с миром.  
  
 Например, указание элемента [\<basicHttpBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) задает использование HTTP в качестве транспорта для конечной точки.Это используется для подключения конечной точки во время выполнения, когда открыта служба, использующая данную конечную точку.  
  
 Существует два вида привязок: предопределенная и пользовательская.Предопределенные привязки содержат полезные комбинации элементов, которые используются в общих сценариях.Список имеющихся в [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] типов предопределенных привязок см. в [Привязки, предоставляемые системой](../../../docs/framework/wcf/system-provided-bindings.md).Если ни одна из заранее заданных коллекций привязок не имеет нужного для приложения\-службы сочетания функций, для соответствия требованиям приложения можно создать пользовательские привязки.[!INCLUDE[crabout](../../../includes/crabout-md.md)] пользовательских привязках см. в разделе [\<customBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  
  
 В следующих четырех примерах проиллюстрированы наиболее общие конфигурации привязок, используемые для настройки службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
#### Указание конечной точки для использования типа привязки  
 В первом примере показано, как указать конечную точку, настроенную по адресу, контракту и привязке.  
  
```  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <!—- This section is optional with the default configuration introduced  
       in .NET Framework 4. -->  
  <endpoint   
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />  
  </endpoint>  
</service>  
```  
  
 В данном примере атрибут `name` указывает на тип службы, для которой предназначена конфигурация.При создании в коде при помощи контракта `HelloWorld` служба инициализируется со всеми конечными точками, указанными в конфигурации примера.Если сборка реализует только один контракт службы, атрибут `name` может быть опущен, поскольку служба использует единственный имеющийся тип.Атрибут принимает строку, которая должна иметь формат `Namespace.Class, AssemblyName, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null`  
  
 Атрибут `address` указывает универсальный код ресурса \(URI\), который другие конечные точки используют для связи со службой.Универсальный код ресурса \(URI\) может быть как абсолютным, так и относительным путем.Если указан относительный адрес, от узла ожидается предоставление базового адреса, подходящего для используемой в привязке схемы транспорта.Если адрес не настроен, в качестве базового адреса используется адрес соответствующей конечной точки.  
  
 Атрибут `contract` задает контракт, который предоставляет данная конечная точка.Тип реализации службы должен реализовывать тип контракта.Если реализация службы реализует один тип контракта, это свойство может быть опущено.  
  
 Атрибут `binding` выбирает предопределенную или специальную привязку для использования в данной конкретной конечной точке.Конечная точка, которая не выбирает привязку явным образом, использует выбор привязки по умолчанию, т. е. `BasicHttpBinding`.  
  
#### Изменение предопределенной привязки  
 В следующем примере изменяется заранее заданная привязка.После этого ее можно использовать для настройки любой конечной точки в службе.Привязка изменяется настройкой значения <xref:System.ServiceModel.Configuration.IBindingConfigurationElement.ReceiveTimeout%2A> на 1 секунду.Обратите внимание, что свойство возвращает объект <xref:System.TimeSpan>.  
  
 Эта измененная привязка находится в разделе привязок.Теперь эта измененная привязка может использоваться при создании любой конечной точки путем установки атрибута `binding` в элементе `endpoint`.  
  
> [!NOTE]
>  Если задать определенное имя для привязки, то значение `bindingConfiguration`, указанное в конечной точке службы, должно совпадать с этим именем.  
  
```  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <endpoint   
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />  
  </endpoint>  
</service>  
<bindings>  
    <basicHttpBinding   
        receiveTimeout="00:00:01"  
    />  
</bindings>  
```  
  
## Настройка поведения для применения к службе  
 В следующем примере специальное поведение настраивается для типа службы.Элемент `ServiceMetadataBehavior` используется, чтобы разрешить [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) делать запрос в службу и создавать документы на языке WSDL из метаданных.  
  
> [!NOTE]
>  Если задать определенное имя для поведения, то значение `behaviorConfiguration`, указанное в разделе службы или конечной точки, должно совпадать с этим именем.  
  
```  
<behaviors>  
    <behavior>  
        <ServiceMetadata httpGetEnabled="true" />   
    </behavior>  
</behaviors>  
<services>  
    <service   
       name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
       <endpoint   
          address="http://computer:8080/Hello"  
          contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
          binding="basicHttpBinding" />  
       </endpoint>  
    </service>  
</services>  
```  
  
 Предыдущая конфигурация позволяет клиенту вызывать и получать метаданные типизированной службы HelloWorld.  
  
 `svcutil /config:Client.exe.config http://computer:8080/Hello?wsdl`  
  
## Указание службы с двумя конечными точками при помощи различных значений привязки  
 В последнем примере две конечные точки настраиваются для типа службы `HelloWorld`.Каждая конечная точка использует отдельный настроенный атрибут `bindingConfiguration` с тем же типом привязки \(каждая точка изменяет `basicHttpBinding`\).  
  
```  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
    <endpoint  
        address="http://computer:8080/Hello1"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="shortTimeout"  
    </endpoint>  
    <endpoint  
        address="http://computer:8080/Hello2"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="Secure"  
     </endpoint>  
</service>  
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
  
 Можно добиться того же поведения с помощью конфигурации по умолчанию, добавив раздел `protocolMapping` и настроив привязки, как показано в следующем примере.  
  
```xml  
<protocolMapping>  
    <add scheme=”http” binding=”basicHttpBinding” bindingConfiguration=”shortTimeout” />  
    <add scheme=”https” binding=”basicHttpBinding” bindingConfiguration=”Secure” />  
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
  
## См. также  
 [Упрощенная конфигурация](../../../docs/framework/wcf/simplified-configuration.md)   
 [Привязки, предоставляемые системой](../../../docs/framework/wcf/system-provided-bindings.md)   
 [Общие сведения о создании конечных точек](../../../docs/framework/wcf/endpoint-creation-overview.md)   
 [Использование привязок для настройки служб и клиентов](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)