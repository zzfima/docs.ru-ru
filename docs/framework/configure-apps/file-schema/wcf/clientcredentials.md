---
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: 7ee49d6960864826dc74fbff629f502fcc70b4bf
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254812"
---
# <a name="clientcredentials"></a><span data-ttu-id="52a83-101">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="52a83-101">\<clientCredentials></span></span>
<span data-ttu-id="52a83-102">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="52a83-102">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
 <span data-ttu-id="52a83-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="52a83-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="52a83-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="52a83-104">\<behaviors></span></span>  
<span data-ttu-id="52a83-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="52a83-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="52a83-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="52a83-106">\<behavior></span></span>  
<span data-ttu-id="52a83-107">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="52a83-107">\<clientCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52a83-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52a83-108">Syntax</span></span>  
  
```xml  
<clientCredentials type="String"
                   supportInteractive="Boolean" >
  <clientCertificate>
  </clientCertificate>
  <digest>
  </digest>
  <isuedToken>
  </isuedToken>
  <peer>
  </peer>
  <serviceCertificate>
  </serviceCertificate>
  <windowsAuthentication>
  </windowsAuthentication>
</clientCredentials>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52a83-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="52a83-109">Attributes and Elements</span></span>  
 <span data-ttu-id="52a83-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="52a83-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52a83-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="52a83-111">Attributes</span></span>  
  
|<span data-ttu-id="52a83-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="52a83-112">Attribute</span></span>|<span data-ttu-id="52a83-113">Описание</span><span class="sxs-lookup"><span data-stu-id="52a83-113">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="52a83-114">Логическое значение, которое указывает, может ли текущий пользователь принимать участие в выборе учетных данных клиента во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="52a83-114">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="52a83-115">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="52a83-115">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="52a83-116">Строка, задающая тип данного элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="52a83-116">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="52a83-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="52a83-117">Child Elements</span></span>  
  
|<span data-ttu-id="52a83-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="52a83-118">Element</span></span>|<span data-ttu-id="52a83-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="52a83-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52a83-120">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="52a83-120">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="52a83-121">Задает сертификат, используемый для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="52a83-121">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="52a83-122">Это элемент типа <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="52a83-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="52a83-123">\<httpDigest></span><span class="sxs-lookup"><span data-stu-id="52a83-123">\<httpDigest></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/httpdigest-element.md)|<span data-ttu-id="52a83-124">Задает хэш-код, используемый для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="52a83-124">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="52a83-125">Это элемент типа <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span><span class="sxs-lookup"><span data-stu-id="52a83-125">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[<span data-ttu-id="52a83-126">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="52a83-126">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="52a83-127">Задает тип пользовательского маркера, используемого для проверки подлинности клиента при подключении к службе маркеров безопасности (STS).</span><span class="sxs-lookup"><span data-stu-id="52a83-127">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="52a83-128">Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span><span class="sxs-lookup"><span data-stu-id="52a83-128">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[<span data-ttu-id="52a83-129">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="52a83-129">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="52a83-130">Задает учетные данные текущего однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="52a83-130">Specifies a current peer credential.</span></span> <span data-ttu-id="52a83-131">Это элемент типа <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="52a83-131">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="52a83-132">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="52a83-132">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="52a83-133">Задает сертификат, используемый при проверки подлинности службы для клиента, и предоставляет структуру для настройки параметров сертификата.</span><span class="sxs-lookup"><span data-stu-id="52a83-133">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="52a83-134">Данный сертификат должен быть предоставлен вне диапазона службой клиенту.</span><span class="sxs-lookup"><span data-stu-id="52a83-134">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="52a83-135">Это элемент типа <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="52a83-135">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="52a83-136">\<Windows ></span><span class="sxs-lookup"><span data-stu-id="52a83-136">\<windows></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windows-of-clientcredentials-element.md)|<span data-ttu-id="52a83-137">Задает учетные данные Windows.</span><span class="sxs-lookup"><span data-stu-id="52a83-137">Specifies a Windows credential.</span></span> <span data-ttu-id="52a83-138">Значением по умолчанию являются учетные данные текущего потока.</span><span class="sxs-lookup"><span data-stu-id="52a83-138">The default is the credential of the current thread.</span></span> <span data-ttu-id="52a83-139">Это элемент типа <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span><span class="sxs-lookup"><span data-stu-id="52a83-139">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="52a83-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="52a83-140">Parent Elements</span></span>  
  
|<span data-ttu-id="52a83-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="52a83-141">Element</span></span>|<span data-ttu-id="52a83-142">Описание</span><span class="sxs-lookup"><span data-stu-id="52a83-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52a83-143">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="52a83-143">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="52a83-144">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="52a83-144">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52a83-145">Примечания</span><span class="sxs-lookup"><span data-stu-id="52a83-145">Remarks</span></span>  
 <span data-ttu-id="52a83-146">Учетные данные клиента используются для проверки подлинности клиента при подключении к службам в случаях, когда требуется взаимная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="52a83-146">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="52a83-147">Данный раздел конфигурации также можно использовать для задания сертификатов служб для сценариев, где клиент должен обеспечить защиту сообщений, передаваемых службе, с помощью сертификатов службы.</span><span class="sxs-lookup"><span data-stu-id="52a83-147">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52a83-148">См. также</span><span class="sxs-lookup"><span data-stu-id="52a83-148">See also</span></span>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [<span data-ttu-id="52a83-149">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="52a83-149">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="52a83-150">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="52a83-150">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
