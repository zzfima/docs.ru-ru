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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 00567c32b800bb98386e15b2ba822ccc9623d72b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltservicecredentialsgt"></a><span data-ttu-id="077ad-102">&lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="077ad-102">&lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="077ad-103">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="077ad-103">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
 <span data-ttu-id="077ad-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="077ad-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="077ad-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="077ad-105">\<behaviors></span></span>  
<span data-ttu-id="077ad-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="077ad-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="077ad-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="077ad-107">\<behavior></span></span>  
<span data-ttu-id="077ad-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="077ad-108">\<serviceCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="077ad-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="077ad-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="077ad-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="077ad-110">Attributes and Elements</span></span>  
 <span data-ttu-id="077ad-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="077ad-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="077ad-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="077ad-112">Attributes</span></span>  
  
|<span data-ttu-id="077ad-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="077ad-113">Attribute</span></span>|<span data-ttu-id="077ad-114">Описание</span><span class="sxs-lookup"><span data-stu-id="077ad-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="077ad-115">Строка, задающая тип данного элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="077ad-115">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="077ad-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="077ad-116">Child Elements</span></span>  
  
|<span data-ttu-id="077ad-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="077ad-117">Element</span></span>|<span data-ttu-id="077ad-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="077ad-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="077ad-119">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="077ad-119">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="077ad-120">Задает сертификат для использования, когда сертификат клиента доступен внештатно.</span><span class="sxs-lookup"><span data-stu-id="077ad-120">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="077ad-121">Этот элемент также задает параметры проверки сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="077ad-121">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="077ad-122">Это элемент типа <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="077ad-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="077ad-123">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="077ad-123">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="077ad-124">Задает для этой службы текущий выданный маркер.</span><span class="sxs-lookup"><span data-stu-id="077ad-124">Specifies the current issued token for this service.</span></span> <span data-ttu-id="077ad-125">Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="077ad-125">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="077ad-126">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="077ad-126">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="077ad-127">Задает текущие учетные данные для однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="077ad-127">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="077ad-128">Это элемент типа <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="077ad-128">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="077ad-129">\<secureConversationAuthentication ></span><span class="sxs-lookup"><span data-stu-id="077ad-129">\<secureConversationAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="077ad-130">Задает текущие учетные данные для безопасного сеанса.</span><span class="sxs-lookup"><span data-stu-id="077ad-130">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="077ad-131">Это элемент типа <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="077ad-131">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="077ad-132">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="077ad-132">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="077ad-133">Задает сертификат, используемый службой для своей идентификации.</span><span class="sxs-lookup"><span data-stu-id="077ad-133">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="077ad-134">Это элемент типа <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="077ad-134">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="077ad-135">\<userNameAuthentication ></span><span class="sxs-lookup"><span data-stu-id="077ad-135">\<userNameAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)|<span data-ttu-id="077ad-136">Задает параметры для проверки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="077ad-136">Specifies the settings for username password validation.</span></span> <span data-ttu-id="077ad-137">Это элемент типа <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="077ad-137">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="077ad-138">\<windowsAuthentication ></span><span class="sxs-lookup"><span data-stu-id="077ad-138">\<windowsAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="077ad-139">Задает параметры для проверки учетных данных ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="077ad-139">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="077ad-140">Это элемент типа <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="077ad-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="077ad-141">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="077ad-141">Parent Elements</span></span>  
  
|<span data-ttu-id="077ad-142">Элемент</span><span class="sxs-lookup"><span data-stu-id="077ad-142">Element</span></span>|<span data-ttu-id="077ad-143">Описание:</span><span class="sxs-lookup"><span data-stu-id="077ad-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="077ad-144">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="077ad-144">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="077ad-145">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="077ad-145">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="077ad-146">См. также</span><span class="sxs-lookup"><span data-stu-id="077ad-146">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
 [<span data-ttu-id="077ad-147">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="077ad-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
