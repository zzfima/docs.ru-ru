---
title: Конфигурация клиента
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 19d1f7630c96f557791f0682fbc0c5d7286c7eb7
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="client-configuration"></a><span data-ttu-id="e1e1c-102">Конфигурация клиента</span><span class="sxs-lookup"><span data-stu-id="e1e1c-102">Client Configuration</span></span>
<span data-ttu-id="e1e1c-103">Конфигурацию клиента [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] можно использовать для задания адреса, привязки, поведения и контракта - основополагающих свойств конечной точки клиента, которая используется клиентом для подключения к конечным точкам службы.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-103">You can use the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client configuration to specify the address, binding, behavior, and contract, the "ABC" properties of the client endpoint, which clients use to connect to service endpoints.</span></span> <span data-ttu-id="e1e1c-104">[ \<Клиента >](../../../../docs/framework/configure-apps/file-schema/wcf/client.md) элемент имеет [ \<endpoint >](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) элемент, атрибуты которого используются для настройки основополагающих свойств конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-104">The [\<client>](../../../../docs/framework/configure-apps/file-schema/wcf/client.md) element has an [\<endpoint>](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) element whose attributes are used to configure the endpoint ABCs.</span></span> <span data-ttu-id="e1e1c-105">Эти атрибуты обсуждаются в подразделе "Настройка конечных точек" данного раздела.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-105">These attributes are discussed in the "Configuring Endpoints" section of this topic.</span></span>  
  
 <span data-ttu-id="e1e1c-106">[ \<Endpoint >](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) элемент также содержит [ \<метаданных >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) элемент, используемый для задания параметров импорта и экспорта метаданных, [ \<заголовки >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) элемент, содержащий коллекцию заголовков настраиваемый адрес, и [ \<удостоверение >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) элемент, который позволяет выполнять проверку подлинности конечной точки другими конечными точками обмен сообщениями с ним.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-106">The [\<endpoint>](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) element also contains a [\<metadata>](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) element that is used to specify settings for importing and exporting metadata , a [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) element that contains a collection of custom address headers, and an [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) element that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span> <span data-ttu-id="e1e1c-107">[ \<Заголовки >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) и [ \<удостоверение >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) элементы являются частью <xref:System.ServiceModel.EndpointAddress> и обсуждаются в [адреса](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-107">The [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are discussed in the [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) topic.</span></span> <span data-ttu-id="e1e1c-108">Ссылки на разделы, в которых рассматривается использование расширений метаданных, приведены в подразделе "Настройка метаданных" данного раздела.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-108">Links to topics that explain the use of metadata extensions are provided in the Configuring Metadata sub-section of this topic.</span></span>  
  
## <a name="configuring-endpoints"></a><span data-ttu-id="e1e1c-109">Настройка конечных точек</span><span class="sxs-lookup"><span data-stu-id="e1e1c-109">Configuring Endpoints</span></span>  
 <span data-ttu-id="e1e1c-110">Конфигурация клиента позволяет клиенту задавать одну или несколько конечных точек, каждая со своим именем, адресом и контрактом, ссылающихся на [ \<привязки >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) и [ \< поведения >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) элементов в конфигурации клиента, который будет использоваться для настройки этих конечных точек.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-110">The client configuration is designed to allow the client to specify one or more endpoints, each with its own name, address, and contract, with each referencing the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) and [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elements in the client configuration to be used to configure that endpoint.</span></span> <span data-ttu-id="e1e1c-111">Файл конфигурации клиента должен называться "App.config", так как это имя ожидается средой выполнения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1e1c-111">The client configuration file should be named "App.config" because this is the name that the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] runtime expects.</span></span> <span data-ttu-id="e1e1c-112">В следующем примере показан файл конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-112">The following example shows a client configuration file.</span></span>  
  
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
  
 <span data-ttu-id="e1e1c-113">Необязательный атрибут `name` уникальным образом идентифицирует конечную точку для данного контракта.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-113">The optional `name` attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="e1e1c-114">Он используется методом <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> или <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> для задания целевой конечной точки в конфигурации клиента, которая должна быть загружена при создании канала к службе.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-114">It is used by the <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> or by the <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> to specify which endpoint in the client configuration is being targeted and must be loaded when a channel is created to service.</span></span> <span data-ttu-id="e1e1c-115">Предусмотрено подстановочное имя "\*" конечной точки в конфигурации, которое указывает методу <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A>, что следует загрузить любую конфигурацию конечной точки из файла, при условии, что имеется ровно одна конфигурация, а в противном случае создать исключение.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-115">A wildcard endpoint configuration name "\*" is available and indicates to the <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> method that it should load any endpoint configuration in the file, provided there is precisely one available, and otherwise throws an exception.</span></span> <span data-ttu-id="e1e1c-116">Если этот атрибут опущен, соответствующая конечная точка используется как конечная точка по умолчанию, связанная с заданным типом контракта.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-116">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified contract type.</span></span> <span data-ttu-id="e1e1c-117">Значением по умолчанию для атрибута `name` является пустая строка, соответствие для которой проверяется так же, как и для любого другого имени.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-117">The default value for the `name` attribute is an empty string which is matched like any other name.</span></span>  
  
 <span data-ttu-id="e1e1c-118">С каждой конечной точкой связан адрес, который используется для поиска и идентификации этой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-118">Every endpoint must have an address associated with it to locate and identify the endpoint.</span></span> <span data-ttu-id="e1e1c-119">Атрибут `address` может использоваться для указания URL-адреса, задающего расположение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-119">The `address` attribute can be used to specify the URL that provides the location of the endpoint.</span></span> <span data-ttu-id="e1e1c-120">Однако адрес для конечной точки службы может также быть задан в коде путем создания универсального кода ресурса (URI), и он добавляется в <xref:System.ServiceModel.ServiceHost> с помощью одного из методов <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-120">But the address for a service endpoint can also be specified in code by creating a Uniform Resource Identifier (URI) and is added to the <xref:System.ServiceModel.ServiceHost> using one of the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> methods.</span></span> <span data-ttu-id="e1e1c-121">Дополнительные сведения см. в разделе [адреса](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md).</span><span class="sxs-lookup"><span data-stu-id="e1e1c-121">For more information, see [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md).</span></span> <span data-ttu-id="e1e1c-122">При введении указывает, [ \<заголовки >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) и [ \<удостоверение >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) элементы являются частью <xref:System.ServiceModel.EndpointAddress> и обсуждаются также в [ Адреса](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-122">As the introduction indicates, the [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are also discussed in the [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) topic.</span></span>  
  
 <span data-ttu-id="e1e1c-123">Атрибут `binding` задает тип привязки, использование которого ожидается в конечной точке при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-123">The `binding` attribute indicates the type of binding the endpoint expects to use when connecting to a service.</span></span> <span data-ttu-id="e1e1c-124">Для того чтобы на тип можно было ссылаться, он должен иметь зарегистрированный раздел конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-124">The type must have a registered configuration section if it is to be referenced.</span></span> <span data-ttu-id="e1e1c-125">В предыдущем примере это [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) секции, которая указывает, что конечная точка использует <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-125">In the previous example, this is the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) section, which indicates that the endpoint uses a <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="e1e1c-126">Однако могут существовать несколько привязок указанного типа, которые могут использоваться конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-126">But there may be more than one binding of a given type that the endpoint can use.</span></span> <span data-ttu-id="e1e1c-127">Каждый из них имеет свой собственный [ \<привязки >](../../../../docs/framework/misc/binding.md) элемент в элементе типа (привязки).</span><span class="sxs-lookup"><span data-stu-id="e1e1c-127">Each of these has its own [\<binding>](../../../../docs/framework/misc/binding.md) element within the (binding) type element.</span></span> <span data-ttu-id="e1e1c-128">Для различения привязок одного типа служит атрибут `bindingconfiguration`.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-128">The `bindingconfiguration` attribute is used to distinguish between bindings of the same type.</span></span> <span data-ttu-id="e1e1c-129">Его значение соответствует `name` атрибут [ \<привязки >](../../../../docs/framework/misc/binding.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-129">Its value is matched with the `name` attribute of the [\<binding>](../../../../docs/framework/misc/binding.md) element.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="e1e1c-130"> Настройка клиента привязки с помощью конфигурации см. в разделе [как: Указание привязки клиента в конфигурации](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="e1e1c-130"> how to configure a client binding using configuration, see [How to: Specify a Client Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md).</span></span>  
  
 <span data-ttu-id="e1e1c-131">`behaviorConfiguration` Атрибут используется для указания [ \<поведение >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) из [ \<endpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) конечная точка должна использовать.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-131">The `behaviorConfiguration` attribute is used to specify which [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) of the [\<endpointBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) the endpoint should use.</span></span> <span data-ttu-id="e1e1c-132">Его значение соответствует `name` атрибут [ \<поведение >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-132">Its value is matched with the `name` attribute of the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element.</span></span> <span data-ttu-id="e1e1c-133">Пример использования конфигурации для задания поведений клиента см. в разделе [Настройка поведений клиента](../../../../docs/framework/wcf/configuring-client-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="e1e1c-133">For an example of using configuration to specify client behaviors, see [Configuring Client Behaviors](../../../../docs/framework/wcf/configuring-client-behaviors.md).</span></span>  
  
 <span data-ttu-id="e1e1c-134">Атрибут `contract` задает контракт, который предоставляет данная конечная точка.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-134">The `contract` attribute specifies which contract the endpoint is exposing.</span></span> <span data-ttu-id="e1e1c-135">Это значение соответствует свойству <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> атрибута <xref:System.ServiceModel.ServiceContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-135">This value maps to the <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> of the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span> <span data-ttu-id="e1e1c-136">Значение по умолчанию - это полное имя типа класса, реализующего службу.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-136">The default value is the full type name of the class that implements the service.</span></span>  
  
### <a name="configuring-metadata"></a><span data-ttu-id="e1e1c-137">Настройка метаданных</span><span class="sxs-lookup"><span data-stu-id="e1e1c-137">Configuring Metadata</span></span>  
 <span data-ttu-id="e1e1c-138">[ \<Метаданных >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) элемент используется для задания параметров, используемых для регистрации метаданных расширений импорта.</span><span class="sxs-lookup"><span data-stu-id="e1e1c-138">The [\<metadata>](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) element is used to specify settings used to register metadata import extensions.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="e1e1c-139"> расширение системы метаданных см. в разделе[расширение системы метаданных](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md).</span><span class="sxs-lookup"><span data-stu-id="e1e1c-139"> extending the metadata system, see[Extending the Metadata System](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1e1c-140">См. также</span><span class="sxs-lookup"><span data-stu-id="e1e1c-140">See Also</span></span>  
 [<span data-ttu-id="e1e1c-141">Конечные точки: адреса, привязки и контракты</span><span class="sxs-lookup"><span data-stu-id="e1e1c-141">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 [<span data-ttu-id="e1e1c-142">Настройка поведения клиентов</span><span class="sxs-lookup"><span data-stu-id="e1e1c-142">Configuring Client Behaviors</span></span>](../../../../docs/framework/wcf/configuring-client-behaviors.md)
