---
title: '&lt;security&gt; для &lt;ws2007HttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 00d1f43cb2d3f3aa67e72ee7ae405041bd2842ac
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509128"
---
# <a name="ltsecuritygt-of-ltws2007httpbindinggt"></a><span data-ttu-id="b909f-102">&lt;security&gt; для &lt;ws2007HttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="b909f-102">&lt;security&gt; of &lt;ws2007HttpBinding&gt;</span></span>
<span data-ttu-id="b909f-103">Представляет параметры безопасности, используемые с [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="b909f-103">Represents the security settings used with the [\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span></span>  
  
 <span data-ttu-id="b909f-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="b909f-104">\<system.serviceModel></span></span>  
<span data-ttu-id="b909f-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="b909f-105">\<bindings></span></span>  
<span data-ttu-id="b909f-106">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="b909f-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="b909f-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="b909f-107">\<binding></span></span>  
<span data-ttu-id="b909f-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="b909f-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b909f-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b909f-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b909f-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b909f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b909f-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b909f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b909f-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b909f-112">Attributes</span></span>  
  
|<span data-ttu-id="b909f-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b909f-113">Attribute</span></span>|<span data-ttu-id="b909f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="b909f-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="b909f-115">-Необязательно.</span><span class="sxs-lookup"><span data-stu-id="b909f-115">-   Optional.</span></span> <span data-ttu-id="b909f-116">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="b909f-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="b909f-117">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="b909f-117">The default is `Message`.</span></span><br /><br /> <span data-ttu-id="b909f-118">Это атрибут типа <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="b909f-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="b909f-119">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="b909f-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="b909f-120">Значение</span><span class="sxs-lookup"><span data-stu-id="b909f-120">Value</span></span>|<span data-ttu-id="b909f-121">Описание</span><span class="sxs-lookup"><span data-stu-id="b909f-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="b909f-122">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="b909f-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="b909f-123">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b909f-123">Security is provided using HTTPS.</span></span> <span data-ttu-id="b909f-124">Необходима настройка службы с помощью SSL-сертификатов.</span><span class="sxs-lookup"><span data-stu-id="b909f-124">The service must be configured with Secure Sockets Layer (SSL) certificates.</span></span> <span data-ttu-id="b909f-125">Сообщение полностью защищено с помощью HTTPS, а проверка подлинности службы выполняется клиентом с помощью SSL-сертификата службы.</span><span class="sxs-lookup"><span data-stu-id="b909f-125">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="b909f-126">Проверка подлинности клиента контролируется посредством `ClientCredentials` атрибут [ \<транспорта >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="b909f-126">The client authentication is controlled through the `ClientCredentials` attribute of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md) element.</span></span>|  
|`Message`|<span data-ttu-id="b909f-127">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="b909f-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="b909f-128">По умолчанию текст сообщений SOAP шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="b909f-128">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="b909f-129">Этот режим предоставляет множество функций, например доступ к учетным данным службы для клиентов за пределами диапазона, выбор используемого набора алгоритмов и уровня защиты, применяемого к тексту сообщения посредством <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span><span class="sxs-lookup"><span data-stu-id="b909f-129">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span></span> <span data-ttu-id="b909f-130">Проверка подлинности клиента выполняется один раз для каждого сеанса, и результаты проверки сохраняются в кэше на протяжении всего сеанса.</span><span class="sxs-lookup"><span data-stu-id="b909f-130">Client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="b909f-131">В данном режиме HTTPS обеспечивает целостность, конфиденциальность и проверку подлинности сервера, а механизм безопасности сообщений SOAP обеспечивает проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="b909f-131">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="b909f-132">По умолчанию проверка подлинности клиента выполняется один раз за сеанс, и результаты проверки сохраняются в кэше на протяжении всего сеанса.</span><span class="sxs-lookup"><span data-stu-id="b909f-132">By default, client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b909f-133">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b909f-133">Child Elements</span></span>  
  
|<span data-ttu-id="b909f-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="b909f-134">Element</span></span>|<span data-ttu-id="b909f-135">Описание</span><span class="sxs-lookup"><span data-stu-id="b909f-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b909f-136">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="b909f-136">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md)|<span data-ttu-id="b909f-137">Определяет параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="b909f-137">Defines the transport security settings.</span></span> <span data-ttu-id="b909f-138">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="b909f-138">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span> <span data-ttu-id="b909f-139">Эти параметры применяются только в том случае, если режим имеет значение Transport.</span><span class="sxs-lookup"><span data-stu-id="b909f-139">These settings are applied only when the mode is set to Transport.</span></span>|  
|[<span data-ttu-id="b909f-140">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="b909f-140">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|<span data-ttu-id="b909f-141">Определяет параметры безопасности сообщения.</span><span class="sxs-lookup"><span data-stu-id="b909f-141">Defines the security settings for the message.</span></span> <span data-ttu-id="b909f-142">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="b909f-142">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span> <span data-ttu-id="b909f-143">Эти параметры неприменимы, если режим имеет значение Transport.</span><span class="sxs-lookup"><span data-stu-id="b909f-143">These settings are not applied when the mode is set to Transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b909f-144">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b909f-144">Parent Elements</span></span>  
  
|<span data-ttu-id="b909f-145">Элемент</span><span class="sxs-lookup"><span data-stu-id="b909f-145">Element</span></span>|<span data-ttu-id="b909f-146">Описание</span><span class="sxs-lookup"><span data-stu-id="b909f-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b909f-147">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="b909f-147">\<ws2007HttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md)|<span data-ttu-id="b909f-148">Привязка безопасности для приложений транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="b909f-148">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b909f-149">Примечания</span><span class="sxs-lookup"><span data-stu-id="b909f-149">Remarks</span></span>  
 <span data-ttu-id="b909f-150">Этот элемент предназначен для взаимодействия со службами, реализующими спецификации WS-\*.</span><span class="sxs-lookup"><span data-stu-id="b909f-150">This element is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="b909f-151">Безопасность транспорта для этой привязки обеспечивается посредством протокола SSL по протоколам HTTP или HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b909f-151">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b909f-152">См. также</span><span class="sxs-lookup"><span data-stu-id="b909f-152">See Also</span></span>  
 <xref:System.ServiceModel.WSHttpSecurity>  
 <xref:System.ServiceModel.WSHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="b909f-153">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="b909f-153">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="b909f-154">Привязки</span><span class="sxs-lookup"><span data-stu-id="b909f-154">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="b909f-155">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="b909f-155">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="b909f-156">Использование привязок для настройки службы Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="b909f-156">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="b909f-157">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="b909f-157">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
