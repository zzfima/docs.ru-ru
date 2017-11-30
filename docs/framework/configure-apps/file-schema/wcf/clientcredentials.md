---
title: '&lt;clientCredentials&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a8a1b3f5f7e8eea555be10870bc00f9b975c57a3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltclientcredentialsgt"></a><span data-ttu-id="c9127-102">&lt;clientCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="c9127-102">&lt;clientCredentials&gt;</span></span>
<span data-ttu-id="c9127-103">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="c9127-103">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
 <span data-ttu-id="c9127-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c9127-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c9127-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="c9127-105">\<behaviors></span></span>  
<span data-ttu-id="c9127-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="c9127-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="c9127-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="c9127-107">\<behavior></span></span>  
<span data-ttu-id="c9127-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="c9127-108">\<clientCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9127-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c9127-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9127-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c9127-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c9127-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c9127-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9127-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c9127-112">Attributes</span></span>  
  
|<span data-ttu-id="c9127-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c9127-113">Attribute</span></span>|<span data-ttu-id="c9127-114">Описание</span><span class="sxs-lookup"><span data-stu-id="c9127-114">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="c9127-115">Логическое значение, которое указывает, может ли текущий пользователь принимать участие в выборе учетных данных клиента во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="c9127-115">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="c9127-116">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="c9127-116">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="c9127-117">Строка, задающая тип данного элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c9127-117">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c9127-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c9127-118">Child Elements</span></span>  
  
|<span data-ttu-id="c9127-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="c9127-119">Element</span></span>|<span data-ttu-id="c9127-120">Описание</span><span class="sxs-lookup"><span data-stu-id="c9127-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9127-121">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="c9127-121">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="c9127-122">Задает сертификат, используемый для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="c9127-122">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="c9127-123">Это элемент типа <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="c9127-123">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="c9127-124">\<httpDigest ></span><span class="sxs-lookup"><span data-stu-id="c9127-124">\<httpDigest></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/httpdigest-element.md)|<span data-ttu-id="c9127-125">Задает хэш-код, используемый для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="c9127-125">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="c9127-126">Это элемент типа <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span><span class="sxs-lookup"><span data-stu-id="c9127-126">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[<span data-ttu-id="c9127-127">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="c9127-127">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="c9127-128">Задает тип пользовательского маркера, используемого для проверки подлинности клиента при подключении к службе маркеров безопасности (STS).</span><span class="sxs-lookup"><span data-stu-id="c9127-128">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="c9127-129">Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span><span class="sxs-lookup"><span data-stu-id="c9127-129">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[<span data-ttu-id="c9127-130">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="c9127-130">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="c9127-131">Задает учетные данные текущего однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="c9127-131">Specifies a current peer credential.</span></span> <span data-ttu-id="c9127-132">Это элемент типа <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="c9127-132">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="c9127-133">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="c9127-133">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="c9127-134">Задает сертификат, используемый при проверки подлинности службы для клиента, и предоставляет структуру для настройки параметров сертификата.</span><span class="sxs-lookup"><span data-stu-id="c9127-134">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="c9127-135">Данный сертификат должен быть предоставлен вне диапазона службой клиенту.</span><span class="sxs-lookup"><span data-stu-id="c9127-135">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="c9127-136">Это элемент типа <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="c9127-136">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="c9127-137">\<Windows ></span><span class="sxs-lookup"><span data-stu-id="c9127-137">\<windows></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windows-of-clientcredentials-element.md)|<span data-ttu-id="c9127-138">Задает учетные данные Windows.</span><span class="sxs-lookup"><span data-stu-id="c9127-138">Specifies a Windows credential.</span></span> <span data-ttu-id="c9127-139">Значением по умолчанию являются учетные данные текущего потока.</span><span class="sxs-lookup"><span data-stu-id="c9127-139">The default is the credential of the current thread.</span></span> <span data-ttu-id="c9127-140">Это элемент типа <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span><span class="sxs-lookup"><span data-stu-id="c9127-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c9127-141">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c9127-141">Parent Elements</span></span>  
  
|<span data-ttu-id="c9127-142">Элемент</span><span class="sxs-lookup"><span data-stu-id="c9127-142">Element</span></span>|<span data-ttu-id="c9127-143">Описание</span><span class="sxs-lookup"><span data-stu-id="c9127-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9127-144">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="c9127-144">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="c9127-145">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="c9127-145">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9127-146">Примечания</span><span class="sxs-lookup"><span data-stu-id="c9127-146">Remarks</span></span>  
 <span data-ttu-id="c9127-147">Учетные данные клиента используются для проверки подлинности клиента при подключении к службам в случаях, когда требуется взаимная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="c9127-147">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="c9127-148">Данный раздел конфигурации также можно использовать для задания сертификатов служб для сценариев, где клиент должен обеспечить защиту сообщений, передаваемых службе, с помощью сертификатов службы.</span><span class="sxs-lookup"><span data-stu-id="c9127-148">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9127-149">См. также</span><span class="sxs-lookup"><span data-stu-id="c9127-149">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 [<span data-ttu-id="c9127-150">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="c9127-150">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="c9127-151">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="c9127-151">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
