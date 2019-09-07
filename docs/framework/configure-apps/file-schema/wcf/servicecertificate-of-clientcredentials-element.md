---
title: <serviceCertificate> элемента <clientCredentials>
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 4c7489a171bdd5cb4b747ca99f1b7ff6dd65517b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399684"
---
# <a name="servicecertificate-of-clientcredentials-element"></a><span data-ttu-id="aaf85-102">\<serviceCertificate > \<>ного элемента ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="aaf85-102">\<serviceCertificate> of \<clientCredentials> Element</span></span>
<span data-ttu-id="aaf85-103">Задает сертификат для использования при проверке подлинности службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="aaf85-103">Specifies a certificate to use when authenticating a service to the client.</span></span>  
  
<span data-ttu-id="aaf85-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="aaf85-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="aaf85-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="aaf85-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="aaf85-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="aaf85-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="aaf85-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="aaf85-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="aaf85-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="aaf85-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="aaf85-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="aaf85-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="aaf85-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceCertificate >**</span><span class="sxs-lookup"><span data-stu-id="aaf85-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaf85-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aaf85-111">Syntax</span></span>  
  
```xml  
<serviceCertificate />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aaf85-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="aaf85-112">Attributes and Elements</span></span>  
 <span data-ttu-id="aaf85-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="aaf85-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aaf85-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aaf85-114">Attributes</span></span>  
 <span data-ttu-id="aaf85-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="aaf85-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="aaf85-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aaf85-116">Child Elements</span></span>  
  
|<span data-ttu-id="aaf85-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="aaf85-117">Element</span></span>|<span data-ttu-id="aaf85-118">Описание</span><span class="sxs-lookup"><span data-stu-id="aaf85-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aaf85-119">\<Дефаултцертификате ></span><span class="sxs-lookup"><span data-stu-id="aaf85-119">\<defaultCertificate></span></span>](defaultcertificate-element.md)|<span data-ttu-id="aaf85-120">Задает сертификат X.509 для использования, когда служба или служба маркеров безопасности не предоставляет сертификат посредством протокола согласования.</span><span class="sxs-lookup"><span data-stu-id="aaf85-120">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>|  
|[<span data-ttu-id="aaf85-121">\<Скопедцертификатес ></span><span class="sxs-lookup"><span data-stu-id="aaf85-121">\<scopedCertificates></span></span>](scopedcertificates-element.md)|<span data-ttu-id="aaf85-122">Представляет коллекцию сертификатов X.509, предоставленную конкретными службами (в области действия) для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="aaf85-122">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="aaf85-123">Эта коллекция обычно используется, чтобы задать сертификаты служб для служб маркеров безопасности в федеративной инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="aaf85-123">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>|  
|[<span data-ttu-id="aaf85-124">\<authentication></span><span class="sxs-lookup"><span data-stu-id="aaf85-124">\<authentication></span></span>](authentication-of-servicecertificate-element.md)|<span data-ttu-id="aaf85-125">Задает поведение проверки подлинности для сертификатов служб, используемых клиентом.</span><span class="sxs-lookup"><span data-stu-id="aaf85-125">Specifies authentication behaviors for service certificates used by a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aaf85-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="aaf85-126">Parent Elements</span></span>  
  
|<span data-ttu-id="aaf85-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="aaf85-127">Element</span></span>|<span data-ttu-id="aaf85-128">Описание</span><span class="sxs-lookup"><span data-stu-id="aaf85-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aaf85-129">\<> clientCredentials</span><span class="sxs-lookup"><span data-stu-id="aaf85-129">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="aaf85-130">Задает учетные данные, используемые клиентом для подтверждения своей подлинности при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="aaf85-130">Specifies the credentials used by the client to authenticate itself to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aaf85-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="aaf85-131">Remarks</span></span>  
 <span data-ttu-id="aaf85-132">Этот элемент конфигурации содержит параметры, используемые клиентом для проверки сертификата, представленного службой с помощью проверки подлинности SSL.</span><span class="sxs-lookup"><span data-stu-id="aaf85-132">This configuration element specifies the settings used by the client to validate the certificate presented by the service using SSL authentication.</span></span> <span data-ttu-id="aaf85-133">Он также содержит сертификат для службы, который явно задан в клиенте для шифрования сообщений для службы с помощью безопасности сообщений.</span><span class="sxs-lookup"><span data-stu-id="aaf85-133">It also contains any certificate for the service that is explicitly configured on the client to use for encrypting messages to the service using message security.</span></span>  
  
 <span data-ttu-id="aaf85-134">Атрибуты `serviceCertificate` элемента идентичны атрибутам [ \<> clientcertificate](clientcertificate-of-clientcredentials-element.md).</span><span class="sxs-lookup"><span data-stu-id="aaf85-134">The attributes of the `serviceCertificate` element are identical to the attributes of the [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaf85-135">См. также</span><span class="sxs-lookup"><span data-stu-id="aaf85-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- [<span data-ttu-id="aaf85-136">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="aaf85-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="aaf85-137">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="aaf85-137">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="aaf85-138">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="aaf85-138">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="aaf85-139">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="aaf85-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
