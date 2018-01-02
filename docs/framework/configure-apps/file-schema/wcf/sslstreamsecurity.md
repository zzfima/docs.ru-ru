---
title: '&lt;sslStreamSecurity&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
caps.latest.revision: "11"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 65233bf416080212a5c1447cffd329eca1b921f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltsslstreamsecuritygt"></a><span data-ttu-id="d0510-102">&lt;sslStreamSecurity&gt;</span><span class="sxs-lookup"><span data-stu-id="d0510-102">&lt;sslStreamSecurity&gt;</span></span>
<span data-ttu-id="d0510-103">Предоставляет пользовательский элемент привязки, поддерживающий безопасность канала с помощью потока SSL.</span><span class="sxs-lookup"><span data-stu-id="d0510-103">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="d0510-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="d0510-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d0510-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="d0510-105">\<bindings></span></span>  
<span data-ttu-id="d0510-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="d0510-106">\<customBinding></span></span>  
<span data-ttu-id="d0510-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="d0510-107">\<binding></span></span>  
<span data-ttu-id="d0510-108">\<sslStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="d0510-108">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0510-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0510-109">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"      sslProtocols="Ssl3|Tls|Tls11|Tls12" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0510-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d0510-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d0510-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d0510-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0510-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d0510-112">Attributes</span></span>  
  
|<span data-ttu-id="d0510-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d0510-113">Attribute</span></span>|<span data-ttu-id="d0510-114">Описание</span><span class="sxs-lookup"><span data-stu-id="d0510-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d0510-115">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="d0510-115">requireClientCertificate</span></span>|<span data-ttu-id="d0510-116">Логическое значение, указывающее, требуется ли для этой привязки сертификат клиента.</span><span class="sxs-lookup"><span data-stu-id="d0510-116">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="d0510-117">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="d0510-117">The default is `false`.</span></span>|  
|<span data-ttu-id="d0510-118">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="d0510-118">sslProtocols</span></span>|<span data-ttu-id="d0510-119">Значение флага перечисления SslProtocols, указывающее, какие протоколы SslProtocols поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="d0510-119">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="d0510-120">Значение по умолчанию — Ssl3 &#124; TLS &#124; Tls11 &#124; Tls12.</span><span class="sxs-lookup"><span data-stu-id="d0510-120">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d0510-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d0510-121">Child Elements</span></span>  
 <span data-ttu-id="d0510-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d0510-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d0510-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d0510-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d0510-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="d0510-124">Element</span></span>|<span data-ttu-id="d0510-125">Описание:</span><span class="sxs-lookup"><span data-stu-id="d0510-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d0510-126">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="d0510-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="d0510-127">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="d0510-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d0510-128">См. также</span><span class="sxs-lookup"><span data-stu-id="d0510-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
 [<span data-ttu-id="d0510-129">Привязки</span><span class="sxs-lookup"><span data-stu-id="d0510-129">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="d0510-130">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="d0510-130">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="d0510-131">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="d0510-131">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="d0510-132">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="d0510-132">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
