---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: d9f8fdf272962916cd08aede484e9bbde55b96a3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227084"
---
# <a name="servicecredentials"></a><span data-ttu-id="e3c28-101">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="e3c28-101">\<serviceCredentials></span></span>
<span data-ttu-id="e3c28-102">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="e3c28-102">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
 <span data-ttu-id="e3c28-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e3c28-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="e3c28-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="e3c28-104">\<behaviors></span></span>  
<span data-ttu-id="e3c28-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e3c28-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="e3c28-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="e3c28-106">\<behavior></span></span>  
<span data-ttu-id="e3c28-107">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="e3c28-107">\<serviceCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3c28-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3c28-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3c28-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e3c28-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e3c28-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e3c28-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3c28-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e3c28-111">Attributes</span></span>  
  
|<span data-ttu-id="e3c28-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e3c28-112">Attribute</span></span>|<span data-ttu-id="e3c28-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e3c28-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="e3c28-114">Строка, задающая тип данного элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e3c28-114">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e3c28-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e3c28-115">Child Elements</span></span>  
  
|<span data-ttu-id="e3c28-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="e3c28-116">Element</span></span>|<span data-ttu-id="e3c28-117">Описание</span><span class="sxs-lookup"><span data-stu-id="e3c28-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3c28-118">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="e3c28-118">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="e3c28-119">Задает сертификат для использования, когда сертификат клиента доступен внештатно.</span><span class="sxs-lookup"><span data-stu-id="e3c28-119">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="e3c28-120">Этот элемент также задает параметры проверки сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="e3c28-120">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="e3c28-121">Это элемент типа <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="e3c28-121">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="e3c28-122">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="e3c28-122">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="e3c28-123">Задает для этой службы текущий выданный маркер.</span><span class="sxs-lookup"><span data-stu-id="e3c28-123">Specifies the current issued token for this service.</span></span> <span data-ttu-id="e3c28-124">Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="e3c28-124">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="e3c28-125">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="e3c28-125">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="e3c28-126">Задает текущие учетные данные для однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="e3c28-126">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="e3c28-127">Это элемент типа <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="e3c28-127">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="e3c28-128">\<secureConversationAuthentication></span><span class="sxs-lookup"><span data-stu-id="e3c28-128">\<secureConversationAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="e3c28-129">Задает текущие учетные данные для безопасного сеанса.</span><span class="sxs-lookup"><span data-stu-id="e3c28-129">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="e3c28-130">Это элемент типа <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="e3c28-130">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="e3c28-131">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="e3c28-131">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="e3c28-132">Задает сертификат, используемый службой для своей идентификации.</span><span class="sxs-lookup"><span data-stu-id="e3c28-132">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="e3c28-133">Это элемент типа <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="e3c28-133">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="e3c28-134">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="e3c28-134">\<userNameAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)|<span data-ttu-id="e3c28-135">Задает параметры для проверки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="e3c28-135">Specifies the settings for username password validation.</span></span> <span data-ttu-id="e3c28-136">Это элемент типа <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="e3c28-136">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="e3c28-137">\<windowsAuthentication ></span><span class="sxs-lookup"><span data-stu-id="e3c28-137">\<windowsAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="e3c28-138">Задает параметры для проверки учетных данных ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="e3c28-138">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="e3c28-139">Это элемент типа <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="e3c28-139">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e3c28-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e3c28-140">Parent Elements</span></span>  
  
|<span data-ttu-id="e3c28-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="e3c28-141">Element</span></span>|<span data-ttu-id="e3c28-142">Описание</span><span class="sxs-lookup"><span data-stu-id="e3c28-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3c28-143">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="e3c28-143">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="e3c28-144">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="e3c28-144">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e3c28-145">См. также</span><span class="sxs-lookup"><span data-stu-id="e3c28-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="e3c28-146">Поведение безопасности</span><span class="sxs-lookup"><span data-stu-id="e3c28-146">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
