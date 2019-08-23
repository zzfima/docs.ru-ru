---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: 5ed87adfb3963513602844fc69afce8f7994fa8e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932427"
---
# <a name="sslstreamsecurity"></a><span data-ttu-id="517aa-101">\<Раздел sslstreamsecurity ></span><span class="sxs-lookup"><span data-stu-id="517aa-101">\<sslStreamSecurity></span></span>
<span data-ttu-id="517aa-102">Представляет пользовательский элемент привязки, который поддерживает безопасность канала с помощью потока SSL.</span><span class="sxs-lookup"><span data-stu-id="517aa-102">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="517aa-103">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="517aa-103">\<system.serviceModel></span></span>  
<span data-ttu-id="517aa-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="517aa-104">\<bindings></span></span>  
<span data-ttu-id="517aa-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="517aa-105">\<customBinding></span></span>  
<span data-ttu-id="517aa-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="517aa-106">\<binding></span></span>  
<span data-ttu-id="517aa-107">\<Раздел sslstreamsecurity ></span><span class="sxs-lookup"><span data-stu-id="517aa-107">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="517aa-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="517aa-108">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="517aa-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="517aa-109">Attributes and Elements</span></span>  
 <span data-ttu-id="517aa-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="517aa-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="517aa-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="517aa-111">Attributes</span></span>  
  
|<span data-ttu-id="517aa-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="517aa-112">Attribute</span></span>|<span data-ttu-id="517aa-113">Описание</span><span class="sxs-lookup"><span data-stu-id="517aa-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="517aa-114">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="517aa-114">requireClientCertificate</span></span>|<span data-ttu-id="517aa-115">Логическое значение, указывающее, требуется ли для этой привязки сертификат клиента.</span><span class="sxs-lookup"><span data-stu-id="517aa-115">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="517aa-116">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="517aa-116">The default is `false`.</span></span>|  
|<span data-ttu-id="517aa-117">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="517aa-117">sslProtocols</span></span>|<span data-ttu-id="517aa-118">Значение флага перечисления SslProtocols, указывающее, какие протоколы SslProtocols поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="517aa-118">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="517aa-119">Значение по умолчанию&#124;—&#124;Ssl3&#124;TLS Tls11 Tls12.</span><span class="sxs-lookup"><span data-stu-id="517aa-119">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="517aa-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="517aa-120">Child Elements</span></span>  
 <span data-ttu-id="517aa-121">Нет.</span><span class="sxs-lookup"><span data-stu-id="517aa-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="517aa-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="517aa-122">Parent Elements</span></span>  
  
|<span data-ttu-id="517aa-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="517aa-123">Element</span></span>|<span data-ttu-id="517aa-124">Описание</span><span class="sxs-lookup"><span data-stu-id="517aa-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="517aa-125">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="517aa-125">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="517aa-126">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="517aa-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="517aa-127">См. также</span><span class="sxs-lookup"><span data-stu-id="517aa-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="517aa-128">Привязки</span><span class="sxs-lookup"><span data-stu-id="517aa-128">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="517aa-129">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="517aa-129">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="517aa-130">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="517aa-130">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="517aa-131">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="517aa-131">\<customBinding></span></span>](custombinding.md)
