---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: 90a34a4a52b4c7a2e67d733fecba132818cac4fc
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399661"
---
# <a name="servicecredentials"></a><span data-ttu-id="3af53-101">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="3af53-101">\<serviceCredentials></span></span>
<span data-ttu-id="3af53-102">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="3af53-102">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
<span data-ttu-id="3af53-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3af53-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3af53-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3af53-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3af53-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3af53-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="3af53-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3af53-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="3af53-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3af53-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="3af53-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceCredentials >**</span><span class="sxs-lookup"><span data-stu-id="3af53-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCredentials>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3af53-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3af53-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3af53-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3af53-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3af53-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3af53-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3af53-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3af53-112">Attributes</span></span>  
  
|<span data-ttu-id="3af53-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3af53-113">Attribute</span></span>|<span data-ttu-id="3af53-114">Описание</span><span class="sxs-lookup"><span data-stu-id="3af53-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="3af53-115">Строка, задающая тип данного элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3af53-115">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3af53-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3af53-116">Child Elements</span></span>  
  
|<span data-ttu-id="3af53-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="3af53-117">Element</span></span>|<span data-ttu-id="3af53-118">Описание</span><span class="sxs-lookup"><span data-stu-id="3af53-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3af53-119">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="3af53-119">\<clientCertificate></span></span>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="3af53-120">Задает сертификат для использования, когда сертификат клиента доступен внештатно.</span><span class="sxs-lookup"><span data-stu-id="3af53-120">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="3af53-121">Этот элемент также задает параметры проверки сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="3af53-121">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="3af53-122">Это элемент типа <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="3af53-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="3af53-123">\<Иссуедтокенаусентикатион ></span><span class="sxs-lookup"><span data-stu-id="3af53-123">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="3af53-124">Задает для этой службы текущий выданный маркер.</span><span class="sxs-lookup"><span data-stu-id="3af53-124">Specifies the current issued token for this service.</span></span> <span data-ttu-id="3af53-125">Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="3af53-125">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="3af53-126">\<Одноранговые ></span><span class="sxs-lookup"><span data-stu-id="3af53-126">\<peer></span></span>](peer-of-servicecredentials.md)|<span data-ttu-id="3af53-127">Задает текущие учетные данные для однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="3af53-127">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="3af53-128">Это элемент типа <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="3af53-128">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="3af53-129">\<Секуреконверсатионаусентикатион ></span><span class="sxs-lookup"><span data-stu-id="3af53-129">\<secureConversationAuthentication></span></span>](secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="3af53-130">Задает текущие учетные данные для безопасного сеанса.</span><span class="sxs-lookup"><span data-stu-id="3af53-130">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="3af53-131">Это элемент типа <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="3af53-131">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="3af53-132">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="3af53-132">\<serviceCertificate></span></span>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="3af53-133">Задает сертификат, используемый службой для своей идентификации.</span><span class="sxs-lookup"><span data-stu-id="3af53-133">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="3af53-134">Это элемент типа <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="3af53-134">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="3af53-135">\<Усернамеаусентикатион ></span><span class="sxs-lookup"><span data-stu-id="3af53-135">\<userNameAuthentication></span></span>](usernameauthentication.md)|<span data-ttu-id="3af53-136">Задает параметры для проверки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="3af53-136">Specifies the settings for username password validation.</span></span> <span data-ttu-id="3af53-137">Это элемент типа <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="3af53-137">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="3af53-138">\<windowsAuthentication ></span><span class="sxs-lookup"><span data-stu-id="3af53-138">\<windowsAuthentication></span></span>](windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="3af53-139">Задает параметры для проверки учетных данных ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="3af53-139">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="3af53-140">Это элемент типа <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="3af53-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3af53-141">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3af53-141">Parent Elements</span></span>  
  
|<span data-ttu-id="3af53-142">Элемент</span><span class="sxs-lookup"><span data-stu-id="3af53-142">Element</span></span>|<span data-ttu-id="3af53-143">Описание</span><span class="sxs-lookup"><span data-stu-id="3af53-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3af53-144">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="3af53-144">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="3af53-145">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="3af53-145">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3af53-146">См. также</span><span class="sxs-lookup"><span data-stu-id="3af53-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="3af53-147">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="3af53-147">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
