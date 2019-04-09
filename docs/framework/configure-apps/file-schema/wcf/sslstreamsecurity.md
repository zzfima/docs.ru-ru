---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: 67ec30b2bf3c322b949700789ce942e4281b77a4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204449"
---
# <a name="sslstreamsecurity"></a><span data-ttu-id="e7209-101">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="e7209-101">\<sslStreamSecurity></span></span>
<span data-ttu-id="e7209-102">Представляет пользовательский элемент привязки, который поддерживает безопасность канала с помощью потока SSL.</span><span class="sxs-lookup"><span data-stu-id="e7209-102">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="e7209-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e7209-103">\<system.serviceModel></span></span>  
<span data-ttu-id="e7209-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="e7209-104">\<bindings></span></span>  
<span data-ttu-id="e7209-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="e7209-105">\<customBinding></span></span>  
<span data-ttu-id="e7209-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="e7209-106">\<binding></span></span>  
<span data-ttu-id="e7209-107">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="e7209-107">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7209-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7209-108">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7209-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e7209-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e7209-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e7209-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7209-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e7209-111">Attributes</span></span>  
  
|<span data-ttu-id="e7209-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e7209-112">Attribute</span></span>|<span data-ttu-id="e7209-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e7209-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e7209-114">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="e7209-114">requireClientCertificate</span></span>|<span data-ttu-id="e7209-115">Логическое значение, указывающее, требуется ли для этой привязки сертификат клиента.</span><span class="sxs-lookup"><span data-stu-id="e7209-115">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="e7209-116">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="e7209-116">The default is `false`.</span></span>|  
|<span data-ttu-id="e7209-117">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="e7209-117">sslProtocols</span></span>|<span data-ttu-id="e7209-118">Значение флага перечисления SslProtocols, указывающее, какие протоколы SslProtocols поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="e7209-118">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="e7209-119">Значение по умолчанию — Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="e7209-119">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e7209-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e7209-120">Child Elements</span></span>  
 <span data-ttu-id="e7209-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e7209-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e7209-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e7209-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e7209-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="e7209-123">Element</span></span>|<span data-ttu-id="e7209-124">Описание</span><span class="sxs-lookup"><span data-stu-id="e7209-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7209-125">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="e7209-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="e7209-126">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="e7209-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e7209-127">См. также</span><span class="sxs-lookup"><span data-stu-id="e7209-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="e7209-128">Привязки</span><span class="sxs-lookup"><span data-stu-id="e7209-128">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="e7209-129">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="e7209-129">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e7209-130">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="e7209-130">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="e7209-131">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="e7209-131">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
