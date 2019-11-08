---
title: <security> из <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
ms.openlocfilehash: b66b5228cab9dbc35502a13a2d0fe56ce4c6a18d
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738582"
---
# <a name="security-of-wshttpbinding"></a><span data-ttu-id="08199-102">\<> безопасности \<wsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="08199-102">\<security> of \<wsHttpBinding></span></span>
<span data-ttu-id="08199-103">Представляет возможности безопасности [\<wsHttpBinding >](wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="08199-103">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>  
  
<span data-ttu-id="08199-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="08199-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="08199-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="08199-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="08199-106">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="08199-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="08199-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsHttpBinding >** ](wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="08199-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)</span></span>\
<span data-ttu-id="08199-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="08199-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="08199-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<security >**</span><span class="sxs-lookup"><span data-stu-id="08199-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08199-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08199-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08199-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="08199-111">Attributes and Elements</span></span>  
 <span data-ttu-id="08199-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="08199-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08199-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="08199-113">Attributes</span></span>  
  
|<span data-ttu-id="08199-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="08199-114">Attribute</span></span>|<span data-ttu-id="08199-115">Описание</span><span class="sxs-lookup"><span data-stu-id="08199-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="08199-116">режим</span><span class="sxs-lookup"><span data-stu-id="08199-116">mode</span></span>|<span data-ttu-id="08199-117">Используемых.</span><span class="sxs-lookup"><span data-stu-id="08199-117">-   Optional.</span></span> <span data-ttu-id="08199-118">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="08199-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="08199-119">Значение по умолчанию: `Message`.</span><span class="sxs-lookup"><span data-stu-id="08199-119">The default is `Message`.</span></span><br /><span data-ttu-id="08199-120">— Этот атрибут имеет тип <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="08199-120">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="08199-121">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="08199-121">Mode Attribute</span></span>  
  
|<span data-ttu-id="08199-122">значения</span><span class="sxs-lookup"><span data-stu-id="08199-122">Value</span></span>|<span data-ttu-id="08199-123">Описание</span><span class="sxs-lookup"><span data-stu-id="08199-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="08199-124">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="08199-124">None</span></span>|<span data-ttu-id="08199-125">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="08199-125">Security is disabled.</span></span>|  
|<span data-ttu-id="08199-126">Transport</span><span class="sxs-lookup"><span data-stu-id="08199-126">Transport</span></span>|<span data-ttu-id="08199-127">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="08199-127">Security is provided using HTTPS.</span></span> <span data-ttu-id="08199-128">Необходимо настроить службу с использованием SSL-сертификата.</span><span class="sxs-lookup"><span data-stu-id="08199-128">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="08199-129">Сообщение полностью защищено с помощью HTTPS, а проверка подлинности выполняется клиентом с помощью SSL-сертификата службы.</span><span class="sxs-lookup"><span data-stu-id="08199-129">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="08199-130">Проверка подлинности клиента контролируется посредством атрибута `ClientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="08199-130">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="08199-131">[\<транспорта](transport-of-wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="08199-131">of the [\<transport>](transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="08199-132">Сообщение</span><span class="sxs-lookup"><span data-stu-id="08199-132">Message</span></span>|<span data-ttu-id="08199-133">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="08199-133">Security is provided using SOAP message security.</span></span> <span data-ttu-id="08199-134">По умолчанию текст сообщений SOAP шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="08199-134">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="08199-135">Этот режим предоставляет множество возможностей, например сведения о доступности учетных данных службы для клиентов на внештатных каналах, об используемом наборе алгоритмов и об уровне защиты, применяемом к тексту сообщения через свойство Security.Message.</span><span class="sxs-lookup"><span data-stu-id="08199-135">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="08199-136">Проверка подлинности клиента выполняется один раз за сеанс, и результаты проверки сохраняются в кэше на протяжении всего сеанса.</span><span class="sxs-lookup"><span data-stu-id="08199-136">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="08199-137">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="08199-137">TransportWithMessageCredential</span></span>|<span data-ttu-id="08199-138">В данном режиме HTTPS обеспечивает целостность, конфиденциальность и проверку подлинности сервера, а механизм безопасности сообщений SOAP обеспечивает проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="08199-138">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="08199-139">По умолчанию проверка подлинности клиента выполняется один раз за сеанс, и результаты проверки сохраняются в кэше на протяжении всего сеанса.</span><span class="sxs-lookup"><span data-stu-id="08199-139">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08199-140">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="08199-140">Child Elements</span></span>  
  
|<span data-ttu-id="08199-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="08199-141">Element</span></span>|<span data-ttu-id="08199-142">Описание</span><span class="sxs-lookup"><span data-stu-id="08199-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08199-143">\<> транспорта</span><span class="sxs-lookup"><span data-stu-id="08199-143">\<transport></span></span>](transport-of-wshttpbinding.md)|<span data-ttu-id="08199-144">Определяет параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="08199-144">Defines the transport security settings.</span></span> <span data-ttu-id="08199-145">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="08199-145">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[<span data-ttu-id="08199-146">сообщение \<</span><span class="sxs-lookup"><span data-stu-id="08199-146">\<message></span></span>](message-of-wshttpbinding.md)|<span data-ttu-id="08199-147">Определяет параметры безопасности сообщения.</span><span class="sxs-lookup"><span data-stu-id="08199-147">Defines the security settings for the message.</span></span> <span data-ttu-id="08199-148">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="08199-148">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="08199-149">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="08199-149">Parent Elements</span></span>  
  
|<span data-ttu-id="08199-150">Элемент</span><span class="sxs-lookup"><span data-stu-id="08199-150">Element</span></span>|<span data-ttu-id="08199-151">Описание</span><span class="sxs-lookup"><span data-stu-id="08199-151">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08199-152">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="08199-152">\<wsHttpBinding></span></span>](wshttpbinding.md)|<span data-ttu-id="08199-153">Привязка безопасности для приложений транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="08199-153">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08199-154">Заметки</span><span class="sxs-lookup"><span data-stu-id="08199-154">Remarks</span></span>  
 <span data-ttu-id="08199-155">Класс WSHttpBinding предназначен для взаимодействия со службами, реализующими спецификации WS-\*.</span><span class="sxs-lookup"><span data-stu-id="08199-155">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="08199-156">Безопасность транспорта для этой привязки обеспечивается посредством протокола SSL по протоколам HTTP или HTTPS.</span><span class="sxs-lookup"><span data-stu-id="08199-156">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08199-157">См. также</span><span class="sxs-lookup"><span data-stu-id="08199-157">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- [<span data-ttu-id="08199-158">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="08199-158">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="08199-159">Привязки</span><span class="sxs-lookup"><span data-stu-id="08199-159">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="08199-160">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="08199-160">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="08199-161">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="08199-161">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="08199-162">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="08199-162">\<binding></span></span>](bindings.md)
