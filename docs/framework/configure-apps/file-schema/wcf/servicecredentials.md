---
title: '&lt;serviceCredentials&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bef277ebd2bd80d51380ae9786b290e7d05a0f0d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltservicecredentialsgt"></a><span data-ttu-id="280c9-102">&lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="280c9-102">&lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="280c9-103">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="280c9-103">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
 <span data-ttu-id="280c9-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="280c9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="280c9-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="280c9-105">\<behaviors></span></span>  
<span data-ttu-id="280c9-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="280c9-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="280c9-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="280c9-107">\<behavior></span></span>  
<span data-ttu-id="280c9-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="280c9-108">\<serviceCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="280c9-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="280c9-109">Syntax</span></span>  
  
```xml  
<serviceCredentials type="String">  
   <clientCertificate>  
   </clientCertificate>  
   <issuedTokenAuthentication>  
   </issuedTokenAuthentication>  
   <peer>  
   </peer>  
   <secureConversationAuthentication>  
   </secureConversationAuthentication>  
   <serviceCertificate>  
   </serviceCertificate>  
   <userNameAuthentication>  
   </userNameAuthentication>  
   <windowsAuthentication>  
   </windowsAuthentication>  
</serviceCredentials>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="280c9-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="280c9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="280c9-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="280c9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="280c9-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="280c9-112">Attributes</span></span>  
  
|<span data-ttu-id="280c9-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="280c9-113">Attribute</span></span>|<span data-ttu-id="280c9-114">Описание</span><span class="sxs-lookup"><span data-stu-id="280c9-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="280c9-115">Строка, задающая тип данного элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="280c9-115">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="280c9-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="280c9-116">Child Elements</span></span>  
  
|<span data-ttu-id="280c9-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="280c9-117">Element</span></span>|<span data-ttu-id="280c9-118">Описание</span><span class="sxs-lookup"><span data-stu-id="280c9-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="280c9-119">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="280c9-119">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="280c9-120">Задает сертификат для использования, когда сертификат клиента доступен внештатно.</span><span class="sxs-lookup"><span data-stu-id="280c9-120">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="280c9-121">Этот элемент также задает параметры проверки сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="280c9-121">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="280c9-122">Это элемент типа <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="280c9-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="280c9-123">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="280c9-123">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="280c9-124">Задает для этой службы текущий выданный маркер.</span><span class="sxs-lookup"><span data-stu-id="280c9-124">Specifies the current issued token for this service.</span></span> <span data-ttu-id="280c9-125">Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="280c9-125">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="280c9-126">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="280c9-126">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="280c9-127">Задает текущие учетные данные для однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="280c9-127">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="280c9-128">Это элемент типа <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="280c9-128">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="280c9-129">\<secureConversationAuthentication ></span><span class="sxs-lookup"><span data-stu-id="280c9-129">\<secureConversationAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="280c9-130">Задает текущие учетные данные для безопасного сеанса.</span><span class="sxs-lookup"><span data-stu-id="280c9-130">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="280c9-131">Это элемент типа <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="280c9-131">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="280c9-132">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="280c9-132">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="280c9-133">Задает сертификат, используемый службой для своей идентификации.</span><span class="sxs-lookup"><span data-stu-id="280c9-133">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="280c9-134">Это элемент типа <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="280c9-134">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="280c9-135">\<userNameAuthentication ></span><span class="sxs-lookup"><span data-stu-id="280c9-135">\<userNameAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)|<span data-ttu-id="280c9-136">Задает параметры для проверки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="280c9-136">Specifies the settings for username password validation.</span></span> <span data-ttu-id="280c9-137">Это элемент типа <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="280c9-137">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="280c9-138">\<windowsAuthentication ></span><span class="sxs-lookup"><span data-stu-id="280c9-138">\<windowsAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="280c9-139">Задает параметры для проверки учетных данных ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="280c9-139">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="280c9-140">Это элемент типа <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="280c9-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="280c9-141">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="280c9-141">Parent Elements</span></span>  
  
|<span data-ttu-id="280c9-142">Элемент</span><span class="sxs-lookup"><span data-stu-id="280c9-142">Element</span></span>|<span data-ttu-id="280c9-143">Описание</span><span class="sxs-lookup"><span data-stu-id="280c9-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="280c9-144">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="280c9-144">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="280c9-145">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="280c9-145">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="280c9-146">См. также</span><span class="sxs-lookup"><span data-stu-id="280c9-146">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
 [<span data-ttu-id="280c9-147">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="280c9-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
