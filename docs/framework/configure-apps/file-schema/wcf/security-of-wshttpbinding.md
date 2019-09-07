---
title: <security> из <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
ms.openlocfilehash: f7a4ef98637a7c966665fdd02ad26929bd4ba6ac
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399716"
---
# <a name="security-of-wshttpbinding"></a><span data-ttu-id="8c31d-102">\<> \<безопасности WSHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="8c31d-102">\<security> of \<wsHttpBinding></span></span>
<span data-ttu-id="8c31d-103">Представляет возможности [ \<безопасности > WSHttpBinding](wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="8c31d-103">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>  
  
<span data-ttu-id="8c31d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8c31d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8c31d-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8c31d-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8c31d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="8c31d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="8c31d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> wsHttpBinding**](wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="8c31d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)</span></span>\
<span data-ttu-id="8c31d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="8c31d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="8c31d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> безопасности**</span><span class="sxs-lookup"><span data-stu-id="8c31d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c31d-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c31d-110">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithMessageCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="String"
             defaultClientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             defaultProxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             defaultRealm="String" />
  <message clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           establishSecurityContext="Boolean"
           negotiateServiceCredential="Boolean" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c31d-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8c31d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8c31d-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8c31d-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c31d-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8c31d-113">Attributes</span></span>  
  
|<span data-ttu-id="8c31d-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8c31d-114">Attribute</span></span>|<span data-ttu-id="8c31d-115">Описание</span><span class="sxs-lookup"><span data-stu-id="8c31d-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8c31d-116">режим</span><span class="sxs-lookup"><span data-stu-id="8c31d-116">mode</span></span>|<span data-ttu-id="8c31d-117">Используемых.</span><span class="sxs-lookup"><span data-stu-id="8c31d-117">-   Optional.</span></span> <span data-ttu-id="8c31d-118">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="8c31d-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="8c31d-119">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="8c31d-119">The default is `Message`.</span></span><br /><span data-ttu-id="8c31d-120">— Этот атрибут имеет тип <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="8c31d-120">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="8c31d-121">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="8c31d-121">Mode Attribute</span></span>  
  
|<span data-ttu-id="8c31d-122">Значение</span><span class="sxs-lookup"><span data-stu-id="8c31d-122">Value</span></span>|<span data-ttu-id="8c31d-123">Описание</span><span class="sxs-lookup"><span data-stu-id="8c31d-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8c31d-124">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="8c31d-124">None</span></span>|<span data-ttu-id="8c31d-125">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="8c31d-125">Security is disabled.</span></span>|  
|<span data-ttu-id="8c31d-126">Transport</span><span class="sxs-lookup"><span data-stu-id="8c31d-126">Transport</span></span>|<span data-ttu-id="8c31d-127">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8c31d-127">Security is provided using HTTPS.</span></span> <span data-ttu-id="8c31d-128">Необходимо настроить службу с использованием SSL-сертификата.</span><span class="sxs-lookup"><span data-stu-id="8c31d-128">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="8c31d-129">Сообщение полностью защищено с помощью HTTPS, а проверка подлинности выполняется клиентом с помощью SSL-сертификата службы.</span><span class="sxs-lookup"><span data-stu-id="8c31d-129">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="8c31d-130">Проверка подлинности клиента контролируется посредством атрибута `ClientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="8c31d-130">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="8c31d-131">> транспорта. [ \<](transport-of-wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="8c31d-131">of the [\<transport>](transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="8c31d-132">Сообщение</span><span class="sxs-lookup"><span data-stu-id="8c31d-132">Message</span></span>|<span data-ttu-id="8c31d-133">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="8c31d-133">Security is provided using SOAP message security.</span></span> <span data-ttu-id="8c31d-134">По умолчанию текст сообщений SOAP шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="8c31d-134">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="8c31d-135">Этот режим предоставляет множество возможностей, например сведения о доступности учетных данных службы для клиентов на внештатных каналах, об используемом наборе алгоритмов и об уровне защиты, применяемом к тексту сообщения через свойство Security.Message.</span><span class="sxs-lookup"><span data-stu-id="8c31d-135">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="8c31d-136">Проверка подлинности клиента выполняется один раз за сеанс, и результаты проверки сохраняются в кэше на протяжении всего сеанса.</span><span class="sxs-lookup"><span data-stu-id="8c31d-136">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="8c31d-137">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="8c31d-137">TransportWithMessageCredential</span></span>|<span data-ttu-id="8c31d-138">В данном режиме HTTPS обеспечивает целостность, конфиденциальность и проверку подлинности сервера, а механизм безопасности сообщений SOAP обеспечивает проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="8c31d-138">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="8c31d-139">По умолчанию проверка подлинности клиента выполняется один раз за сеанс, и результаты проверки сохраняются в кэше на протяжении всего сеанса.</span><span class="sxs-lookup"><span data-stu-id="8c31d-139">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c31d-140">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8c31d-140">Child Elements</span></span>  
  
|<span data-ttu-id="8c31d-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="8c31d-141">Element</span></span>|<span data-ttu-id="8c31d-142">Описание</span><span class="sxs-lookup"><span data-stu-id="8c31d-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c31d-143">\<> транспорта</span><span class="sxs-lookup"><span data-stu-id="8c31d-143">\<transport></span></span>](transport-of-wshttpbinding.md)|<span data-ttu-id="8c31d-144">Определяет параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="8c31d-144">Defines the transport security settings.</span></span> <span data-ttu-id="8c31d-145">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="8c31d-145">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[<span data-ttu-id="8c31d-146">\<> сообщения</span><span class="sxs-lookup"><span data-stu-id="8c31d-146">\<message></span></span>](message-of-wshttpbinding.md)|<span data-ttu-id="8c31d-147">Определяет параметры безопасности сообщения.</span><span class="sxs-lookup"><span data-stu-id="8c31d-147">Defines the security settings for the message.</span></span> <span data-ttu-id="8c31d-148">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="8c31d-148">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8c31d-149">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8c31d-149">Parent Elements</span></span>  
  
|<span data-ttu-id="8c31d-150">Элемент</span><span class="sxs-lookup"><span data-stu-id="8c31d-150">Element</span></span>|<span data-ttu-id="8c31d-151">Описание</span><span class="sxs-lookup"><span data-stu-id="8c31d-151">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c31d-152">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="8c31d-152">\<wsHttpBinding></span></span>](wshttpbinding.md)|<span data-ttu-id="8c31d-153">Привязка безопасности для приложений транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="8c31d-153">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c31d-154">Примечания</span><span class="sxs-lookup"><span data-stu-id="8c31d-154">Remarks</span></span>  
 <span data-ttu-id="8c31d-155">Класс WSHttpBinding предназначен для взаимодействия со службами, реализующими спецификации WS-\*.</span><span class="sxs-lookup"><span data-stu-id="8c31d-155">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="8c31d-156">Безопасность транспорта для этой привязки обеспечивается посредством протокола SSL по протоколам HTTP или HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8c31d-156">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c31d-157">См. также</span><span class="sxs-lookup"><span data-stu-id="8c31d-157">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- [<span data-ttu-id="8c31d-158">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="8c31d-158">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="8c31d-159">Привязки</span><span class="sxs-lookup"><span data-stu-id="8c31d-159">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8c31d-160">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="8c31d-160">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="8c31d-161">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="8c31d-161">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="8c31d-162">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="8c31d-162">\<binding></span></span>](../../../misc/binding.md)
