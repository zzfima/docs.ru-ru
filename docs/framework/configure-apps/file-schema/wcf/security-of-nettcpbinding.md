---
title: '&lt;security&gt; для &lt;netTcpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 286cd191-4fd5-4c4e-a223-9c71cf7fdead
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 13aeb3261fdb9689caa1dea1ec7382fdb9d9b1ce
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516977"
---
# <a name="ltsecuritygt-of-ltnettcpbindinggt"></a><span data-ttu-id="a79cf-102">&lt;security&gt; для &lt;netTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="a79cf-102">&lt;security&gt; of &lt;netTcpBinding&gt;</span></span>
<span data-ttu-id="a79cf-103">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="a79cf-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="a79cf-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a79cf-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a79cf-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="a79cf-105">\<bindings></span></span>  
<span data-ttu-id="a79cf-106">\<netTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="a79cf-106">\<netTcpBinding></span></span>  
<span data-ttu-id="a79cf-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="a79cf-107">\<binding></span></span>  
<span data-ttu-id="a79cf-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="a79cf-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a79cf-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a79cf-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">  
   <transport  
      clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
           protectionLevel="None/Sign/EncryptAndSign" />  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a79cf-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a79cf-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a79cf-111">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a79cf-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a79cf-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a79cf-112">Attributes</span></span>  
  
|<span data-ttu-id="a79cf-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a79cf-113">Attribute</span></span>|<span data-ttu-id="a79cf-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a79cf-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a79cf-115">режим</span><span class="sxs-lookup"><span data-stu-id="a79cf-115">mode</span></span>|<span data-ttu-id="a79cf-116">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="a79cf-116">Optional.</span></span> <span data-ttu-id="a79cf-117">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="a79cf-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="a79cf-118">Ниже приведены допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="a79cf-118">Valid values are shown below.</span></span> <span data-ttu-id="a79cf-119">Значение по умолчанию — `Transport`.</span><span class="sxs-lookup"><span data-stu-id="a79cf-119">The default value is `Transport`.</span></span><br /><br /> <span data-ttu-id="a79cf-120">Это атрибут типа <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="a79cf-120">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="a79cf-121">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="a79cf-121">mode Attribute</span></span>  
  
|<span data-ttu-id="a79cf-122">Значение</span><span class="sxs-lookup"><span data-stu-id="a79cf-122">Value</span></span>|<span data-ttu-id="a79cf-123">Описание</span><span class="sxs-lookup"><span data-stu-id="a79cf-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a79cf-124">Нет</span><span class="sxs-lookup"><span data-stu-id="a79cf-124">None</span></span>|<span data-ttu-id="a79cf-125">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="a79cf-125">Security is disabled.</span></span>|  
|<span data-ttu-id="a79cf-126">Transport</span><span class="sxs-lookup"><span data-stu-id="a79cf-126">Transport</span></span>|<span data-ttu-id="a79cf-127">Безопасность транспорта обеспечивается с помощью TLS через TCP или SPNego.</span><span class="sxs-lookup"><span data-stu-id="a79cf-127">Transport security is provided using TLS over TCP or SPNego.</span></span> <span data-ttu-id="a79cf-128">Может потребоваться настроить службу с использованием сертификатов SSL.</span><span class="sxs-lookup"><span data-stu-id="a79cf-128">The service may need to be configured with SSL certificates.</span></span> <span data-ttu-id="a79cf-129">Этот режим позволяет контролировать уровень защиты.</span><span class="sxs-lookup"><span data-stu-id="a79cf-129">It is possible to control the protection level with this mode.</span></span>|  
|<span data-ttu-id="a79cf-130">Сообщение</span><span class="sxs-lookup"><span data-stu-id="a79cf-130">Message</span></span>|<span data-ttu-id="a79cf-131">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="a79cf-131">Security is provided using SOAP message security.</span></span> <span data-ttu-id="a79cf-132">По умолчанию текст сообщений SOAP шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="a79cf-132">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="a79cf-133">Этот режим предоставляет множество функций, таких как сведения о доступности учетных данных службы для клиентов за пределами диапазона, об используемом наборе алгоритмов и об уровне защиты, применяемом к тексту сообщения.</span><span class="sxs-lookup"><span data-stu-id="a79cf-133">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body.</span></span> <span data-ttu-id="a79cf-134">Проверка подлинности клиента выполняется один раз за сеанс, и результаты проверки сохраняются в кэше на протяжении всего сеанса.</span><span class="sxs-lookup"><span data-stu-id="a79cf-134">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="a79cf-135">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="a79cf-135">TransportWithMessageCredential</span></span>|<span data-ttu-id="a79cf-136">Безопасность транспорта связана с безопасностью сообщения.</span><span class="sxs-lookup"><span data-stu-id="a79cf-136">Transport security is coupled with message security.</span></span> <span data-ttu-id="a79cf-137">Безопасность транспорта обеспечивается протоколом TLS через TCP, или SPNego, и гарантирует целостность, конфиденциальность и проверку подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="a79cf-137">Transport security is provided by TLS over TCP, or SPNego, and ensures integrity, confidentiality, and server authentication.</span></span> <span data-ttu-id="a79cf-138">Безопасность сообщений SOAP представляет проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="a79cf-138">SOAP message security provides client authentication.</span></span> <span data-ttu-id="a79cf-139">По умолчанию проверка подлинности клиента выполняется один раз за сеанс, и результаты проверки сохраняются в кэше на протяжении всего сеанса.</span><span class="sxs-lookup"><span data-stu-id="a79cf-139">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a79cf-140">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a79cf-140">Child Elements</span></span>  
  
|<span data-ttu-id="a79cf-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="a79cf-141">Element</span></span>|<span data-ttu-id="a79cf-142">Описание</span><span class="sxs-lookup"><span data-stu-id="a79cf-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a79cf-143">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="a79cf-143">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)|<span data-ttu-id="a79cf-144">Определяет параметры безопасности для данного транспорта.</span><span class="sxs-lookup"><span data-stu-id="a79cf-144">Defines the security settings for the transport.</span></span> <span data-ttu-id="a79cf-145">Это элемент типа <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="a79cf-145">This element is of type <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>.</span></span>|  
|[<span data-ttu-id="a79cf-146">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="a79cf-146">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)|<span data-ttu-id="a79cf-147">Определяет параметры безопасности сообщения.</span><span class="sxs-lookup"><span data-stu-id="a79cf-147">Defines the security settings for the message.</span></span> <span data-ttu-id="a79cf-148">Это элемент типа <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>.</span><span class="sxs-lookup"><span data-stu-id="a79cf-148">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a79cf-149">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a79cf-149">Parent Elements</span></span>  
  
|<span data-ttu-id="a79cf-150">Элемент</span><span class="sxs-lookup"><span data-stu-id="a79cf-150">Element</span></span>|<span data-ttu-id="a79cf-151">Описание</span><span class="sxs-lookup"><span data-stu-id="a79cf-151">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a79cf-152">привязка</span><span class="sxs-lookup"><span data-stu-id="a79cf-152">binding</span></span>|<span data-ttu-id="a79cf-153">Элемент привязки [ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="a79cf-153">The binding element of the [\<netTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a79cf-154">Примечания</span><span class="sxs-lookup"><span data-stu-id="a79cf-154">Remarks</span></span>  
 <span data-ttu-id="a79cf-155">Каждая из стандартных привязок предоставляет параметры для управления требованиями безопасности перемещения.</span><span class="sxs-lookup"><span data-stu-id="a79cf-155">Each of the standard bindings provides parameters for controlling the transfer security requirements.</span></span> <span data-ttu-id="a79cf-156">Эти параметры, как правило, включают режим безопасности, определяющий, используется ли безопасность уровня сообщения или уровня транспорта, а также выбор типа учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="a79cf-156">These parameters typically include the security mode that specified whether message-level or transport-level security is used and the choice of client credential type.</span></span> <span data-ttu-id="a79cf-157">На основании предоставленного выбора параметров создается стек каналов с соответствующей безопасностью.</span><span class="sxs-lookup"><span data-stu-id="a79cf-157">Based on the choice of options these parameters present, a channel stack is constructed with appropriate security.</span></span>  
  
 <span data-ttu-id="a79cf-158">Предоставляемые системой привязки, поставляемые Windows Communication Foundation (WCF), представляют собой набор, отвечающий требованиям наиболее распространенных сценариев.</span><span class="sxs-lookup"><span data-stu-id="a79cf-158">The system-provided bindings supplied by Windows Communication Foundation (WCF) are a set designed to meet some of the most common scenario requirements.</span></span> <span data-ttu-id="a79cf-159">Каждая из этих привязок позволяет задавать требования безопасности для некоторых конкретных целевых сценариев.</span><span class="sxs-lookup"><span data-stu-id="a79cf-159">Each of these bindings allows the specification of security requirements for some specific targeted scenarios.</span></span>  
  
 <span data-ttu-id="a79cf-160">Элемент конфигурации предоставляет спецификации безопасности для `netTcpBinding`.</span><span class="sxs-lookup"><span data-stu-id="a79cf-160">This configuration element provides the security specifications for `netTcpBinding`.</span></span> <span data-ttu-id="a79cf-161">Это безопасная, надежная и оптимизированная привязка, пригодная для обмена данными между компьютерами.</span><span class="sxs-lookup"><span data-stu-id="a79cf-161">This is a secure, reliable, optimized binding suitable for cross-machine communication.</span></span> <span data-ttu-id="a79cf-162">По умолчанию она создает стек связи среды выполнения, поддерживающий протокол TCP для доставки сообщений и безопасность Windows для безопасности сообщений и проверки подлинности, WS-ReliableMessaging для надежности, а также кодирование двоичных сообщений.</span><span class="sxs-lookup"><span data-stu-id="a79cf-162">By default it generates a runtime communication stack supporting TCP for message delivery and Windows Security for message security and authentication, WS-ReliableMessaging for reliability, and binary message encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a79cf-163">См. также</span><span class="sxs-lookup"><span data-stu-id="a79cf-163">See Also</span></span>  
 <xref:System.ServiceModel.NetTcpSecurity>  
 <xref:System.ServiceModel.NetTcpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetTcpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>  
 [<span data-ttu-id="a79cf-164">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="a79cf-164">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="a79cf-165">Привязки</span><span class="sxs-lookup"><span data-stu-id="a79cf-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="a79cf-166">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="a79cf-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="a79cf-167">Использование привязок для настройки службы Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="a79cf-167">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="a79cf-168">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="a79cf-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
