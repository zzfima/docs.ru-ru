---
title: <serviceCertificate> элемента <clientCredentials>
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: a3013d0f7efd3014892cf6400447d708809c5fcd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936341"
---
# <a name="servicecertificate-of-clientcredentials-element"></a><span data-ttu-id="4b0e0-102">\<serviceCertificate > \<>ного элемента ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="4b0e0-102">\<serviceCertificate> of \<clientCredentials> Element</span></span>
<span data-ttu-id="4b0e0-103">Задает сертификат для использования при проверке подлинности службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="4b0e0-103">Specifies a certificate to use when authenticating a service to the client.</span></span>  
  
 <span data-ttu-id="4b0e0-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4b0e0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4b0e0-105">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="4b0e0-105">\<behaviors></span></span>  
<span data-ttu-id="4b0e0-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="4b0e0-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="4b0e0-107">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="4b0e0-107">\<behavior></span></span>  
<span data-ttu-id="4b0e0-108">\<> clientCredentials</span><span class="sxs-lookup"><span data-stu-id="4b0e0-108">\<clientCredentials></span></span>  
<span data-ttu-id="4b0e0-109">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="4b0e0-109">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b0e0-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b0e0-110">Syntax</span></span>  
  
```xml  
<serviceCertificate />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b0e0-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4b0e0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4b0e0-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4b0e0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b0e0-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4b0e0-113">Attributes</span></span>  
 <span data-ttu-id="4b0e0-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="4b0e0-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4b0e0-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4b0e0-115">Child Elements</span></span>  
  
|<span data-ttu-id="4b0e0-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="4b0e0-116">Element</span></span>|<span data-ttu-id="4b0e0-117">Описание</span><span class="sxs-lookup"><span data-stu-id="4b0e0-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b0e0-118">\<Дефаултцертификате ></span><span class="sxs-lookup"><span data-stu-id="4b0e0-118">\<defaultCertificate></span></span>](defaultcertificate-element.md)|<span data-ttu-id="4b0e0-119">Задает сертификат X.509 для использования, когда служба или служба маркеров безопасности не предоставляет сертификат посредством протокола согласования.</span><span class="sxs-lookup"><span data-stu-id="4b0e0-119">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>|  
|[<span data-ttu-id="4b0e0-120">\<Скопедцертификатес ></span><span class="sxs-lookup"><span data-stu-id="4b0e0-120">\<scopedCertificates></span></span>](scopedcertificates-element.md)|<span data-ttu-id="4b0e0-121">Представляет коллекцию сертификатов X.509, предоставленную конкретными службами (в области действия) для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="4b0e0-121">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="4b0e0-122">Эта коллекция обычно используется, чтобы задать сертификаты служб для служб маркеров безопасности в федеративной инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="4b0e0-122">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>|  
|[<span data-ttu-id="4b0e0-123">\<authentication></span><span class="sxs-lookup"><span data-stu-id="4b0e0-123">\<authentication></span></span>](authentication-of-servicecertificate-element.md)|<span data-ttu-id="4b0e0-124">Задает поведение проверки подлинности для сертификатов служб, используемых клиентом.</span><span class="sxs-lookup"><span data-stu-id="4b0e0-124">Specifies authentication behaviors for service certificates used by a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4b0e0-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4b0e0-125">Parent Elements</span></span>  
  
|<span data-ttu-id="4b0e0-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="4b0e0-126">Element</span></span>|<span data-ttu-id="4b0e0-127">Описание</span><span class="sxs-lookup"><span data-stu-id="4b0e0-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b0e0-128">\<> clientCredentials</span><span class="sxs-lookup"><span data-stu-id="4b0e0-128">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="4b0e0-129">Задает учетные данные, используемые клиентом для подтверждения своей подлинности при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="4b0e0-129">Specifies the credentials used by the client to authenticate itself to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b0e0-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="4b0e0-130">Remarks</span></span>  
 <span data-ttu-id="4b0e0-131">Этот элемент конфигурации содержит параметры, используемые клиентом для проверки сертификата, представленного службой с помощью проверки подлинности SSL.</span><span class="sxs-lookup"><span data-stu-id="4b0e0-131">This configuration element specifies the settings used by the client to validate the certificate presented by the service using SSL authentication.</span></span> <span data-ttu-id="4b0e0-132">Он также содержит сертификат для службы, который явно задан в клиенте для шифрования сообщений для службы с помощью безопасности сообщений.</span><span class="sxs-lookup"><span data-stu-id="4b0e0-132">It also contains any certificate for the service that is explicitly configured on the client to use for encrypting messages to the service using message security.</span></span>  
  
 <span data-ttu-id="4b0e0-133">Атрибуты `serviceCertificate` элемента идентичны атрибутам [ \<> clientcertificate](clientcertificate-of-clientcredentials-element.md).</span><span class="sxs-lookup"><span data-stu-id="4b0e0-133">The attributes of the `serviceCertificate` element are identical to the attributes of the [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b0e0-134">См. также</span><span class="sxs-lookup"><span data-stu-id="4b0e0-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- [<span data-ttu-id="4b0e0-135">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="4b0e0-135">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="4b0e0-136">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="4b0e0-136">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="4b0e0-137">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="4b0e0-137">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="4b0e0-138">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="4b0e0-138">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
