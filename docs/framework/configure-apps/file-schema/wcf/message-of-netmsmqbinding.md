---
title: <message> из <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: 5a4a4e8b645ee2c607988ac3031af537c93ca8c0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736758"
---
# <a name="message-of-netmsmqbinding"></a><span data-ttu-id="f3aa6-102">> сообщения \<\<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="f3aa6-102">\<message> of \<netMsmqBinding></span></span>

<span data-ttu-id="f3aa6-103">Определяет параметры безопасности сообщений SOAP для данной привязки `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="f3aa6-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>

<span data-ttu-id="f3aa6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f3aa6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f3aa6-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f3aa6-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f3aa6-106">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="f3aa6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="f3aa6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netMsmqBinding >** ](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="f3aa6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)</span></span>\
<span data-ttu-id="f3aa6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="f3aa6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="f3aa6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<security >** ](security-of-netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="f3aa6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)</span></span>\
<span data-ttu-id="f3aa6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**сообщение >**</span><span class="sxs-lookup"><span data-stu-id="f3aa6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="f3aa6-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3aa6-111">Syntax</span></span>

```xml
<netMsmqBinding>
  <binding>
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
    </security>
  </binding>
</netMsmqBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f3aa6-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f3aa6-112">Attributes and Elements</span></span>

<span data-ttu-id="f3aa6-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f3aa6-113">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f3aa6-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f3aa6-114">Attributes</span></span>

|<span data-ttu-id="f3aa6-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f3aa6-115">Attribute</span></span>|<span data-ttu-id="f3aa6-116">Описание</span><span class="sxs-lookup"><span data-stu-id="f3aa6-116">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="f3aa6-117">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="f3aa6-117">algorithmSuite</span></span>|<span data-ttu-id="f3aa6-118">Задает алгоритмы шифрования сообщений и ключей, которые используются для обеспечения безопасности на уровне сообщений для сообщений, которые отправляются с помощью транспорта MSMQ.</span><span class="sxs-lookup"><span data-stu-id="f3aa6-118">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="f3aa6-119">Значение по умолчанию — `Aes256`.</span><span class="sxs-lookup"><span data-stu-id="f3aa6-119">The default value is `Aes256`.</span></span> <span data-ttu-id="f3aa6-120">Это атрибут типа <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="f3aa6-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|
|<span data-ttu-id="f3aa6-121">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="f3aa6-121">clientCredentialType</span></span>|<span data-ttu-id="f3aa6-122">Задает тип учетных данных, используемых при проверке подлинности клиента для сообщений, которые отправляются с помощью транспорта MSMQ.</span><span class="sxs-lookup"><span data-stu-id="f3aa6-122">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="f3aa6-123">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f3aa6-123">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f3aa6-124">-None: Это позволяет службе взаимодействовать с анонимными клиентами.</span><span class="sxs-lookup"><span data-stu-id="f3aa6-124">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="f3aa6-125">Как для службы, так и для клиента учетные данные не требуются.</span><span class="sxs-lookup"><span data-stu-id="f3aa6-125">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="f3aa6-126">-Windows: Это позволяет обмениваться сообщениями SOAP в контексте с проверкой подлинности учетных данных Windows.</span><span class="sxs-lookup"><span data-stu-id="f3aa6-126">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="f3aa6-127">В этом случае всегда выполняется проверка подлинности на основе Kerberos.</span><span class="sxs-lookup"><span data-stu-id="f3aa6-127">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="f3aa6-128">-UserName: Это позволяет службе требовать проверку подлинности клиента с помощью учетных данных имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="f3aa6-128">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="f3aa6-129">Учетные данные в этом случае необходимо указывать с помощью `clientCredentials` **внимание:** Windows Communication Foundation (WCF) не поддерживает отправку дайджеста пароля или получение ключей с помощью пароля и использование таких ключей для обеспечения безопасности сообщений.</span><span class="sxs-lookup"><span data-stu-id="f3aa6-129">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="f3aa6-130">Таким образом, WCF обеспечивает защиту Exchange при использовании учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="f3aa6-130">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="f3aa6-131">В данном режиме требуется, чтобы сертификат службы был указан на стороне клиента при помощи поведения `clientCredential` и при помощи `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="f3aa6-131">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="f3aa6-132">-Certificate: Это позволяет службе требовать проверку подлинности клиента с помощью сертификата.</span><span class="sxs-lookup"><span data-stu-id="f3aa6-132">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="f3aa6-133">В этом случае учетные данные клиента должны быть определены с помощью поведения `clientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="f3aa6-133">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="f3aa6-134">Учетные данные службы в данном случае должны быть определены с помощью поведения `clientCredentials`, которому задается значение `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="f3aa6-134">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="f3aa6-135">-CardSpace: Это позволяет службе требовать проверку подлинности клиента с помощью CardSpace.</span><span class="sxs-lookup"><span data-stu-id="f3aa6-135">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="f3aa6-136">Необходимо определить `serviceCertificate` в поведении `clientCredential`.</span><span class="sxs-lookup"><span data-stu-id="f3aa6-136">The `serviceCertificate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="f3aa6-137">Значение по умолчанию — `Windows`.</span><span class="sxs-lookup"><span data-stu-id="f3aa6-137">The default value is `Windows`.</span></span> <span data-ttu-id="f3aa6-138">Это атрибут типа <xref:System.ServiceModel.MessageCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="f3aa6-138">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="f3aa6-139">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f3aa6-139">Child Elements</span></span>

<span data-ttu-id="f3aa6-140">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="f3aa6-140">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f3aa6-141">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f3aa6-141">Parent Elements</span></span>

|<span data-ttu-id="f3aa6-142">Элемент</span><span class="sxs-lookup"><span data-stu-id="f3aa6-142">Element</span></span>|<span data-ttu-id="f3aa6-143">Описание</span><span class="sxs-lookup"><span data-stu-id="f3aa6-143">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f3aa6-144">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="f3aa6-144">\<security></span></span>](security-of-netmsmqbinding.md)|<span data-ttu-id="f3aa6-145">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="f3aa6-145">Defines the security settings for a binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="f3aa6-146">См. также</span><span class="sxs-lookup"><span data-stu-id="f3aa6-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [<span data-ttu-id="f3aa6-147">Очереди в WCF</span><span class="sxs-lookup"><span data-stu-id="f3aa6-147">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="f3aa6-148">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="f3aa6-148">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="f3aa6-149">Привязки</span><span class="sxs-lookup"><span data-stu-id="f3aa6-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f3aa6-150">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="f3aa6-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f3aa6-151">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="f3aa6-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="f3aa6-152">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="f3aa6-152">\<binding></span></span>](bindings.md)
