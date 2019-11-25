---
title: Конфигурация клиента
ms.date: 03/30/2017
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
ms.openlocfilehash: 6a5cbf5d536af8649b0b8bb93600e94a48c507c1
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141767"
---
# <a name="client-configuration"></a>Конфигурация клиента
Можно использовать конфигурацию клиента Windows Communication Foundation (WCF) для указания адреса, привязки, поведения и контракта, свойств "ABC" клиентской конечной точки, которые клиенты используют для подключения к конечным точкам службы. Элемент [> клиента\<](../../configure-apps/file-schema/wcf/client.md) имеет элемент [\<конечной точки >](../../configure-apps/file-schema/wcf/endpoint-of-client.md) , атрибуты которого используются для настройки конечной точки ABCs. Эти атрибуты обсуждаются в разделе [Настройка конечных точек](#configuring-endpoints) .  
  
 Элемент [\<конечная точка >](../../configure-apps/file-schema/wcf/endpoint-of-client.md) также содержит элемент [\<метаданных >](../../configure-apps/file-schema/wcf/metadata.md) , который используется для задания параметров импорта и экспорта метаданных,\<> [headers](../../configure-apps/file-schema/wcf/headers.md) , содержащего коллекцию настраиваемых заголовков адресов, и элемент [\<Identity >](../../configure-apps/file-schema/wcf/identity.md) , который обеспечивает проверку подлинности конечной точки другими конечными точками, которые обмениваются сообщениями. Элементы [\<headers >](../../configure-apps/file-schema/wcf/headers.md) и [\<Identity >](../../configure-apps/file-schema/wcf/identity.md) являются частью <xref:System.ServiceModel.EndpointAddress> и рассматриваются в статье [адреса](../../wcf/feature-details/endpoint-addresses.md) . Ссылки на разделы, в которых объясняется использование расширений метаданных, приведены в разделе [Настройка метаданных](#configuring-metadata) .  
  
## <a name="configuring-endpoints"></a>Настройка конечных точек  
 Конфигурация клиента позволяет клиенту указать одну или несколько конечных точек, каждый из которых имеет собственное имя, адрес и контракт, с каждой ссылкой на [\<привязки >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) и [\<поведения >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) элементов в конфигурации клиента, которые будут использоваться для настройки этой конечной точки. Файл конфигурации клиента должен называться "App. config", так как это имя, которое требуется среде выполнения WCF. В следующем примере показан файл конфигурации клиента.  
  
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
  
 Необязательный атрибут `name` уникальным образом идентифицирует конечную точку для данного контракта. Он используется методом <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> или <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> для задания целевой конечной точки в конфигурации клиента, которая должна быть загружена при создании канала к службе. Имя конфигурации конечной точки с подстановочным знаком "\*" доступно и указывает методу <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A>, что он должен загрузить любую конфигурацию конечной точки в файле, при условии, что имеется только один доступный объект, и в противном случае вызывает исключение. Если этот атрибут опущен, соответствующая конечная точка используется как конечная точка по умолчанию, связанная с заданным типом контракта. Значением по умолчанию для атрибута `name` является пустая строка, соответствие для которой проверяется так же, как и для любого другого имени.  
  
 С каждой конечной точкой связан адрес, который используется для поиска и идентификации этой конечной точки. Атрибут `address` может использоваться для указания URL-адреса, задающего расположение конечной точки. Однако адрес для конечной точки службы может также быть задан в коде путем создания универсального кода ресурса (URI), и он добавляется в <xref:System.ServiceModel.ServiceHost> с помощью одного из методов <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>. Дополнительные сведения см. в разделе [адреса](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md). Как указано в введении, [\<заголовки >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) и [\<идентификаторы >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) являются частью <xref:System.ServiceModel.EndpointAddress> и также рассматриваются в разделе [адреса](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) .  
  
 Атрибут `binding` задает тип привязки, использование которого ожидается в конечной точке при подключении к службе. Для того чтобы на тип можно было ссылаться, он должен иметь зарегистрированный раздел конфигурации. В предыдущем примере это раздел [\<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) , который указывает, что конечная точка использует <xref:System.ServiceModel.WSHttpBinding>. Однако могут существовать несколько привязок указанного типа, которые могут использоваться конечной точкой. Каждый из них имеет собственную [\<привязки >](../../configure-apps/file-schema/wcf/bindings.md) элемент в элементе типа (Binding). Для различения привязок одного типа служит атрибут `bindingconfiguration`. Его значение соответствует атрибуту `name` элемента [> привязки\<](../../configure-apps/file-schema/wcf/bindings.md) . Дополнительные сведения о настройке привязки клиента с помощью конфигурации см. в разделе [инструкции. Указание привязки клиента в конфигурации](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md).  
  
 Атрибут `behaviorConfiguration` используется для указания того, какое [поведение\<](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) [\<EndpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) , которое должна использовать конечная точка. Его значение соответствует атрибуту `name` элемента [> поведения\<](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) . Пример использования конфигурации для указания поведения клиента см. в разделе [Настройка поведения клиента](../../../../docs/framework/wcf/configuring-client-behaviors.md).  
  
 Атрибут `contract` задает контракт, который предоставляет данная конечная точка. Это значение соответствует свойству <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> атрибута <xref:System.ServiceModel.ServiceContractAttribute>. Значение по умолчанию - это полное имя типа класса, реализующего службу.  
  
### <a name="configuring-metadata"></a>Настройка метаданных  
 Элемент [> метаданных\<](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) используется для указания параметров, используемых для регистрации расширений импорта метаданных. Дополнительные сведения о расширении системы метаданных см. в разделе [расширение системы метаданных](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md).  
  
## <a name="see-also"></a>См. также

- [Конечные точки: адреса, привязки и контракты](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [Настройка поведения клиентов](../../../../docs/framework/wcf/configuring-client-behaviors.md)
