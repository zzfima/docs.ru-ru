---
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: f295fe48e194611c80b78c0c23ab3e66ea1c0b64
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400501"
---
# <a name="clientcredentials"></a><span data-ttu-id="292a1-101">\<> clientCredentials</span><span class="sxs-lookup"><span data-stu-id="292a1-101">\<clientCredentials></span></span>
<span data-ttu-id="292a1-102">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="292a1-102">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
<span data-ttu-id="292a1-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="292a1-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="292a1-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="292a1-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="292a1-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="292a1-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="292a1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="292a1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="292a1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="292a1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="292a1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> clientCredentials**</span><span class="sxs-lookup"><span data-stu-id="292a1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCredentials>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="292a1-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="292a1-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="292a1-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="292a1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="292a1-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="292a1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="292a1-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="292a1-112">Attributes</span></span>  
  
|<span data-ttu-id="292a1-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="292a1-113">Attribute</span></span>|<span data-ttu-id="292a1-114">Описание</span><span class="sxs-lookup"><span data-stu-id="292a1-114">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="292a1-115">Логическое значение, которое указывает, может ли текущий пользователь принимать участие в выборе учетных данных клиента во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="292a1-115">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="292a1-116">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="292a1-116">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="292a1-117">Строка, задающая тип данного элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="292a1-117">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="292a1-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="292a1-118">Child Elements</span></span>  
  
|<span data-ttu-id="292a1-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="292a1-119">Element</span></span>|<span data-ttu-id="292a1-120">Описание</span><span class="sxs-lookup"><span data-stu-id="292a1-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="292a1-121">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="292a1-121">\<clientCertificate></span></span>](clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="292a1-122">Задает сертификат, используемый для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="292a1-122">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="292a1-123">Это элемент типа <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="292a1-123">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="292a1-124">\<Хттпдижест ></span><span class="sxs-lookup"><span data-stu-id="292a1-124">\<httpDigest></span></span>](httpdigest-element.md)|<span data-ttu-id="292a1-125">Задает хэш-код, используемый для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="292a1-125">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="292a1-126">Это элемент типа <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span><span class="sxs-lookup"><span data-stu-id="292a1-126">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[<span data-ttu-id="292a1-127">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="292a1-127">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="292a1-128">Задает тип пользовательского маркера, используемого для проверки подлинности клиента при подключении к службе маркеров безопасности (STS).</span><span class="sxs-lookup"><span data-stu-id="292a1-128">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="292a1-129">Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span><span class="sxs-lookup"><span data-stu-id="292a1-129">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[<span data-ttu-id="292a1-130">\<Одноранговые ></span><span class="sxs-lookup"><span data-stu-id="292a1-130">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="292a1-131">Задает учетные данные текущего однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="292a1-131">Specifies a current peer credential.</span></span> <span data-ttu-id="292a1-132">Это элемент типа <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="292a1-132">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="292a1-133">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="292a1-133">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="292a1-134">Задает сертификат, используемый при проверки подлинности службы для клиента, и предоставляет структуру для настройки параметров сертификата.</span><span class="sxs-lookup"><span data-stu-id="292a1-134">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="292a1-135">Данный сертификат должен быть предоставлен вне диапазона службой клиенту.</span><span class="sxs-lookup"><span data-stu-id="292a1-135">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="292a1-136">Это элемент типа <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="292a1-136">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="292a1-137">\<> Windows</span><span class="sxs-lookup"><span data-stu-id="292a1-137">\<windows></span></span>](windows-of-clientcredentials-element.md)|<span data-ttu-id="292a1-138">Задает учетные данные Windows.</span><span class="sxs-lookup"><span data-stu-id="292a1-138">Specifies a Windows credential.</span></span> <span data-ttu-id="292a1-139">Значением по умолчанию являются учетные данные текущего потока.</span><span class="sxs-lookup"><span data-stu-id="292a1-139">The default is the credential of the current thread.</span></span> <span data-ttu-id="292a1-140">Это элемент типа <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span><span class="sxs-lookup"><span data-stu-id="292a1-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="292a1-141">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="292a1-141">Parent Elements</span></span>  
  
|<span data-ttu-id="292a1-142">Элемент</span><span class="sxs-lookup"><span data-stu-id="292a1-142">Element</span></span>|<span data-ttu-id="292a1-143">Описание</span><span class="sxs-lookup"><span data-stu-id="292a1-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="292a1-144">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="292a1-144">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="292a1-145">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="292a1-145">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="292a1-146">Примечания</span><span class="sxs-lookup"><span data-stu-id="292a1-146">Remarks</span></span>  
 <span data-ttu-id="292a1-147">Учетные данные клиента используются для проверки подлинности клиента при подключении к службам в случаях, когда требуется взаимная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="292a1-147">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="292a1-148">Данный раздел конфигурации также можно использовать для задания сертификатов служб для сценариев, где клиент должен обеспечить защиту сообщений, передаваемых службе, с помощью сертификатов службы.</span><span class="sxs-lookup"><span data-stu-id="292a1-148">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="292a1-149">См. также</span><span class="sxs-lookup"><span data-stu-id="292a1-149">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [<span data-ttu-id="292a1-150">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="292a1-150">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="292a1-151">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="292a1-151">Securing Clients</span></span>](../../../wcf/securing-clients.md)
