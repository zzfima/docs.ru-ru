---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: b5d257b3082717ba94b9a4517ed5ccd4bd325c06
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936298"
---
# <a name="servicecredentials"></a><span data-ttu-id="18825-101">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="18825-101">\<serviceCredentials></span></span>
<span data-ttu-id="18825-102">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="18825-102">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
 <span data-ttu-id="18825-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="18825-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="18825-104">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="18825-104">\<behaviors></span></span>  
<span data-ttu-id="18825-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="18825-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="18825-106">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="18825-106">\<behavior></span></span>  
<span data-ttu-id="18825-107">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="18825-107">\<serviceCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18825-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18825-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18825-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="18825-109">Attributes and Elements</span></span>  
 <span data-ttu-id="18825-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="18825-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18825-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="18825-111">Attributes</span></span>  
  
|<span data-ttu-id="18825-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="18825-112">Attribute</span></span>|<span data-ttu-id="18825-113">Описание</span><span class="sxs-lookup"><span data-stu-id="18825-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="18825-114">Строка, задающая тип данного элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="18825-114">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18825-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="18825-115">Child Elements</span></span>  
  
|<span data-ttu-id="18825-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="18825-116">Element</span></span>|<span data-ttu-id="18825-117">Описание</span><span class="sxs-lookup"><span data-stu-id="18825-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18825-118">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="18825-118">\<clientCertificate></span></span>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="18825-119">Задает сертификат для использования, когда сертификат клиента доступен внештатно.</span><span class="sxs-lookup"><span data-stu-id="18825-119">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="18825-120">Этот элемент также задает параметры проверки сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="18825-120">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="18825-121">Это элемент типа <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="18825-121">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="18825-122">\<Иссуедтокенаусентикатион ></span><span class="sxs-lookup"><span data-stu-id="18825-122">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="18825-123">Задает для этой службы текущий выданный маркер.</span><span class="sxs-lookup"><span data-stu-id="18825-123">Specifies the current issued token for this service.</span></span> <span data-ttu-id="18825-124">Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="18825-124">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="18825-125">\<Одноранговые ></span><span class="sxs-lookup"><span data-stu-id="18825-125">\<peer></span></span>](peer-of-servicecredentials.md)|<span data-ttu-id="18825-126">Задает текущие учетные данные для однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="18825-126">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="18825-127">Это элемент типа <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="18825-127">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="18825-128">\<Секуреконверсатионаусентикатион ></span><span class="sxs-lookup"><span data-stu-id="18825-128">\<secureConversationAuthentication></span></span>](secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="18825-129">Задает текущие учетные данные для безопасного сеанса.</span><span class="sxs-lookup"><span data-stu-id="18825-129">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="18825-130">Это элемент типа <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="18825-130">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="18825-131">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="18825-131">\<serviceCertificate></span></span>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="18825-132">Задает сертификат, используемый службой для своей идентификации.</span><span class="sxs-lookup"><span data-stu-id="18825-132">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="18825-133">Это элемент типа <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="18825-133">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="18825-134">\<Усернамеаусентикатион ></span><span class="sxs-lookup"><span data-stu-id="18825-134">\<userNameAuthentication></span></span>](usernameauthentication.md)|<span data-ttu-id="18825-135">Задает параметры для проверки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="18825-135">Specifies the settings for username password validation.</span></span> <span data-ttu-id="18825-136">Это элемент типа <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="18825-136">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="18825-137">\<windowsAuthentication ></span><span class="sxs-lookup"><span data-stu-id="18825-137">\<windowsAuthentication></span></span>](windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="18825-138">Задает параметры для проверки учетных данных ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="18825-138">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="18825-139">Это элемент типа <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="18825-139">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="18825-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="18825-140">Parent Elements</span></span>  
  
|<span data-ttu-id="18825-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="18825-141">Element</span></span>|<span data-ttu-id="18825-142">Описание</span><span class="sxs-lookup"><span data-stu-id="18825-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18825-143">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="18825-143">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="18825-144">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="18825-144">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="18825-145">См. также</span><span class="sxs-lookup"><span data-stu-id="18825-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="18825-146">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="18825-146">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
