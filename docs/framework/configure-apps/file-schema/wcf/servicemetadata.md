---
title: '&lt;serviceMetadata&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2b4c3b4c-31d4-4908-a9b7-5bb411c221f2
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f4e88c6e5f03cef83e640fbca7434d10f82653f1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltservicemetadatagt"></a><span data-ttu-id="1d6b3-102">&lt;serviceMetadata&gt;</span><span class="sxs-lookup"><span data-stu-id="1d6b3-102">&lt;serviceMetadata&gt;</span></span>
<span data-ttu-id="1d6b3-103">Задает публикацию метаданных службы и связанных сведений.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-103">Specifies the publication of service metadata and associated information.</span></span>  
  
<span data-ttu-id="1d6b3-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="1d6b3-104">\<system.serviceModel></span></span>  
<span data-ttu-id="1d6b3-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="1d6b3-105">\<behaviors></span></span>  
<span data-ttu-id="1d6b3-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1d6b3-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="1d6b3-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="1d6b3-107">\<behavior></span></span>  
<span data-ttu-id="1d6b3-108">\<serviceMetadata ></span><span class="sxs-lookup"><span data-stu-id="1d6b3-108">\<serviceMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d6b3-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d6b3-109">Syntax</span></span>  
  
```xml
<serviceMetadata externalMetadataLocation="String"  
                 httpGetBinding="String" 
                 httpGetBindingConfiguration="String"  
                 httpGetEnabled="Boolean" 
                 httpGetUrl="String" 
                 httpsGetBinding="String" 
                 httpsGetBindingConfiguration="String"  
                 httpsGetEnabled="Boolean"   
                 httpsGetUrl="String"  
                 policyVersion="Policy12/Policy15" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d6b3-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1d6b3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1d6b3-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1d6b3-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1d6b3-112">Attributes</span></span>  
  
|<span data-ttu-id="1d6b3-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1d6b3-113">Attribute</span></span>|<span data-ttu-id="1d6b3-114">Описание</span><span class="sxs-lookup"><span data-stu-id="1d6b3-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1d6b3-115">externalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="1d6b3-115">externalMetadataLocation</span></span>|<span data-ttu-id="1d6b3-116">Универсальный код ресурса (URI), содержащий местоположение WSDL-файла, возвращаемый пользователю в ответ на запросы WSDL и MEX, вместо автоматически создаваемых WSDL.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-116">A Uri that contains the location of a WSDL file, which is returned to the user in response to WSDL and MEX requests instead of the auto-generated WSDL.</span></span> <span data-ttu-id="1d6b3-117">Если атрибут не задан, по умолчанию возвращается WSDL.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-117">When this attribute is not set, the default WSDL is returned.</span></span> <span data-ttu-id="1d6b3-118">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-118">The default is an empty string.</span></span>|  
|<span data-ttu-id="1d6b3-119">httpGetBinding</span><span class="sxs-lookup"><span data-stu-id="1d6b3-119">httpGetBinding</span></span>|<span data-ttu-id="1d6b3-120">Строковое значение, в котором указывается тип привязки, используемой для загрузки метаданных посредством HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-120">A string that specifies the type of the binding that will be used for metadata retrieval via HTTP GET.</span></span> <span data-ttu-id="1d6b3-121">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-121">This setting is optional.</span></span> <span data-ttu-id="1d6b3-122">Если он не указан, то будут использоваться привязки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-122">If it is not specified, the default bindings will be used.</span></span><br /><br /> <span data-ttu-id="1d6b3-123">Поддерживаются только привязки с внутренними элементами привязки, поддерживающими <xref:System.ServiceModel.Channels.IReplyChannel>.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-123">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="1d6b3-124">Кроме этого, свойство <xref:System.ServiceModel.Channels.MessageVersion> привязки должно иметь значение <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-124">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>|  
|<span data-ttu-id="1d6b3-125">httpGetBindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="1d6b3-125">httpGetBindingConfiguration</span></span>|<span data-ttu-id="1d6b3-126">Строка, задающая имя привязки, указанной атрибутом `httpGetBinding`, который ссылается на дополнительные сведения конфигурации этой привязки.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-126">A string that sets the name of the binding that is specified in the `httpGetBinding` attribute, which references to the additional configuration information of this binding.</span></span> <span data-ttu-id="1d6b3-127">Такое же имя должно быть задано в разделе `<bindings>`.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-127">The same name must be defined in the `<bindings>` section.</span></span>|  
|<span data-ttu-id="1d6b3-128">httpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="1d6b3-128">httpGetEnabled</span></span>|<span data-ttu-id="1d6b3-129">Логическое значение, указывающее, следует ли опубликовывать метаданные службы для извлечения с помощью запроса HTTP-GET.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-129">A Boolean value that specifies whether to publish service metadata for retrieval using an HTTP/Get request.</span></span> <span data-ttu-id="1d6b3-130">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-130">The default is `false`.</span></span><br /><br /> <span data-ttu-id="1d6b3-131">Если атрибут httpGetUrl не указан, адрес, по которому публикуются метаданные, - это адрес службы плюс «?wsdl».</span><span class="sxs-lookup"><span data-stu-id="1d6b3-131">If the httpGetUrl attribute is not specified, the address at which the metadata is published is the service address plus a "?wsdl".</span></span> <span data-ttu-id="1d6b3-132">Например, если адрес службы - "http://localhost:8080/CalculatorService", то адрес метаданных HTTP/Get будет иметь вид "http://localhost:8080/CalculatorService?wsdl".</span><span class="sxs-lookup"><span data-stu-id="1d6b3-132">For example, if the service address is "http://localhost:8080/CalculatorService", the HTTP/Get metadata address is "http://localhost:8080/CalculatorService?wsdl".</span></span><br /><br /> <span data-ttu-id="1d6b3-133">Если это свойство имеет `false`, или адрес службы не основан на HTTP или HTTPS, «? wsdl» игнорируется.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-133">If this property is `false`, or the address of the service is not based on HTTP or HTTPS, "?wsdl" is ignored.</span></span>|  
|<span data-ttu-id="1d6b3-134">httpGetUrl</span><span class="sxs-lookup"><span data-stu-id="1d6b3-134">httpGetUrl</span></span>|<span data-ttu-id="1d6b3-135">URI, указывающий адрес, по которому метаданные публикуются для извлечения с использованием запроса HTTP-GET.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-135">A Uri that specifies the address at which the metadata is published for retrieval using an HTTP/Get request.</span></span> <span data-ttu-id="1d6b3-136">Если указан относительный URI, то он будет обрабатываться относительно базового адреса службы.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-136">If a relative Uri is specified it will be treated as relative to the service’s base address.</span></span>|  
|<span data-ttu-id="1d6b3-137">httpsGetBinding</span><span class="sxs-lookup"><span data-stu-id="1d6b3-137">httpsGetBinding</span></span>|<span data-ttu-id="1d6b3-138">Строковое значение, в котором указывается тип привязки, используемой для загрузки метаданных посредством HTTPS GET.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-138">A string that specifies the type of the binding that will be used for metadata retrieval via HTTPS GET.</span></span> <span data-ttu-id="1d6b3-139">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-139">This setting is optional.</span></span> <span data-ttu-id="1d6b3-140">Если он не указан, то будут использоваться привязки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-140">If it is not specified, the default bindings will be used.</span></span><br /><br /> <span data-ttu-id="1d6b3-141">Поддерживаются только привязки с внутренними элементами привязки, поддерживающими <xref:System.ServiceModel.Channels.IReplyChannel>.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-141">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="1d6b3-142">Кроме этого, свойство <xref:System.ServiceModel.Channels.MessageVersion> привязки должно иметь значение <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-142">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>|  
|<span data-ttu-id="1d6b3-143">httpsGetBindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="1d6b3-143">httpsGetBindingConfiguration</span></span>|<span data-ttu-id="1d6b3-144">Строка, задающая имя привязки, указанной атрибутом `httpsGetBinding`, который ссылается на дополнительные сведения конфигурации этой привязки.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-144">A string that sets the name of the binding that is specified in the `httpsGetBinding` attribute, which references to the additional configuration information of this binding.</span></span> <span data-ttu-id="1d6b3-145">Такое же имя должно быть задано в разделе `<bindings>`.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-145">The same name must be defined in the `<bindings>` section.</span></span>|  
|<span data-ttu-id="1d6b3-146">httpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="1d6b3-146">httpsGetEnabled</span></span>|<span data-ttu-id="1d6b3-147">Логическое значение, указывающее, следует ли опубликовывать метаданные службы для извлечения с помощью запроса HTTPS-GET.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-147">A Boolean value that specifies whether to publish service metadata for retrieval using an HTTPS/Get request.</span></span> <span data-ttu-id="1d6b3-148">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-148">The default is `false`.</span></span><br /><br /> <span data-ttu-id="1d6b3-149">Если атрибут httpsGetUrl не указан, адрес, по которому публикуются метаданные, - это адрес службы плюс «?wsdl».</span><span class="sxs-lookup"><span data-stu-id="1d6b3-149">If the httpsGetUrl attribute is not specified, the address at which the metadata is published is the service address plus a "?wsdl".</span></span> <span data-ttu-id="1d6b3-150">Например, если адрес службы - "https://localhost:8080/CalculatorService", то адрес метаданных HTTPS/Get будет иметь вид "https://localhost:8080/CalculatorService?wsdl".</span><span class="sxs-lookup"><span data-stu-id="1d6b3-150">For example, if the service address is "https://localhost:8080/CalculatorService", the HTTP/Get metadata address is "https://localhost:8080/CalculatorService?wsdl".</span></span><br /><br /> <span data-ttu-id="1d6b3-151">Если это свойство имеет `false`, или адрес службы не основан на HTTP или HTTPS, «? wsdl» игнорируется.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-151">If this property is `false`, or the address of the service is not based on HTTP or HTTPS, "?wsdl" is ignored.</span></span>|  
|<span data-ttu-id="1d6b3-152">httpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="1d6b3-152">httpsGetUrl</span></span>|<span data-ttu-id="1d6b3-153">URI, указывающий адрес, по которому метаданные публикуются для извлечения с использованием запроса HTTPS-GET.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-153">A Uri that specifies the address at which the metadata is published for retrieval using an HTTPS/Get request.</span></span>|  
|<span data-ttu-id="1d6b3-154">policyVersion</span><span class="sxs-lookup"><span data-stu-id="1d6b3-154">policyVersion</span></span>|<span data-ttu-id="1d6b3-155">Строка, указывающая версию используемой спецификации Web Services Policy.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-155">A string that specifies the version of the WS-Policy specification being used.</span></span> <span data-ttu-id="1d6b3-156">Это атрибут типа <xref:System.ServiceModel.Description.PolicyVersion>.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-156">This attribute is of type <xref:System.ServiceModel.Description.PolicyVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1d6b3-157">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1d6b3-157">Child Elements</span></span>  
 <span data-ttu-id="1d6b3-158">Нет</span><span class="sxs-lookup"><span data-stu-id="1d6b3-158">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1d6b3-159">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1d6b3-159">Parent Elements</span></span>  
  
|<span data-ttu-id="1d6b3-160">Элемент</span><span class="sxs-lookup"><span data-stu-id="1d6b3-160">Element</span></span>|<span data-ttu-id="1d6b3-161">Описание</span><span class="sxs-lookup"><span data-stu-id="1d6b3-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1d6b3-162">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="1d6b3-162">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="1d6b3-163">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-163">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d6b3-164">Примечания</span><span class="sxs-lookup"><span data-stu-id="1d6b3-164">Remarks</span></span>  
 <span data-ttu-id="1d6b3-165">Элемент конфигурации позволяет управлять возможностями публикации метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-165">This configuration element allows you to control the metadata publishing features of a service.</span></span> <span data-ttu-id="1d6b3-166">Чтобы предотвратить непреднамеренное разглашение потенциально важных метаданных службы, в конфигурации служб [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] публикация метаданных по умолчанию отключена.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-166">To prevent unintentional disclosure of potentially sensitive service metadata, the default configuration for [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services disables metadata publishing.</span></span> <span data-ttu-id="1d6b3-167">Такое расширение функциональности по умолчанию защищено, но это также означает, что при этом невозможно использовать средство импорта метаданных (например, Svcutil.exe) для создания клиентского кода, необходимого для вызова службы, если поведение публикации не включено явно в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-167">This behavior is secure by default, but also means that you cannot use a metadata import tool (such as Svcutil.exe) to generate the client code required to call the service unless the service’s metadata publishing behavior is explicitly enabled in configuration.</span></span> <span data-ttu-id="1d6b3-168">Включить такое поведение публикации для службы можно с помощью элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-168">Using this configuration element, you can enable this publishing behavior for your service.</span></span>  
  
 <span data-ttu-id="1d6b3-169">Подробный пример настройки этого поведения см. в разделе [поведения публикации метаданных](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md).</span><span class="sxs-lookup"><span data-stu-id="1d6b3-169">For a detailed example of configuring this behavior, see [Metadata Publishing Behavior](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md).</span></span>  
  
 <span data-ttu-id="1d6b3-170">Дополнительные атрибуты `httpGetBinding` и `httpsGetBinding` позволяют настроить привязки, используемые для извлечения метаданных посредством HTTP-GET (или HTTPS-GET).</span><span class="sxs-lookup"><span data-stu-id="1d6b3-170">The optional `httpGetBinding` and `httpsGetBinding` attributes allow you to configure the bindings used for metadata retrieval via HTTP GET (or HTTPS GET).</span></span> <span data-ttu-id="1d6b3-171">Если они не заданы, для извлечения метаданных применяются привязки по умолчанию (`HttpTransportBindingElement` для HTTP и `HttpsTransportBindingElement` для HTTPS).</span><span class="sxs-lookup"><span data-stu-id="1d6b3-171">If they are not specified, the default bindings (`HttpTransportBindingElement`, in the case of HTTP and `HttpsTransportBindingElement`, in the case of HTTPS) are used for metadata retrieval as appropriate.</span></span> <span data-ttu-id="1d6b3-172">Обратите внимание, что эти атрибуты нельзя использовать вместе со встроенными привязками WCF.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-172">Notice that you cannot use these attributes with the built-in WCF bindings.</span></span> <span data-ttu-id="1d6b3-173">Поддерживаются только привязки с внутренними элементами привязки, поддерживающими <xref:System.ServiceModel.Channels.IReplyChannel>.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-173">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="1d6b3-174">Кроме этого, свойство <xref:System.ServiceModel.Channels.MessageVersion> привязки должно иметь значение <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-174">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>  
  
 <span data-ttu-id="1d6b3-175">Для снижения подверженности службы действиям недобросовестных пользователей перенос можно защитить с помощью механизма SSL по протоколу HTTP (HTTPS).</span><span class="sxs-lookup"><span data-stu-id="1d6b3-175">To reduce the exposure of a service to malicious users, it is possible to secure the transfer using the SSL over HTTP (HTTPS) mechanism.</span></span> <span data-ttu-id="1d6b3-176">Для этого необходимо вначале выполнить привязку подходящего сертификата X.509 к конкретному порту компьютера, на котором размещена служба.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-176">To do so, you must first bind a suitable X.509 certificate to a specific port on the computer that is hosting the service.</span></span> <span data-ttu-id="1d6b3-177">([!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)] [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).) Затем необходимо добавить этот элемент в конфигурацию службы и задать атрибуту `httpsGetEnabled` значение `true`.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-177">([!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)] [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).) Second, add this element to the service configuration and set the `httpsGetEnabled` attribute to `true`.</span></span> <span data-ttu-id="1d6b3-178">После этого следует присвоить атрибуту `httpsGetUrl` URL-адрес конечной точки метаданных службы, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-178">Finally, set the `httpsGetUrl` attribute to the URL of the service metadata endpoint, as shown in the following example.</span></span>  
  
```xml
<behaviors>  
  <serviceBehaviors>  
    <behavior name="NewBehavior">  
      <serviceMetadata httpsGetEnabled="true"   
                       httpsGetUrl="https://myComputerName/myEndpoint" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="example"></a><span data-ttu-id="1d6b3-179">Пример</span><span class="sxs-lookup"><span data-stu-id="1d6b3-179">Example</span></span>  
 <span data-ttu-id="1d6b3-180">Следующий пример настроить службу для предоставления метаданных с помощью \<serviceMetadata > элемент.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-180">The following example configure a service to expose metadata by using the \<serviceMetadata> element.</span></span> <span data-ttu-id="1d6b3-181">Здесь также настраивается конечная точка предоставления доступа к контракту `IMetadataExchange` как реализации протокола WS-MetadataExchange (MEX).</span><span class="sxs-lookup"><span data-stu-id="1d6b3-181">It also configures an endpoint to expose the `IMetadataExchange` contract as an implementation of a WS-MetadataExchange (MEX) protocol.</span></span> <span data-ttu-id="1d6b3-182">В примере используется привязка `mexHttpBinding`, являющаяся удобной стандартной привязкой, эквивалентной привязке `wsHttpBinding` с режимом безопасности `None`.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-182">The example uses the `mexHttpBinding`, which is a convenience standard binding that is equivalent to the `wsHttpBinding` with the security mode set to `None`.</span></span> <span data-ttu-id="1d6b3-183">Относительный адрес «mex» используется в конечной точке, которая при разрешении относительно базового адреса службы приводит к созданию адреса конечной точки http://localhost/servicemodelsamples/service.svc/mex.</span><span class="sxs-lookup"><span data-stu-id="1d6b3-183">A relative address of "mex" is used in the endpoint, which when resolved against the services base address results in an endpoint address of http://localhost/servicemodelsamples/service.svc/mex.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.CalculatorService" 
               behaviorConfiguration="CalculatorServiceBehavior">  
        <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc -->  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex   
             To expose the IMetadataExchange contract, you must enable the serviceMetadata behavior as demonstrated below. -->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  

    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <!-- The serviceMetadata behavior publishes metadata through   
               the IMetadataExchange contract. When this behavior is   
               present, you can expose this contract through an endpoint   
               as shown above. Setting httpGetEnabled to true publishes   
               the service's WSDL at the <baseaddress>?wsdl  
               eg. http://localhost/servicemodelsamples/service.svc?wsdl -->  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1d6b3-184">См. также</span><span class="sxs-lookup"><span data-stu-id="1d6b3-184">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceMetadataPublishingElement>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
 [<span data-ttu-id="1d6b3-185">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="1d6b3-185">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="1d6b3-186">Поведение публикации метаданных</span><span class="sxs-lookup"><span data-stu-id="1d6b3-186">Metadata Publishing Behavior</span></span>](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)
