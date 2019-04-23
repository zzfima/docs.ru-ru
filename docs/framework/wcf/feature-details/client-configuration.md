---
title: Конфигурация клиента
ms.date: 03/30/2017
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
ms.openlocfilehash: b9975c6caeedc94bf4a7773e71a95eb0d8c7aed2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59144694"
---
# <a name="client-configuration"></a>Конфигурация клиента
Конфигурация клиента Windows Communication Foundation (WCF) можно использовать для указания адреса, привязки, поведения и контракта, «ABC» свойства конечной точки клиента, которые используются клиентами для подключения к конечным точкам службы. [ \<Клиента >](../../configure-apps/file-schema/wcf/client.md) элемент имеет [ \<конечной точки >](../../configure-apps/file-schema/wcf/endpoint-of-client.md) элемент, атрибуты которого используются для настройки основополагающих свойств конечной точки. Эти атрибуты описаны в [Настройка конечных точек](#configuring-endpoints) раздел.  
  
 [ \<Конечной точки >](../../configure-apps/file-schema/wcf/endpoint-of-client.md) элемент также содержит [ \<метаданных >](../../configure-apps/file-schema/wcf/metadata.md) элемент, который используется для задания параметров импорта и экспорта метаданных, [ \<заголовки >](../../configure-apps/file-schema/wcf/headers.md) элемент, содержащий коллекцию пользовательских адресных заголовков, и [ \<удостоверений >](../../configure-apps/file-schema/wcf/identity.md) элемент, который позволяет выполнять проверку подлинности конечной точки другими конечными точками обмен сообщениями с ним. [ \<Заголовки >](../../configure-apps/file-schema/wcf/headers.md) и [ \<удостоверений >](../../configure-apps/file-schema/wcf/identity.md) элементы являются частью <xref:System.ServiceModel.EndpointAddress> и обсуждаются в [адреса](../../wcf/feature-details/endpoint-addresses.md) статьи. Ссылки на разделы, объясняющие использование расширений метаданных приведены в [Настройка метаданных](#configuring-metadata) раздел.  
  
## <a name="configuring-endpoints"></a>Настройка конечных точек  
 Конфигурация клиента позволяет клиенту задавать одну или несколько конечных точек, каждая со своим именем, адресом и контрактом, ссылающихся на [ \<привязки >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) и [ \< варианты поведения >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) элементов в конфигурации клиента, который будет использоваться для настройки этих конечных точек. В файле конфигурации клиента должен называться «App.config», так как это имя, которое ожидает, что среда выполнения WCF. В следующем примере показан файл конфигурации клиента.  
  
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
  
 Необязательный атрибут `name` уникальным образом идентифицирует конечную точку для данного контракта. Он используется методом <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> или <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> для задания целевой конечной точки в конфигурации клиента, которая должна быть загружена при создании канала к службе. Имя конфигурации конечной точки с подстановочными знаками "\*" доступна и указывает <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> что следует загрузить Любая конфигурация конечной точки в файле, если имеется ровно одна доступна и в противном случае вызывается исключение. Если этот атрибут опущен, соответствующая конечная точка используется как конечная точка по умолчанию, связанная с заданным типом контракта. Значением по умолчанию для атрибута `name` является пустая строка, соответствие для которой проверяется так же, как и для любого другого имени.  
  
 С каждой конечной точкой связан адрес, который используется для поиска и идентификации этой конечной точки. Атрибут `address` может использоваться для указания URL-адреса, задающего расположение конечной точки. Однако адрес для конечной точки службы может также быть задан в коде путем создания универсального кода ресурса (URI), и он добавляется в <xref:System.ServiceModel.ServiceHost> с помощью одного из методов <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>. Дополнительные сведения см. в разделе [адреса](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md). Как указано во введении, [ \<заголовки >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) и [ \<удостоверений >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) элементы являются частью <xref:System.ServiceModel.EndpointAddress> и обсуждаются также в [ Адреса](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) раздела.  
  
 Атрибут `binding` задает тип привязки, использование которого ожидается в конечной точке при подключении к службе. Для того чтобы на тип можно было ссылаться, он должен иметь зарегистрированный раздел конфигурации. В предыдущем примере это [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) секции, которая указывает, что конечная точка использует <xref:System.ServiceModel.WSHttpBinding>. Однако могут существовать несколько привязок указанного типа, которые могут использоваться конечной точкой. Каждая из них имеет свой собственный [ \<привязки >](../../../../docs/framework/misc/binding.md) элемента в элементе типа (привязки). Для различения привязок одного типа служит атрибут `bindingconfiguration`. Его значение соответствует `name` атрибут [ \<привязки >](../../../../docs/framework/misc/binding.md) элемент. Дополнительные сведения о том, как настроить клиент привязки с использованием конфигурации, см. в разделе [как: Указание привязки клиента в конфигурации](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md).  
  
 `behaviorConfiguration` Атрибут используется для указания [ \<поведение >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) из [ \<endpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) должна использоваться конечной точкой. Его значение соответствует `name` атрибут [ \<поведение >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) элемент. Пример использования конфигурации для задания поведений клиента, см. в разделе [Настройка поведений клиента](../../../../docs/framework/wcf/configuring-client-behaviors.md).  
  
 Атрибут `contract` задает контракт, который предоставляет данная конечная точка. Это значение соответствует свойству <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> атрибута <xref:System.ServiceModel.ServiceContractAttribute>. Значение по умолчанию - это полное имя типа класса, реализующего службу.  
  
### <a name="configuring-metadata"></a>Настройка метаданных  
 [ \<Метаданных >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) элемент используется для задания параметров, используемых для регистрации метаданных расширений импорта. Дополнительные сведения о расширении системы метаданных см. в разделе [расширении системы метаданных](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md).  
  
## <a name="see-also"></a>См. также

- [Конечные точки: Адреса, привязки и контракты](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [Настройка поведения клиентов](../../../../docs/framework/wcf/configuring-client-behaviors.md)
