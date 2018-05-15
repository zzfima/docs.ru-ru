---
title: '&lt;serviceCertificate&gt; элемента &lt;clientCredentials&gt;'
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 1d54c39fd681e0686e419b7b73243703e9184d1f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltservicecertificategt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="47151-102">&lt;serviceCertificate&gt; элемента &lt;clientCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="47151-102">&lt;serviceCertificate&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="47151-103">Задает сертификат для использования при проверке подлинности службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="47151-103">Specifies a certificate to use when authenticating a service to the client.</span></span>  
  
 <span data-ttu-id="47151-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="47151-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="47151-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="47151-105">\<behaviors></span></span>  
<span data-ttu-id="47151-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="47151-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="47151-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="47151-107">\<behavior></span></span>  
<span data-ttu-id="47151-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="47151-108">\<clientCredentials></span></span>  
<span data-ttu-id="47151-109">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="47151-109">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47151-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47151-110">Syntax</span></span>  
  
```xml  
<serviceCertificate />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47151-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="47151-111">Attributes and Elements</span></span>  
 <span data-ttu-id="47151-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="47151-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47151-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="47151-113">Attributes</span></span>  
 <span data-ttu-id="47151-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="47151-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="47151-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="47151-115">Child Elements</span></span>  
  
|<span data-ttu-id="47151-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="47151-116">Element</span></span>|<span data-ttu-id="47151-117">Описание</span><span class="sxs-lookup"><span data-stu-id="47151-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="47151-118">\<defaultCertificate ></span><span class="sxs-lookup"><span data-stu-id="47151-118">\<defaultCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md)|<span data-ttu-id="47151-119">Задает сертификат X.509 для использования, когда служба или служба маркеров безопасности не предоставляет сертификат посредством протокола согласования.</span><span class="sxs-lookup"><span data-stu-id="47151-119">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>|  
|[<span data-ttu-id="47151-120">\<scopedCertificates ></span><span class="sxs-lookup"><span data-stu-id="47151-120">\<scopedCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md)|<span data-ttu-id="47151-121">Представляет коллекцию сертификатов X.509, предоставленную конкретными службами (в области действия) для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="47151-121">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="47151-122">Эта коллекция обычно используется, чтобы задать сертификаты служб для служб маркеров безопасности в федеративной инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="47151-122">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>|  
|[<span data-ttu-id="47151-123">\<Проверка подлинности ></span><span class="sxs-lookup"><span data-stu-id="47151-123">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)|<span data-ttu-id="47151-124">Задает поведение проверки подлинности для сертификатов служб, используемых клиентом.</span><span class="sxs-lookup"><span data-stu-id="47151-124">Specifies authentication behaviors for service certificates used by a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="47151-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="47151-125">Parent Elements</span></span>  
  
|<span data-ttu-id="47151-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="47151-126">Element</span></span>|<span data-ttu-id="47151-127">Описание</span><span class="sxs-lookup"><span data-stu-id="47151-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="47151-128">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="47151-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="47151-129">Задает учетные данные, используемые клиентом для подтверждения своей подлинности при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="47151-129">Specifies the credentials used by the client to authenticate itself to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47151-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="47151-130">Remarks</span></span>  
 <span data-ttu-id="47151-131">Этот элемент конфигурации содержит параметры, используемые клиентом для проверки сертификата, представленного службой с помощью проверки подлинности SSL.</span><span class="sxs-lookup"><span data-stu-id="47151-131">This configuration element specifies the settings used by the client to validate the certificate presented by the service using SSL authentication.</span></span> <span data-ttu-id="47151-132">Он также содержит сертификат для службы, который явно задан в клиенте для шифрования сообщений для службы с помощью безопасности сообщений.</span><span class="sxs-lookup"><span data-stu-id="47151-132">It also contains any certificate for the service that is explicitly configured on the client to use for encrypting messages to the service using message security.</span></span>  
  
 <span data-ttu-id="47151-133">Атрибуты `serviceCertificate` идентичны элемент с атрибутами [ \<clientCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span><span class="sxs-lookup"><span data-stu-id="47151-133">The attributes of the `serviceCertificate` element are identical to the attributes of the [\<clientCertificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47151-134">См. также</span><span class="sxs-lookup"><span data-stu-id="47151-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 [<span data-ttu-id="47151-135">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="47151-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="47151-136">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="47151-136">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="47151-137">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="47151-137">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="47151-138">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="47151-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
