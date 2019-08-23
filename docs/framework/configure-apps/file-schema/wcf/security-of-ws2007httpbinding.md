---
title: <security> из <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
ms.openlocfilehash: a895df027bee7430e51e76c480136a49b6b2a0be
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936579"
---
# <a name="security-of-ws2007httpbinding"></a><span data-ttu-id="d5746-102">\<> безопасности > \<WS2007HttpBinding</span><span class="sxs-lookup"><span data-stu-id="d5746-102">\<security> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="d5746-103">Представляет параметры безопасности, используемые с [ \<элементом > WS2007HttpBinding](ws2007httpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="d5746-103">Represents the security settings used with the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>  
  
 <span data-ttu-id="d5746-104">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="d5746-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d5746-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="d5746-105">\<bindings></span></span>  
<span data-ttu-id="d5746-106">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="d5746-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="d5746-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="d5746-107">\<binding></span></span>  
<span data-ttu-id="d5746-108">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="d5746-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5746-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5746-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5746-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d5746-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d5746-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d5746-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5746-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d5746-112">Attributes</span></span>  
  
|<span data-ttu-id="d5746-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d5746-113">Attribute</span></span>|<span data-ttu-id="d5746-114">Описание</span><span class="sxs-lookup"><span data-stu-id="d5746-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="d5746-115">Используемых.</span><span class="sxs-lookup"><span data-stu-id="d5746-115">-   Optional.</span></span> <span data-ttu-id="d5746-116">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="d5746-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="d5746-117">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="d5746-117">The default is `Message`.</span></span><br /><br /> <span data-ttu-id="d5746-118">Это атрибут типа <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="d5746-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="d5746-119">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="d5746-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="d5746-120">Значение</span><span class="sxs-lookup"><span data-stu-id="d5746-120">Value</span></span>|<span data-ttu-id="d5746-121">Описание</span><span class="sxs-lookup"><span data-stu-id="d5746-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="d5746-122">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="d5746-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="d5746-123">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d5746-123">Security is provided using HTTPS.</span></span> <span data-ttu-id="d5746-124">Необходима настройка службы с помощью SSL-сертификатов.</span><span class="sxs-lookup"><span data-stu-id="d5746-124">The service must be configured with Secure Sockets Layer (SSL) certificates.</span></span> <span data-ttu-id="d5746-125">Сообщение полностью защищено с помощью HTTPS, а проверка подлинности службы выполняется клиентом с помощью SSL-сертификата службы.</span><span class="sxs-lookup"><span data-stu-id="d5746-125">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="d5746-126">Проверка подлинности клиента контролируется `ClientCredentials` с помощью атрибута [ \<элемента Transport >](transport-of-ws2007httpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="d5746-126">The client authentication is controlled through the `ClientCredentials` attribute of the [\<transport>](transport-of-ws2007httpbinding.md) element.</span></span>|  
|`Message`|<span data-ttu-id="d5746-127">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="d5746-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="d5746-128">По умолчанию текст сообщений SOAP шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="d5746-128">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="d5746-129">Этот режим предоставляет множество возможностей, например доступ к учетным данным службы для клиентов за пределами диапазона, выбор используемого набора алгоритмов и уровня защиты, применяемого к тексту сообщения посредством <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span><span class="sxs-lookup"><span data-stu-id="d5746-129">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span></span> <span data-ttu-id="d5746-130">Проверка подлинности клиента выполняется один раз для каждого сеанса, и результаты проверки сохраняются в кэше на протяжении всего сеанса.</span><span class="sxs-lookup"><span data-stu-id="d5746-130">Client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="d5746-131">В данном режиме HTTPS обеспечивает целостность, конфиденциальность и проверку подлинности сервера, а механизм безопасности сообщений SOAP обеспечивает проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="d5746-131">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="d5746-132">По умолчанию проверка подлинности клиента выполняется один раз за сеанс, и результаты проверки сохраняются в кэше на протяжении всего сеанса.</span><span class="sxs-lookup"><span data-stu-id="d5746-132">By default, client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d5746-133">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d5746-133">Child Elements</span></span>  
  
|<span data-ttu-id="d5746-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="d5746-134">Element</span></span>|<span data-ttu-id="d5746-135">Описание</span><span class="sxs-lookup"><span data-stu-id="d5746-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5746-136">\<> транспорта</span><span class="sxs-lookup"><span data-stu-id="d5746-136">\<transport></span></span>](transport-of-ws2007httpbinding.md)|<span data-ttu-id="d5746-137">Определяет параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="d5746-137">Defines the transport security settings.</span></span> <span data-ttu-id="d5746-138">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="d5746-138">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span> <span data-ttu-id="d5746-139">Эти параметры применяются только в том случае, если режим имеет значение Transport.</span><span class="sxs-lookup"><span data-stu-id="d5746-139">These settings are applied only when the mode is set to Transport.</span></span>|  
|[<span data-ttu-id="d5746-140">\<> сообщения</span><span class="sxs-lookup"><span data-stu-id="d5746-140">\<message></span></span>](message-of-ws2007httpbinding.md)|<span data-ttu-id="d5746-141">Определяет параметры безопасности сообщения.</span><span class="sxs-lookup"><span data-stu-id="d5746-141">Defines the security settings for the message.</span></span> <span data-ttu-id="d5746-142">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="d5746-142">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span> <span data-ttu-id="d5746-143">Эти параметры неприменимы, если режим имеет значение Transport.</span><span class="sxs-lookup"><span data-stu-id="d5746-143">These settings are not applied when the mode is set to Transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d5746-144">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d5746-144">Parent Elements</span></span>  
  
|<span data-ttu-id="d5746-145">Элемент</span><span class="sxs-lookup"><span data-stu-id="d5746-145">Element</span></span>|<span data-ttu-id="d5746-146">Описание</span><span class="sxs-lookup"><span data-stu-id="d5746-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5746-147">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="d5746-147">\<ws2007HttpBinding></span></span>](ws2007httpbinding.md)|<span data-ttu-id="d5746-148">Привязка безопасности для приложений транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="d5746-148">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5746-149">Примечания</span><span class="sxs-lookup"><span data-stu-id="d5746-149">Remarks</span></span>  
 <span data-ttu-id="d5746-150">Этот элемент предназначен для взаимодействия со службами, реализующими спецификации WS-\*.</span><span class="sxs-lookup"><span data-stu-id="d5746-150">This element is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="d5746-151">Безопасность транспорта для этой привязки обеспечивается посредством протокола SSL по протоколам HTTP или HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d5746-151">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5746-152">См. также</span><span class="sxs-lookup"><span data-stu-id="d5746-152">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="d5746-153">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="d5746-153">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="d5746-154">Привязки</span><span class="sxs-lookup"><span data-stu-id="d5746-154">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d5746-155">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="d5746-155">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d5746-156">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="d5746-156">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="d5746-157">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="d5746-157">\<binding></span></span>](../../../misc/binding.md)
