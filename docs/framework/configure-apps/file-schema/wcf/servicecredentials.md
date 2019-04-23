---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: d9f8fdf272962916cd08aede484e9bbde55b96a3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227084"
---
# <a name="servicecredentials"></a><span data-ttu-id="6bed2-101">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="6bed2-101">\<serviceCredentials></span></span>
<span data-ttu-id="6bed2-102">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="6bed2-102">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
 <span data-ttu-id="6bed2-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6bed2-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="6bed2-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="6bed2-104">\<behaviors></span></span>  
<span data-ttu-id="6bed2-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="6bed2-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="6bed2-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="6bed2-106">\<behavior></span></span>  
<span data-ttu-id="6bed2-107">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="6bed2-107">\<serviceCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bed2-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6bed2-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6bed2-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6bed2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6bed2-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6bed2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6bed2-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6bed2-111">Attributes</span></span>  
  
|<span data-ttu-id="6bed2-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6bed2-112">Attribute</span></span>|<span data-ttu-id="6bed2-113">Описание</span><span class="sxs-lookup"><span data-stu-id="6bed2-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="6bed2-114">Строка, задающая тип данного элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6bed2-114">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6bed2-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6bed2-115">Child Elements</span></span>  
  
|<span data-ttu-id="6bed2-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="6bed2-116">Element</span></span>|<span data-ttu-id="6bed2-117">Описание</span><span class="sxs-lookup"><span data-stu-id="6bed2-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6bed2-118">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="6bed2-118">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="6bed2-119">Задает сертификат для использования, когда сертификат клиента доступен внештатно.</span><span class="sxs-lookup"><span data-stu-id="6bed2-119">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="6bed2-120">Этот элемент также задает параметры проверки сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="6bed2-120">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="6bed2-121">Это элемент типа <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="6bed2-121">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="6bed2-122">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="6bed2-122">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="6bed2-123">Задает для этой службы текущий выданный маркер.</span><span class="sxs-lookup"><span data-stu-id="6bed2-123">Specifies the current issued token for this service.</span></span> <span data-ttu-id="6bed2-124">Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="6bed2-124">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="6bed2-125">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="6bed2-125">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="6bed2-126">Задает текущие учетные данные для однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="6bed2-126">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="6bed2-127">Это элемент типа <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="6bed2-127">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="6bed2-128">\<secureConversationAuthentication></span><span class="sxs-lookup"><span data-stu-id="6bed2-128">\<secureConversationAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="6bed2-129">Задает текущие учетные данные для безопасного сеанса.</span><span class="sxs-lookup"><span data-stu-id="6bed2-129">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="6bed2-130">Это элемент типа <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="6bed2-130">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="6bed2-131">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="6bed2-131">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="6bed2-132">Задает сертификат, используемый службой для своей идентификации.</span><span class="sxs-lookup"><span data-stu-id="6bed2-132">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="6bed2-133">Это элемент типа <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="6bed2-133">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="6bed2-134">\<userNameAuthentication ></span><span class="sxs-lookup"><span data-stu-id="6bed2-134">\<userNameAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)|<span data-ttu-id="6bed2-135">Задает параметры для проверки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="6bed2-135">Specifies the settings for username password validation.</span></span> <span data-ttu-id="6bed2-136">Это элемент типа <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="6bed2-136">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="6bed2-137">\<windowsAuthentication ></span><span class="sxs-lookup"><span data-stu-id="6bed2-137">\<windowsAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="6bed2-138">Задает параметры для проверки учетных данных ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="6bed2-138">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="6bed2-139">Это элемент типа <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="6bed2-139">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6bed2-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6bed2-140">Parent Elements</span></span>  
  
|<span data-ttu-id="6bed2-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="6bed2-141">Element</span></span>|<span data-ttu-id="6bed2-142">Описание</span><span class="sxs-lookup"><span data-stu-id="6bed2-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6bed2-143">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="6bed2-143">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="6bed2-144">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="6bed2-144">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6bed2-145">См. также</span><span class="sxs-lookup"><span data-stu-id="6bed2-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="6bed2-146">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="6bed2-146">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
