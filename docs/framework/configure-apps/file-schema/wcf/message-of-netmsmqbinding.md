---
title: <message> из <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: c623b7daf1e91c9c1800b9653525cd51b1087506
ms.sourcegitcommit: 5c2176883dc3107445702724a7caa7ac2f6cb0d3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2019
ms.locfileid: "58890570"
---
# <a name="message-of-netmsmqbinding"></a><span data-ttu-id="e0728-102">\<сообщение > из \<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="e0728-102">\<message> of \<netMsmqBinding></span></span>

<span data-ttu-id="e0728-103">Определяет параметры безопасности сообщений SOAP для данной привязки `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="e0728-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>

```xml
<system.ServiceModel>
  <bindings>
    <netMsmqBinding>
      <binding>
        <security>
          <message>
```

## <a name="syntax"></a><span data-ttu-id="e0728-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0728-104">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="e0728-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e0728-105">Attributes and Elements</span></span>

<span data-ttu-id="e0728-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e0728-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="e0728-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e0728-107">Attributes</span></span>

|<span data-ttu-id="e0728-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e0728-108">Attribute</span></span>|<span data-ttu-id="e0728-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e0728-109">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="e0728-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="e0728-110">algorithmSuite</span></span>|<span data-ttu-id="e0728-111">Задает алгоритмы шифрования сообщений и ключей, которые используются для обеспечения безопасности на уровне сообщений для сообщений, которые отправляются с помощью транспорта MSMQ.</span><span class="sxs-lookup"><span data-stu-id="e0728-111">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="e0728-112">Значение по умолчанию — `Aes256`.</span><span class="sxs-lookup"><span data-stu-id="e0728-112">The default value is `Aes256`.</span></span> <span data-ttu-id="e0728-113">Это атрибут типа <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="e0728-113">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|
|<span data-ttu-id="e0728-114">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="e0728-114">clientCredentialType</span></span>|<span data-ttu-id="e0728-115">Задает тип учетных данных, используемых при проверке подлинности клиента для сообщений, которые отправляются с помощью транспорта MSMQ.</span><span class="sxs-lookup"><span data-stu-id="e0728-115">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="e0728-116">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="e0728-116">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e0728-117">-None: Данный атрибут позволяет службе взаимодействовать с анонимными клиентами.</span><span class="sxs-lookup"><span data-stu-id="e0728-117">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="e0728-118">Как для службы, так и для клиента учетные данные не требуются.</span><span class="sxs-lookup"><span data-stu-id="e0728-118">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="e0728-119">-Windows: Это позволяет проводить проверку подлинности учетных данных Windows обмен сообщениями SOAP.</span><span class="sxs-lookup"><span data-stu-id="e0728-119">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="e0728-120">В этом случае всегда выполняется проверка подлинности на основе Kerberos.</span><span class="sxs-lookup"><span data-stu-id="e0728-120">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="e0728-121">-UserName: Это позволяет службе запрашивать проверку подлинности клиента с помощью имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="e0728-121">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="e0728-122">В этом случае учетные данные должны быть определены с помощью `clientCredentials` поведение **осторожность:**  Windows Communication Foundation (WCF) не поддерживает передачу хэш-кода пароля или получение ключей с помощью пароля и использование таких ключей для обеспечения безопасности сообщений.</span><span class="sxs-lookup"><span data-stu-id="e0728-122">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="e0728-123">Таким образом WCF обеспечивает безопасность обмена при использовании учетных данных UserName.</span><span class="sxs-lookup"><span data-stu-id="e0728-123">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="e0728-124">В данном режиме требуется, чтобы сертификат службы был указан на стороне клиента при помощи поведения `clientCredential` и при помощи `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="e0728-124">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="e0728-125">-Сертификат: Это позволяет службе требовать проверки подлинности клиента с помощью сертификата.</span><span class="sxs-lookup"><span data-stu-id="e0728-125">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="e0728-126">В этом случае учетные данные клиента должны быть определены с помощью поведения `clientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="e0728-126">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="e0728-127">Учетные данные службы в данном случае должны быть определены с помощью поведения `clientCredentials`, которому задается значение `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="e0728-127">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="e0728-128">-CardSpace: Это позволяет службе требовать проверки подлинности клиента с помощью CardSpace.</span><span class="sxs-lookup"><span data-stu-id="e0728-128">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="e0728-129">Необходимо определить `serviceCertificate` в поведении `clientCredential`.</span><span class="sxs-lookup"><span data-stu-id="e0728-129">The `serviceCertificate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="e0728-130">Значение по умолчанию — `Windows`.</span><span class="sxs-lookup"><span data-stu-id="e0728-130">The default value is `Windows`.</span></span> <span data-ttu-id="e0728-131">Это атрибут типа <xref:System.ServiceModel.MessageCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="e0728-131">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="e0728-132">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e0728-132">Child Elements</span></span>

<span data-ttu-id="e0728-133">Нет</span><span class="sxs-lookup"><span data-stu-id="e0728-133">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e0728-134">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e0728-134">Parent Elements</span></span>

|<span data-ttu-id="e0728-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="e0728-135">Element</span></span>|<span data-ttu-id="e0728-136">Описание</span><span class="sxs-lookup"><span data-stu-id="e0728-136">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e0728-137">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="e0728-137">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="e0728-138">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="e0728-138">Defines the security settings for a binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="e0728-139">См. также</span><span class="sxs-lookup"><span data-stu-id="e0728-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [<span data-ttu-id="e0728-140">Очереди в WCF</span><span class="sxs-lookup"><span data-stu-id="e0728-140">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="e0728-141">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="e0728-141">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e0728-142">Привязки</span><span class="sxs-lookup"><span data-stu-id="e0728-142">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="e0728-143">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="e0728-143">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e0728-144">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="e0728-144">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="e0728-145">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="e0728-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
