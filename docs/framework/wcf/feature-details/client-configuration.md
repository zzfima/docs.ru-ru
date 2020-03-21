---
title: Конфигурация клиента
ms.date: 03/30/2017
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
ms.openlocfilehash: ff82f56639ec451c04624d22fff0bcb03f46d946
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185363"
---
# <a name="client-configuration"></a>Конфигурация клиента
Вы можете использовать конфигурацию клиента Windows Communication Foundation (WCF) для указания адреса, связывания, поведения и контракта, свойств "ABC" конечной точки клиента, которые клиенты используют для подключения к конечным точкам обслуживания. [ \<Элемент>клиента](../../configure-apps/file-schema/wcf/client.md) имеет элемент>[ \<конечным элементом,](../../configure-apps/file-schema/wcf/endpoint-of-client.md) атрибуты которого используются для настройки ABCs конечных точек. Эти атрибуты обсуждаются в разделе [Настройка конечных точек.](#configuring-endpoints)  
  
 Элемент [ \<>также](../../configure-apps/file-schema/wcf/endpoint-of-client.md) содержит [ \<элемент метаданных>,](../../configure-apps/file-schema/wcf/metadata.md) который используется для определения параметров импорта и экспорта метаданных, элемент [ \<заголовков>,](../../configure-apps/file-schema/wcf/headers.md) содержащий набор пользовательских заголовков адресов, и элемент [ \<>идентификации,](../../configure-apps/file-schema/wcf/identity.md) позволяющий аутентификацию конечной точки другими конечными точками обмениваться с ним сообщениями. [ \<Заголовки>](../../configure-apps/file-schema/wcf/headers.md) и <xref:System.ServiceModel.EndpointAddress> [ \<элементы идентификационных>](../../configure-apps/file-schema/wcf/identity.md) являются частью статьи [Addresses.](../../wcf/feature-details/endpoint-addresses.md) Ссылки на темы, объясняющие использование расширений метаданных, приведены в разделе [«Настройка метаданных».](#configuring-metadata)  
  
## <a name="configuring-endpoints"></a>Настройка конечных точек  
 Конфигурация клиента предназначена для того, чтобы клиент мог указать одну или несколько конечных точек, каждую со своим именем, адресом и контрактом, при каждой ссылке на [ \<привязки>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) и [ \<поведение>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) элементов в конфигурации клиента, которые будут использоваться для настройки этой конечной точки. Файл конфигурации клиента должен называться "App.config", потому что это имя, которое ожидает время выполнения WCF. В следующем примере показан файл конфигурации клиента.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
        <client>  
          <endpoint  
            name="endpoint1"  
            address="http://localhost/ServiceModelSamples/service.svc"  
            binding="wsHttpBinding"  
            bindingConfiguration="WSHttpBinding_IHello"  
            behaviorConfiguration="IHello_Behavior"  
            contract="IHello" >  
  
            <metadata>  
              <wsdlImporters>  
                <extension  
                  type="Microsoft.ServiceModel.Samples.WsdlDocumentationImporter, WsdlDocumentation"/>  
              </wsdlImporters>  
            </metadata>  
  
            <identity>  
              <servicePrincipalName value="host/localhost" />  
            </identity>  
          </endpoint>  
// Add another endpoint by adding another <endpoint> element.  
          <endpoint  
            name="endpoint2">  
           //Configure another endpoint here.  
          </endpoint>  
        </client>  
  
//The bindings section references by the bindingConfiguration endpoint attribute.  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_IHello"
                 bypassProxyOnLocal="false"
                 hostNameComparisonMode="StrongWildcard">  
          <readerQuotas maxDepth="32"/>  
          <reliableSession ordered="true"
                           enabled="false" />  
          <security mode="Message">  
           //Security settings go here.  
          </security>  
        </binding>  
        <binding name="Another Binding"  
        //Configure this binding here.  
        </binding>  
          </wsHttpBinding>  
        </bindings>  
  
//The behavior section references by the behaviorConfiguration endpoint attribute.  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name=" IHello_Behavior ">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
  
    </system.serviceModel>  
</configuration>  
```  
  
 Необязательный атрибут `name` уникальным образом идентифицирует конечную точку для данного контракта. Он используется методом <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> или <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> для задания целевой конечной точки в конфигурации клиента, которая должна быть загружена при создании канала к службе. Имя конфигурации конфигурации\*конфигурации подстановочных <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> знаков " доступно и указывает методу, что он должен загрузить любую конфигурацию конечных точек в файле, при условии, что имеется точно одна из доступных и в противном случае бросает исключение. Если этот атрибут опущен, соответствующая конечная точка используется как конечная точка по умолчанию, связанная с заданным типом контракта. Значением по умолчанию для атрибута `name` является пустая строка, соответствие для которой проверяется так же, как и для любого другого имени.  
  
 С каждой конечной точкой связан адрес, который используется для поиска и идентификации этой конечной точки. Атрибут `address` может использоваться для указания URL-адреса, задающего расположение конечной точки. Однако адрес для конечной точки службы может также быть задан в коде путем создания универсального кода ресурса (URI), и он добавляется в <xref:System.ServiceModel.ServiceHost> с помощью одного из методов <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>. Для получения дополнительной информации [см.](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) Как указывается во введении, [ \<заголовки>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) <xref:System.ServiceModel.EndpointAddress> и [ \<элементы>идентификации](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) являются частью и также обсуждаются в теме [Адреса.](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)  
  
 Атрибут `binding` задает тип привязки, использование которого ожидается в конечной точке при подключении к службе. Для того чтобы на тип можно было ссылаться, он должен иметь зарегистрированный раздел конфигурации. В предыдущем примере это раздел [ \<wsHttpBinding>,](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) который указывает <xref:System.ServiceModel.WSHttpBinding>на то, что конечная точка использует . Однако могут существовать несколько привязок указанного типа, которые могут использоваться конечной точкой. Каждый из них имеет свой собственный [ \<связывающий элемент>](../../configure-apps/file-schema/wcf/bindings.md) элементв (обязательный) элемент типа. Для различения привязок одного типа служит атрибут `bindingconfiguration`. Его значение сопоставляется `name` с атрибутом [ \<связывающего элемента>.](../../configure-apps/file-schema/wcf/bindings.md) Для получения дополнительной информации о том, как настроить привязку клиента с помощью конфигурации, [см.](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)  
  
 Атрибут `behaviorConfiguration` используется для определения [ \<того,](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) какое поведение>[ \<конечных точекПоведение>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) конечной точке должна использоваться. Его значение сопоставляется `name` с атрибутом [ \<поведения>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) элементом. Например, при использовании конфигурации для указания поведения клиента [см.](../../../../docs/framework/wcf/configuring-client-behaviors.md)  
  
 Атрибут `contract` задает контракт, который предоставляет данная конечная точка. Это значение соответствует свойству <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> атрибута <xref:System.ServiceModel.ServiceContractAttribute>. Значение по умолчанию - это полное имя типа класса, реализующего службу.  
  
### <a name="configuring-metadata"></a>Настройка метаданных  
 [ \<Элемент метаданных>](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) используется для определения параметров, используемых для регистрации расширений импорта метаданных. Для получения дополнительной информации о расширении системы метаданных [см.](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)  
  
## <a name="see-also"></a>См. также раздел

- [Конечные точки: адреса, привязки и контракты](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [Настройка поведения клиентов](../../../../docs/framework/wcf/configuring-client-behaviors.md)
