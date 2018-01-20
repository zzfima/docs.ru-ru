---
title: "&lt;security&gt; для &lt;ws2007HttpBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: fa650731b729b3b527ffe8087ae0316960cf30f3
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="ltsecuritygt-of-ltws2007httpbindinggt"></a><span data-ttu-id="b6913-102">&lt;security&gt; для &lt;ws2007HttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="b6913-102">&lt;security&gt; of &lt;ws2007HttpBinding&gt;</span></span>
<span data-ttu-id="b6913-103">Представляет параметры безопасности, используемые с [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="b6913-103">Represents the security settings used with the [\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span></span>  
  
 <span data-ttu-id="b6913-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b6913-104">\<system.serviceModel></span></span>  
<span data-ttu-id="b6913-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="b6913-105">\<bindings></span></span>  
<span data-ttu-id="b6913-106">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="b6913-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="b6913-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="b6913-107">\<binding></span></span>  
<span data-ttu-id="b6913-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="b6913-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6913-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6913-109">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
    <bindings>  
        <ws2007HttpBinding>  
            <binding name = "string">  
              <security mode="None/Message/Transport/TransportWithMessageCredential">  
                  <transport>  
                  </transport>  
                  <message>  
                  </message>  
              </security  
        </ws2007HttpBinding>  
    </bindings>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6913-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b6913-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b6913-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b6913-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6913-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b6913-112">Attributes</span></span>  
  
|<span data-ttu-id="b6913-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b6913-113">Attribute</span></span>|<span data-ttu-id="b6913-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="b6913-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="b6913-115">— Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="b6913-115">-   Optional.</span></span> <span data-ttu-id="b6913-116">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="b6913-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="b6913-117">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="b6913-117">The default is `Message`.</span></span><br /><br /> <span data-ttu-id="b6913-118">Это атрибут типа <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="b6913-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="b6913-119">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="b6913-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="b6913-120">Значение</span><span class="sxs-lookup"><span data-stu-id="b6913-120">Value</span></span>|<span data-ttu-id="b6913-121">Описание</span><span class="sxs-lookup"><span data-stu-id="b6913-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="b6913-122">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="b6913-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="b6913-123">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b6913-123">Security is provided using HTTPS.</span></span> <span data-ttu-id="b6913-124">Необходима настройка службы с помощью SSL-сертификатов.</span><span class="sxs-lookup"><span data-stu-id="b6913-124">The service must be configured with Secure Sockets Layer (SSL) certificates.</span></span> <span data-ttu-id="b6913-125">Сообщение полностью защищено с помощью HTTPS, а проверка подлинности службы выполняется клиентом с помощью SSL-сертификата службы.</span><span class="sxs-lookup"><span data-stu-id="b6913-125">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="b6913-126">Проверка подлинности клиента осуществляется с помощью `ClientCredentials` атрибут [ \<транспорта >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="b6913-126">The client authentication is controlled through the `ClientCredentials` attribute of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md) element.</span></span>|  
|`Message`|<span data-ttu-id="b6913-127">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="b6913-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="b6913-128">По умолчанию текст сообщений SOAP шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="b6913-128">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="b6913-129">Этот режим предоставляет множество функций, например доступ к учетным данным службы для клиентов за пределами диапазона, выбор используемого набора алгоритмов и уровня защиты, применяемого к тексту сообщения посредством <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span><span class="sxs-lookup"><span data-stu-id="b6913-129">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span></span> <span data-ttu-id="b6913-130">Проверка подлинности клиента выполняется один раз для каждого сеанса, и результаты проверки сохраняются в кэше на протяжении всего сеанса.</span><span class="sxs-lookup"><span data-stu-id="b6913-130">Client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="b6913-131">В данном режиме HTTPS обеспечивает целостность, конфиденциальность и проверку подлинности сервера, а механизм безопасности сообщений SOAP обеспечивает проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="b6913-131">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="b6913-132">По умолчанию проверка подлинности клиента выполняется один раз за сеанс, и результаты проверки сохраняются в кэше на протяжении всего сеанса.</span><span class="sxs-lookup"><span data-stu-id="b6913-132">By default, client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b6913-133">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b6913-133">Child Elements</span></span>  
  
|<span data-ttu-id="b6913-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="b6913-134">Element</span></span>|<span data-ttu-id="b6913-135">Описание:</span><span class="sxs-lookup"><span data-stu-id="b6913-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6913-136">\<transport></span><span class="sxs-lookup"><span data-stu-id="b6913-136">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md)|<span data-ttu-id="b6913-137">Определяет параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="b6913-137">Defines the transport security settings.</span></span> <span data-ttu-id="b6913-138">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="b6913-138">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span> <span data-ttu-id="b6913-139">Эти параметры применяются только в том случае, если режим имеет значение Transport.</span><span class="sxs-lookup"><span data-stu-id="b6913-139">These settings are applied only when the mode is set to Transport.</span></span>|  
|[<span data-ttu-id="b6913-140">\<message></span><span class="sxs-lookup"><span data-stu-id="b6913-140">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|<span data-ttu-id="b6913-141">Определяет параметры безопасности сообщения.</span><span class="sxs-lookup"><span data-stu-id="b6913-141">Defines the security settings for the message.</span></span> <span data-ttu-id="b6913-142">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="b6913-142">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span> <span data-ttu-id="b6913-143">Эти параметры неприменимы, если режим имеет значение Transport.</span><span class="sxs-lookup"><span data-stu-id="b6913-143">These settings are not applied when the mode is set to Transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b6913-144">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b6913-144">Parent Elements</span></span>  
  
|<span data-ttu-id="b6913-145">Элемент</span><span class="sxs-lookup"><span data-stu-id="b6913-145">Element</span></span>|<span data-ttu-id="b6913-146">Описание:</span><span class="sxs-lookup"><span data-stu-id="b6913-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6913-147">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="b6913-147">\<ws2007HttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md)|<span data-ttu-id="b6913-148">Привязка безопасности для приложений транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="b6913-148">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6913-149">Примечания</span><span class="sxs-lookup"><span data-stu-id="b6913-149">Remarks</span></span>  
 <span data-ttu-id="b6913-150">Этот элемент предназначен для взаимодействия со службами, реализующими спецификации WS-\*.</span><span class="sxs-lookup"><span data-stu-id="b6913-150">This element is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="b6913-151">Безопасность транспорта для этой привязки обеспечивается посредством протокола SSL по протоколам HTTP или HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b6913-151">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6913-152">См. также</span><span class="sxs-lookup"><span data-stu-id="b6913-152">See Also</span></span>  
 <xref:System.ServiceModel.WSHttpSecurity>  
 <xref:System.ServiceModel.WSHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="b6913-153">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="b6913-153">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="b6913-154">Привязки</span><span class="sxs-lookup"><span data-stu-id="b6913-154">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="b6913-155">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="b6913-155">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="b6913-156">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="b6913-156">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="b6913-157">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="b6913-157">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
