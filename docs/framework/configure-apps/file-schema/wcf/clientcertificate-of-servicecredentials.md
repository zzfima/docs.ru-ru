---
title: <clientCertificate> из <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
ms.openlocfilehash: a8a78bbfcd9dfbf6975503a845d5bb4e2d24b13d
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398140"
---
# <a name="clientcertificate-of-servicecredentials"></a><span data-ttu-id="70cc3-102">\<clientCertificate > \<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="70cc3-102">\<clientCertificate> of \<serviceCredentials></span></span>
<span data-ttu-id="70cc3-103">Задает файл сертификата X.509, используемый для подписания и шифрования сообщений к клиенту от службы при дуплексном обмене данными.</span><span class="sxs-lookup"><span data-stu-id="70cc3-103">Defines an X.509 certificate used to sign and encrypt messages to a client form a service in a duplex communication pattern.</span></span>  
  
<span data-ttu-id="70cc3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="70cc3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="70cc3-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="70cc3-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="70cc3-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="70cc3-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="70cc3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="70cc3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="70cc3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="70cc3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="70cc3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="70cc3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="70cc3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<clientCertificate >**</span><span class="sxs-lookup"><span data-stu-id="70cc3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCertificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70cc3-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="70cc3-111">Syntax</span></span>  
  
```xml  
<clientCertificate>
  <certificate />
  <authentication />
</clientCertificate>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70cc3-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="70cc3-112">Attributes and Elements</span></span>  
 <span data-ttu-id="70cc3-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="70cc3-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70cc3-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="70cc3-114">Attributes</span></span>  
 <span data-ttu-id="70cc3-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="70cc3-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="70cc3-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="70cc3-116">Child Elements</span></span>  
  
|<span data-ttu-id="70cc3-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="70cc3-117">Element</span></span>|<span data-ttu-id="70cc3-118">Описание</span><span class="sxs-lookup"><span data-stu-id="70cc3-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="70cc3-119">\<authentication></span><span class="sxs-lookup"><span data-stu-id="70cc3-119">\<authentication></span></span>](authentication-of-clientcertificate-element.md)|<span data-ttu-id="70cc3-120">Задает параметры проверки подлинности для сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="70cc3-120">Specifies authentication options for the client certificate.</span></span>|  
|[<span data-ttu-id="70cc3-121">\<> сертификата</span><span class="sxs-lookup"><span data-stu-id="70cc3-121">\<certificate></span></span>](certificate-of-clientcertificate-element.md)|<span data-ttu-id="70cc3-122">Задает тип сертификата для использования.</span><span class="sxs-lookup"><span data-stu-id="70cc3-122">Specifies the certificate to use.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="70cc3-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="70cc3-123">Parent Elements</span></span>  
  
|<span data-ttu-id="70cc3-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="70cc3-124">Element</span></span>|<span data-ttu-id="70cc3-125">Описание</span><span class="sxs-lookup"><span data-stu-id="70cc3-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="70cc3-126">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="70cc3-126">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="70cc3-127">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="70cc3-127">Specifies the credentials to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70cc3-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="70cc3-128">Remarks</span></span>  
 <span data-ttu-id="70cc3-129">Этот элемент используется в случаях, когда служба должна получить клиентский сертификат заранее для безопасного обмена данными с клиентом.</span><span class="sxs-lookup"><span data-stu-id="70cc3-129">This element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="70cc3-130">Это характерно для дуплексного обмена данными.</span><span class="sxs-lookup"><span data-stu-id="70cc3-130">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="70cc3-131">В более распространенном варианте «запрос/отклик» клиент включает сертификат в запрос, который используется службой для шифрования и подписания отклика.</span><span class="sxs-lookup"><span data-stu-id="70cc3-131">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="70cc3-132">Тем не менее при дуплексном обмене данными служба не получает запроса от клиента, и ей, таким образом, необходим сертификат клиента заранее, чтобы обеспечить защиту сообщения, отправляемого клиенту.</span><span class="sxs-lookup"><span data-stu-id="70cc3-132">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="70cc3-133">Следовательно, необходимо получить сертификат клиента при согласовании вне диапазона и указать сертификат с помощью этого элемента.</span><span class="sxs-lookup"><span data-stu-id="70cc3-133">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="70cc3-134">Дополнительные сведения о дуплексных службах см [. в разделе как Создание дуплексного контракта](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="70cc3-134">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
 <span data-ttu-id="70cc3-135">Заданный в этом элементе сертификат используется для шифрования сообщений к клиенту только для привязок, которые настроены с использованием режима проверки подлинности `MutualCertificateDuplex`.</span><span class="sxs-lookup"><span data-stu-id="70cc3-135">The certificate set in this element is used to encrypt messages to the client only for bindings that are configured with `MutualCertificateDuplex` message security authentication mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70cc3-136">См. также</span><span class="sxs-lookup"><span data-stu-id="70cc3-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>
- [<span data-ttu-id="70cc3-137">Практическое руководство. Создание дуплексного контракта</span><span class="sxs-lookup"><span data-stu-id="70cc3-137">How to: Create a Duplex Contract</span></span>](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="70cc3-138">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="70cc3-138">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="70cc3-139">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="70cc3-139">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
