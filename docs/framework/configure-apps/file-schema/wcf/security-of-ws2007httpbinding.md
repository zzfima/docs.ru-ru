---
title: <security> из <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
ms.openlocfilehash: e88f55f3651d1ccd55631dce13a0349ac2772624
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736387"
---
# <a name="security-of-ws2007httpbinding"></a><span data-ttu-id="e2f41-102">\<> безопасности \<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="e2f41-102">\<security> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="e2f41-103">Представляет параметры безопасности, используемые с элементом [\<ws2007HttpBinding >](ws2007httpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="e2f41-103">Represents the security settings used with the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>  
  
<span data-ttu-id="e2f41-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e2f41-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e2f41-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e2f41-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e2f41-106">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="e2f41-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="e2f41-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ws2007HttpBinding >** ](ws2007httpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="e2f41-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)</span></span>\
<span data-ttu-id="e2f41-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="e2f41-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="e2f41-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<security >**</span><span class="sxs-lookup"><span data-stu-id="e2f41-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2f41-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2f41-110">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <bindings>
    <ws2007HttpBinding>
      <binding name = "String">
        <security mode="None/Message/Transport/TransportWithMessageCredential">
          <transport>
          </transport>
          <message>
          </message>
        </security>
      </binding>
    </ws2007HttpBinding>
  </bindings>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2f41-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e2f41-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e2f41-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e2f41-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2f41-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e2f41-113">Attributes</span></span>  
  
|<span data-ttu-id="e2f41-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e2f41-114">Attribute</span></span>|<span data-ttu-id="e2f41-115">Описание</span><span class="sxs-lookup"><span data-stu-id="e2f41-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="e2f41-116">Используемых.</span><span class="sxs-lookup"><span data-stu-id="e2f41-116">-   Optional.</span></span> <span data-ttu-id="e2f41-117">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="e2f41-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="e2f41-118">Значение по умолчанию: `Message`.</span><span class="sxs-lookup"><span data-stu-id="e2f41-118">The default is `Message`.</span></span><br /><br /> <span data-ttu-id="e2f41-119">Это атрибут типа <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="e2f41-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="e2f41-120">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="e2f41-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="e2f41-121">значения</span><span class="sxs-lookup"><span data-stu-id="e2f41-121">Value</span></span>|<span data-ttu-id="e2f41-122">Описание</span><span class="sxs-lookup"><span data-stu-id="e2f41-122">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="e2f41-123">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="e2f41-123">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="e2f41-124">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e2f41-124">Security is provided using HTTPS.</span></span> <span data-ttu-id="e2f41-125">Необходима настройка службы с помощью SSL-сертификатов.</span><span class="sxs-lookup"><span data-stu-id="e2f41-125">The service must be configured with Secure Sockets Layer (SSL) certificates.</span></span> <span data-ttu-id="e2f41-126">Сообщение полностью защищено с помощью HTTPS, а проверка подлинности службы выполняется клиентом с помощью SSL-сертификата службы.</span><span class="sxs-lookup"><span data-stu-id="e2f41-126">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="e2f41-127">Проверка подлинности клиента контролируется с помощью атрибута `ClientCredentials` элемента [> транспорта\<](transport-of-ws2007httpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="e2f41-127">The client authentication is controlled through the `ClientCredentials` attribute of the [\<transport>](transport-of-ws2007httpbinding.md) element.</span></span>|  
|`Message`|<span data-ttu-id="e2f41-128">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="e2f41-128">Security is provided using SOAP message security.</span></span> <span data-ttu-id="e2f41-129">По умолчанию текст сообщений SOAP шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="e2f41-129">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="e2f41-130">Этот режим предоставляет множество возможностей, например доступ к учетным данным службы для клиентов за пределами диапазона, выбор используемого набора алгоритмов и уровня защиты, применяемого к тексту сообщения посредством <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span><span class="sxs-lookup"><span data-stu-id="e2f41-130">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span></span> <span data-ttu-id="e2f41-131">Проверка подлинности клиента выполняется один раз для каждого сеанса, и результаты проверки сохраняются в кэше на протяжении всего сеанса.</span><span class="sxs-lookup"><span data-stu-id="e2f41-131">Client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="e2f41-132">В данном режиме HTTPS обеспечивает целостность, конфиденциальность и проверку подлинности сервера, а механизм безопасности сообщений SOAP обеспечивает проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="e2f41-132">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="e2f41-133">По умолчанию проверка подлинности клиента выполняется один раз за сеанс, и результаты проверки сохраняются в кэше на протяжении всего сеанса.</span><span class="sxs-lookup"><span data-stu-id="e2f41-133">By default, client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e2f41-134">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e2f41-134">Child Elements</span></span>  
  
|<span data-ttu-id="e2f41-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="e2f41-135">Element</span></span>|<span data-ttu-id="e2f41-136">Описание</span><span class="sxs-lookup"><span data-stu-id="e2f41-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e2f41-137">\<> транспорта</span><span class="sxs-lookup"><span data-stu-id="e2f41-137">\<transport></span></span>](transport-of-ws2007httpbinding.md)|<span data-ttu-id="e2f41-138">Определяет параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="e2f41-138">Defines the transport security settings.</span></span> <span data-ttu-id="e2f41-139">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="e2f41-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span> <span data-ttu-id="e2f41-140">Эти параметры применяются только в том случае, если режим имеет значение Transport.</span><span class="sxs-lookup"><span data-stu-id="e2f41-140">These settings are applied only when the mode is set to Transport.</span></span>|  
|[<span data-ttu-id="e2f41-141">сообщение \<</span><span class="sxs-lookup"><span data-stu-id="e2f41-141">\<message></span></span>](message-of-ws2007httpbinding.md)|<span data-ttu-id="e2f41-142">Определяет параметры безопасности сообщения.</span><span class="sxs-lookup"><span data-stu-id="e2f41-142">Defines the security settings for the message.</span></span> <span data-ttu-id="e2f41-143">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="e2f41-143">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span> <span data-ttu-id="e2f41-144">Эти параметры неприменимы, если режим имеет значение Transport.</span><span class="sxs-lookup"><span data-stu-id="e2f41-144">These settings are not applied when the mode is set to Transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e2f41-145">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e2f41-145">Parent Elements</span></span>  
  
|<span data-ttu-id="e2f41-146">Элемент</span><span class="sxs-lookup"><span data-stu-id="e2f41-146">Element</span></span>|<span data-ttu-id="e2f41-147">Описание</span><span class="sxs-lookup"><span data-stu-id="e2f41-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e2f41-148">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="e2f41-148">\<ws2007HttpBinding></span></span>](ws2007httpbinding.md)|<span data-ttu-id="e2f41-149">Привязка безопасности для приложений транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="e2f41-149">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2f41-150">Заметки</span><span class="sxs-lookup"><span data-stu-id="e2f41-150">Remarks</span></span>  
 <span data-ttu-id="e2f41-151">Этот элемент предназначен для взаимодействия со службами, реализующими спецификации WS-\*.</span><span class="sxs-lookup"><span data-stu-id="e2f41-151">This element is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="e2f41-152">Безопасность транспорта для этой привязки обеспечивается посредством протокола SSL по протоколам HTTP или HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e2f41-152">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2f41-153">См. также</span><span class="sxs-lookup"><span data-stu-id="e2f41-153">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="e2f41-154">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="e2f41-154">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e2f41-155">Привязки</span><span class="sxs-lookup"><span data-stu-id="e2f41-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e2f41-156">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="e2f41-156">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e2f41-157">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="e2f41-157">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="e2f41-158">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="e2f41-158">\<binding></span></span>](bindings.md)
