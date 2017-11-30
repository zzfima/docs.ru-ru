---
title: "&lt;message&gt; для &lt;netMsmqBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f3b03fcce02c51563ed006e62a3f77f76bede777
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltmessagegt-of-ltnetmsmqbindinggt"></a><span data-ttu-id="ecb85-102">&lt;message&gt; для &lt;netMsmqBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="ecb85-102">&lt;message&gt; of &lt;netMsmqBinding&gt;</span></span>
<span data-ttu-id="ecb85-103">Определяет параметры безопасности сообщений SOAP для данной привязки `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="ecb85-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>  
  
 <span data-ttu-id="ecb85-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ecb85-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ecb85-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="ecb85-105">\<bindings></span></span>  
<span data-ttu-id="ecb85-106">\<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="ecb85-106">\<netMsmqBinding></span></span>  
<span data-ttu-id="ecb85-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="ecb85-107">\<binding></span></span>  
<span data-ttu-id="ecb85-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="ecb85-108">\<security></span></span>  
<span data-ttu-id="ecb85-109">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="ecb85-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecb85-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ecb85-110">Syntax</span></span>  
  
```xml  
<netMsmqBinding>  
    <binding>  
      <security>  
         <message   
                      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />  
    </security>  
</netMsmqBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ecb85-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ecb85-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ecb85-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ecb85-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ecb85-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ecb85-113">Attributes</span></span>  
  
|<span data-ttu-id="ecb85-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ecb85-114">Attribute</span></span>|<span data-ttu-id="ecb85-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ecb85-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ecb85-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="ecb85-116">algorithmSuite</span></span>|<span data-ttu-id="ecb85-117">Задает алгоритмы шифрования сообщений и ключей, которые используются для обеспечения безопасности на уровне сообщений для сообщений, которые отправляются с помощью транспорта MSMQ.</span><span class="sxs-lookup"><span data-stu-id="ecb85-117">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="ecb85-118">Значение по умолчанию — `Aes256`.</span><span class="sxs-lookup"><span data-stu-id="ecb85-118">The default value is `Aes256`.</span></span> <span data-ttu-id="ecb85-119">Это атрибут типа <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="ecb85-119">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|  
|<span data-ttu-id="ecb85-120">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="ecb85-120">clientCredentialType</span></span>|<span data-ttu-id="ecb85-121">Задает тип учетных данных, используемых при проверке подлинности клиента для сообщений, которые отправляются с помощью транспорта MSMQ.</span><span class="sxs-lookup"><span data-stu-id="ecb85-121">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="ecb85-122">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="ecb85-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ecb85-123">— None: Данное значение позволяет службе взаимодействовать с анонимными клиентами.</span><span class="sxs-lookup"><span data-stu-id="ecb85-123">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="ecb85-124">Как для службы, так и для клиента учетные данные не требуются.</span><span class="sxs-lookup"><span data-stu-id="ecb85-124">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="ecb85-125">-Windows: Это позволяет проводить проверку подлинности учетных данных Windows обмен сообщениями SOAP.</span><span class="sxs-lookup"><span data-stu-id="ecb85-125">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="ecb85-126">В этом случае всегда выполняется проверка подлинности на основе Kerberos.</span><span class="sxs-lookup"><span data-stu-id="ecb85-126">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="ecb85-127">-UserName: Данное значение позволяет службе требовать проверку подлинности клиента с помощью учетных данных UserName.</span><span class="sxs-lookup"><span data-stu-id="ecb85-127">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="ecb85-128">В этом случае необходимо указать с помощью учетных данных `clientCredentials` поведение **осторожность:** [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] не поддерживает отправку пароля хэш-кода или получение ключей с использованием пароля и использование таких ключей для обеспечения безопасности сообщений.  </span><span class="sxs-lookup"><span data-stu-id="ecb85-128">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="ecb85-129">Таким образом, служба [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] принудительно обеспечивает безопасность обмена при использовании учетных данных UserName.</span><span class="sxs-lookup"><span data-stu-id="ecb85-129">Therefore, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="ecb85-130">В данном режиме требуется, чтобы сертификат службы был указан на стороне клиента при помощи поведения `clientCredential` и при помощи `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="ecb85-130">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="ecb85-131">-Certificate: Данное значение позволяет службе требовать проверки подлинности клиента с помощью сертификата.</span><span class="sxs-lookup"><span data-stu-id="ecb85-131">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="ecb85-132">В этом случае учетные данные клиента должны быть определены с помощью поведения `clientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="ecb85-132">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="ecb85-133">Учетные данные службы в данном случае должны быть определены с помощью поведения `clientCredentials`, которому задается значение `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="ecb85-133">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="ecb85-134">-CardSpace: Данное значение позволяет службе требовать проверки подлинности клиента с помощью CardSpace.</span><span class="sxs-lookup"><span data-stu-id="ecb85-134">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="ecb85-135">Необходимо определить `serviceCertiifcate` в поведении `clientCredential`.</span><span class="sxs-lookup"><span data-stu-id="ecb85-135">The `serviceCertiifcate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="ecb85-136">Значение по умолчанию — `Windows`.</span><span class="sxs-lookup"><span data-stu-id="ecb85-136">The default value is `Windows`.</span></span> <span data-ttu-id="ecb85-137">Это атрибут типа <xref:System.ServiceModel.MessageCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="ecb85-137">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ecb85-138">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ecb85-138">Child Elements</span></span>  
 <span data-ttu-id="ecb85-139">Нет</span><span class="sxs-lookup"><span data-stu-id="ecb85-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ecb85-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ecb85-140">Parent Elements</span></span>  
  
|<span data-ttu-id="ecb85-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="ecb85-141">Element</span></span>|<span data-ttu-id="ecb85-142">Описание</span><span class="sxs-lookup"><span data-stu-id="ecb85-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ecb85-143">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="ecb85-143">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="ecb85-144">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="ecb85-144">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ecb85-145">См. также</span><span class="sxs-lookup"><span data-stu-id="ecb85-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>  
 <xref:System.ServiceModel.MessageSecurityOverMsmq>  
 [<span data-ttu-id="ecb85-146">Очереди в WCF</span><span class="sxs-lookup"><span data-stu-id="ecb85-146">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="ecb85-147">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="ecb85-147">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="ecb85-148">Привязки</span><span class="sxs-lookup"><span data-stu-id="ecb85-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="ecb85-149">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="ecb85-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="ecb85-150">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="ecb85-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="ecb85-151">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="ecb85-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
