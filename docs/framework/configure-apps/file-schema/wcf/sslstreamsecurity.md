---
title: '&lt;sslStreamSecurity&gt;'
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
author: BrucePerlerMS
ms.openlocfilehash: 6eacf1833ecf980696d75c5dbcaaba3ba6403d92
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47087454"
---
# <a name="ltsslstreamsecuritygt"></a><span data-ttu-id="a4032-102">&lt;sslStreamSecurity&gt;</span><span class="sxs-lookup"><span data-stu-id="a4032-102">&lt;sslStreamSecurity&gt;</span></span>
<span data-ttu-id="a4032-103">Предоставляет пользовательский элемент привязки, поддерживающий безопасность канала с помощью потока SSL.</span><span class="sxs-lookup"><span data-stu-id="a4032-103">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="a4032-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="a4032-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a4032-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="a4032-105">\<bindings></span></span>  
<span data-ttu-id="a4032-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="a4032-106">\<customBinding></span></span>  
<span data-ttu-id="a4032-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="a4032-107">\<binding></span></span>  
<span data-ttu-id="a4032-108">\<sslStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="a4032-108">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4032-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a4032-109">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"      sslProtocols="Ssl3|Tls|Tls11|Tls12" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4032-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a4032-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a4032-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a4032-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4032-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a4032-112">Attributes</span></span>  
  
|<span data-ttu-id="a4032-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a4032-113">Attribute</span></span>|<span data-ttu-id="a4032-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a4032-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a4032-115">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="a4032-115">requireClientCertificate</span></span>|<span data-ttu-id="a4032-116">Логическое значение, указывающее, требуется ли для этой привязки сертификат клиента.</span><span class="sxs-lookup"><span data-stu-id="a4032-116">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="a4032-117">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="a4032-117">The default is `false`.</span></span>|  
|<span data-ttu-id="a4032-118">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="a4032-118">sslProtocols</span></span>|<span data-ttu-id="a4032-119">Значение флага перечисления SslProtocols, указывающее, какие протоколы SslProtocols поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="a4032-119">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="a4032-120">Значение по умолчанию — Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="a4032-120">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a4032-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a4032-121">Child Elements</span></span>  
 <span data-ttu-id="a4032-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a4032-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a4032-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a4032-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a4032-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="a4032-124">Element</span></span>|<span data-ttu-id="a4032-125">Описание</span><span class="sxs-lookup"><span data-stu-id="a4032-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a4032-126">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="a4032-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="a4032-127">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="a4032-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a4032-128">См. также</span><span class="sxs-lookup"><span data-stu-id="a4032-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
 [<span data-ttu-id="a4032-129">Привязки</span><span class="sxs-lookup"><span data-stu-id="a4032-129">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="a4032-130">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="a4032-130">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="a4032-131">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="a4032-131">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="a4032-132">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="a4032-132">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
