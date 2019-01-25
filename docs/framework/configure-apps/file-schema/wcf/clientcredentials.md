---
title: '&lt;ClientCredentials&gt;'
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: d8171254fed64a2d9ba526d5714d5707aa1b1c1e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646059"
---
# <a name="ltclientcredentialsgt"></a><span data-ttu-id="d09bc-102">&lt;ClientCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="d09bc-102">&lt;clientCredentials&gt;</span></span>
<span data-ttu-id="d09bc-103">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="d09bc-103">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
 <span data-ttu-id="d09bc-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d09bc-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d09bc-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="d09bc-105">\<behaviors></span></span>  
<span data-ttu-id="d09bc-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="d09bc-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="d09bc-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="d09bc-107">\<behavior></span></span>  
<span data-ttu-id="d09bc-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="d09bc-108">\<clientCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d09bc-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d09bc-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d09bc-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d09bc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d09bc-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d09bc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d09bc-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d09bc-112">Attributes</span></span>  
  
|<span data-ttu-id="d09bc-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d09bc-113">Attribute</span></span>|<span data-ttu-id="d09bc-114">Описание</span><span class="sxs-lookup"><span data-stu-id="d09bc-114">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="d09bc-115">Логическое значение, которое указывает, может ли текущий пользователь принимать участие в выборе учетных данных клиента во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d09bc-115">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="d09bc-116">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="d09bc-116">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="d09bc-117">Строка, задающая тип данного элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d09bc-117">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d09bc-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d09bc-118">Child Elements</span></span>  
  
|<span data-ttu-id="d09bc-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="d09bc-119">Element</span></span>|<span data-ttu-id="d09bc-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="d09bc-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d09bc-121">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="d09bc-121">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="d09bc-122">Задает сертификат, используемый для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="d09bc-122">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="d09bc-123">Это элемент типа <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="d09bc-123">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="d09bc-124">\<httpDigest></span><span class="sxs-lookup"><span data-stu-id="d09bc-124">\<httpDigest></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/httpdigest-element.md)|<span data-ttu-id="d09bc-125">Задает хэш-код, используемый для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="d09bc-125">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="d09bc-126">Это элемент типа <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span><span class="sxs-lookup"><span data-stu-id="d09bc-126">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[<span data-ttu-id="d09bc-127">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="d09bc-127">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="d09bc-128">Задает тип пользовательского маркера, используемого для проверки подлинности клиента при подключении к службе маркеров безопасности (STS).</span><span class="sxs-lookup"><span data-stu-id="d09bc-128">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="d09bc-129">Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span><span class="sxs-lookup"><span data-stu-id="d09bc-129">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[<span data-ttu-id="d09bc-130">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="d09bc-130">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="d09bc-131">Задает учетные данные текущего однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="d09bc-131">Specifies a current peer credential.</span></span> <span data-ttu-id="d09bc-132">Это элемент типа <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="d09bc-132">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="d09bc-133">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="d09bc-133">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="d09bc-134">Задает сертификат, используемый при проверки подлинности службы для клиента, и предоставляет структуру для настройки параметров сертификата.</span><span class="sxs-lookup"><span data-stu-id="d09bc-134">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="d09bc-135">Данный сертификат должен быть предоставлен вне диапазона службой клиенту.</span><span class="sxs-lookup"><span data-stu-id="d09bc-135">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="d09bc-136">Это элемент типа <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="d09bc-136">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="d09bc-137">\<Windows ></span><span class="sxs-lookup"><span data-stu-id="d09bc-137">\<windows></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windows-of-clientcredentials-element.md)|<span data-ttu-id="d09bc-138">Задает учетные данные Windows.</span><span class="sxs-lookup"><span data-stu-id="d09bc-138">Specifies a Windows credential.</span></span> <span data-ttu-id="d09bc-139">Значением по умолчанию являются учетные данные текущего потока.</span><span class="sxs-lookup"><span data-stu-id="d09bc-139">The default is the credential of the current thread.</span></span> <span data-ttu-id="d09bc-140">Это элемент типа <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span><span class="sxs-lookup"><span data-stu-id="d09bc-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d09bc-141">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d09bc-141">Parent Elements</span></span>  
  
|<span data-ttu-id="d09bc-142">Элемент</span><span class="sxs-lookup"><span data-stu-id="d09bc-142">Element</span></span>|<span data-ttu-id="d09bc-143">Описание</span><span class="sxs-lookup"><span data-stu-id="d09bc-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d09bc-144">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="d09bc-144">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="d09bc-145">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d09bc-145">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d09bc-146">Примечания</span><span class="sxs-lookup"><span data-stu-id="d09bc-146">Remarks</span></span>  
 <span data-ttu-id="d09bc-147">Учетные данные клиента используются для проверки подлинности клиента при подключении к службам в случаях, когда требуется взаимная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="d09bc-147">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="d09bc-148">Данный раздел конфигурации также можно использовать для задания сертификатов служб для сценариев, где клиент должен обеспечить защиту сообщений, передаваемых службе, с помощью сертификатов службы.</span><span class="sxs-lookup"><span data-stu-id="d09bc-148">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d09bc-149">См. также</span><span class="sxs-lookup"><span data-stu-id="d09bc-149">See also</span></span>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [<span data-ttu-id="d09bc-150">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="d09bc-150">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="d09bc-151">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="d09bc-151">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
