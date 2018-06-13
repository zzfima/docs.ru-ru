---
title: '&lt;message&gt; для &lt;netMsmqBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: 0e947667c414079f24398b401456efd56bf9922c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358561"
---
# <a name="ltmessagegt-of-ltnetmsmqbindinggt"></a><span data-ttu-id="1cbf8-102">&lt;message&gt; для &lt;netMsmqBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="1cbf8-102">&lt;message&gt; of &lt;netMsmqBinding&gt;</span></span>
<span data-ttu-id="1cbf8-103">Определяет параметры безопасности сообщений SOAP для данной привязки `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>  
  
 <span data-ttu-id="1cbf8-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1cbf8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1cbf8-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="1cbf8-105">\<bindings></span></span>  
<span data-ttu-id="1cbf8-106">\<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="1cbf8-106">\<netMsmqBinding></span></span>  
<span data-ttu-id="1cbf8-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="1cbf8-107">\<binding></span></span>  
<span data-ttu-id="1cbf8-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="1cbf8-108">\<security></span></span>  
<span data-ttu-id="1cbf8-109">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="1cbf8-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cbf8-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1cbf8-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1cbf8-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1cbf8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1cbf8-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1cbf8-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1cbf8-113">Attributes</span></span>  
  
|<span data-ttu-id="1cbf8-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1cbf8-114">Attribute</span></span>|<span data-ttu-id="1cbf8-115">Описание</span><span class="sxs-lookup"><span data-stu-id="1cbf8-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1cbf8-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="1cbf8-116">algorithmSuite</span></span>|<span data-ttu-id="1cbf8-117">Задает алгоритмы шифрования сообщений и ключей, которые используются для обеспечения безопасности на уровне сообщений для сообщений, которые отправляются с помощью транспорта MSMQ.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-117">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="1cbf8-118">Значение по умолчанию — `Aes256`.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-118">The default value is `Aes256`.</span></span> <span data-ttu-id="1cbf8-119">Это атрибут типа <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-119">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|  
|<span data-ttu-id="1cbf8-120">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="1cbf8-120">clientCredentialType</span></span>|<span data-ttu-id="1cbf8-121">Задает тип учетных данных, используемых при проверке подлинности клиента для сообщений, которые отправляются с помощью транспорта MSMQ.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-121">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="1cbf8-122">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="1cbf8-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1cbf8-123">— None: Данное значение позволяет службе взаимодействовать с анонимными клиентами.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-123">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="1cbf8-124">Как для службы, так и для клиента учетные данные не требуются.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-124">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="1cbf8-125">-Windows: Это позволяет проводить проверку подлинности учетных данных Windows обмен сообщениями SOAP.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-125">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="1cbf8-126">В этом случае всегда выполняется проверка подлинности на основе Kerberos.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-126">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="1cbf8-127">-UserName: Данное значение позволяет службе требовать проверку подлинности клиента с помощью учетных данных UserName.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-127">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="1cbf8-128">В этом случае необходимо указать с помощью учетных данных `clientCredentials` поведение **осторожность:** Windows Communication Foundation (WCF) не поддерживает отправку хэш-кода или получение ключей с использованием пароля и использование таких ключей для пароля безопасность сообщений.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-128">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="1cbf8-129">Таким образом WCF принудительно обеспечивает безопасность обмена данными при использовании учетных данных UserName.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-129">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="1cbf8-130">В данном режиме требуется, чтобы сертификат службы был указан на стороне клиента при помощи поведения `clientCredential` и при помощи `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-130">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="1cbf8-131">-Certificate: Данное значение позволяет службе требовать проверки подлинности клиента с помощью сертификата.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-131">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="1cbf8-132">В этом случае учетные данные клиента должны быть определены с помощью поведения `clientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-132">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="1cbf8-133">Учетные данные службы в данном случае должны быть определены с помощью поведения `clientCredentials`, которому задается значение `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-133">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="1cbf8-134">-CardSpace: Данное значение позволяет службе требовать проверки подлинности клиента с помощью CardSpace.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-134">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="1cbf8-135">Необходимо определить `serviceCertiifcate` в поведении `clientCredential`.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-135">The `serviceCertiifcate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="1cbf8-136">Значение по умолчанию — `Windows`.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-136">The default value is `Windows`.</span></span> <span data-ttu-id="1cbf8-137">Это атрибут типа <xref:System.ServiceModel.MessageCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-137">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1cbf8-138">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1cbf8-138">Child Elements</span></span>  
 <span data-ttu-id="1cbf8-139">Нет</span><span class="sxs-lookup"><span data-stu-id="1cbf8-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1cbf8-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1cbf8-140">Parent Elements</span></span>  
  
|<span data-ttu-id="1cbf8-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="1cbf8-141">Element</span></span>|<span data-ttu-id="1cbf8-142">Описание</span><span class="sxs-lookup"><span data-stu-id="1cbf8-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1cbf8-143">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="1cbf8-143">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="1cbf8-144">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-144">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1cbf8-145">См. также</span><span class="sxs-lookup"><span data-stu-id="1cbf8-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>  
 <xref:System.ServiceModel.MessageSecurityOverMsmq>  
 [<span data-ttu-id="1cbf8-146">Очереди в WCF</span><span class="sxs-lookup"><span data-stu-id="1cbf8-146">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="1cbf8-147">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="1cbf8-147">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="1cbf8-148">Привязки</span><span class="sxs-lookup"><span data-stu-id="1cbf8-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="1cbf8-149">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="1cbf8-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="1cbf8-150">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="1cbf8-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="1cbf8-151">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="1cbf8-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
