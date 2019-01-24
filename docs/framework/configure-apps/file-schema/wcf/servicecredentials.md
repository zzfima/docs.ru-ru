---
title: '&lt;ServiceCredentials&gt;'
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: 978439dfeb0c5275e2ec43f9c891b6927e7a7869
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610439"
---
# <a name="ltservicecredentialsgt"></a><span data-ttu-id="27c4d-102">&lt;ServiceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="27c4d-102">&lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="27c4d-103">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="27c4d-103">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
 <span data-ttu-id="27c4d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="27c4d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="27c4d-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="27c4d-105">\<behaviors></span></span>  
<span data-ttu-id="27c4d-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="27c4d-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="27c4d-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="27c4d-107">\<behavior></span></span>  
<span data-ttu-id="27c4d-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="27c4d-108">\<serviceCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27c4d-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27c4d-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27c4d-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="27c4d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="27c4d-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="27c4d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27c4d-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="27c4d-112">Attributes</span></span>  
  
|<span data-ttu-id="27c4d-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="27c4d-113">Attribute</span></span>|<span data-ttu-id="27c4d-114">Описание</span><span class="sxs-lookup"><span data-stu-id="27c4d-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="27c4d-115">Строка, задающая тип данного элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="27c4d-115">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="27c4d-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="27c4d-116">Child Elements</span></span>  
  
|<span data-ttu-id="27c4d-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="27c4d-117">Element</span></span>|<span data-ttu-id="27c4d-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="27c4d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27c4d-119">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="27c4d-119">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="27c4d-120">Задает сертификат для использования, когда сертификат клиента доступен внештатно.</span><span class="sxs-lookup"><span data-stu-id="27c4d-120">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="27c4d-121">Этот элемент также задает параметры проверки сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="27c4d-121">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="27c4d-122">Это элемент типа <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="27c4d-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="27c4d-123">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="27c4d-123">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="27c4d-124">Задает для этой службы текущий выданный маркер.</span><span class="sxs-lookup"><span data-stu-id="27c4d-124">Specifies the current issued token for this service.</span></span> <span data-ttu-id="27c4d-125">Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="27c4d-125">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="27c4d-126">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="27c4d-126">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="27c4d-127">Задает текущие учетные данные для однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="27c4d-127">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="27c4d-128">Это элемент типа <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="27c4d-128">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="27c4d-129">\<secureConversationAuthentication></span><span class="sxs-lookup"><span data-stu-id="27c4d-129">\<secureConversationAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="27c4d-130">Задает текущие учетные данные для безопасного сеанса.</span><span class="sxs-lookup"><span data-stu-id="27c4d-130">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="27c4d-131">Это элемент типа <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="27c4d-131">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="27c4d-132">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="27c4d-132">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="27c4d-133">Задает сертификат, используемый службой для своей идентификации.</span><span class="sxs-lookup"><span data-stu-id="27c4d-133">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="27c4d-134">Это элемент типа <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="27c4d-134">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="27c4d-135">\<userNameAuthentication ></span><span class="sxs-lookup"><span data-stu-id="27c4d-135">\<userNameAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)|<span data-ttu-id="27c4d-136">Задает параметры для проверки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="27c4d-136">Specifies the settings for username password validation.</span></span> <span data-ttu-id="27c4d-137">Это элемент типа <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="27c4d-137">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="27c4d-138">\<windowsAuthentication ></span><span class="sxs-lookup"><span data-stu-id="27c4d-138">\<windowsAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="27c4d-139">Задает параметры для проверки учетных данных ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="27c4d-139">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="27c4d-140">Это элемент типа <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="27c4d-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="27c4d-141">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="27c4d-141">Parent Elements</span></span>  
  
|<span data-ttu-id="27c4d-142">Элемент</span><span class="sxs-lookup"><span data-stu-id="27c4d-142">Element</span></span>|<span data-ttu-id="27c4d-143">Описание:</span><span class="sxs-lookup"><span data-stu-id="27c4d-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27c4d-144">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="27c4d-144">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="27c4d-145">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="27c4d-145">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="27c4d-146">См. также</span><span class="sxs-lookup"><span data-stu-id="27c4d-146">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="27c4d-147">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="27c4d-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
