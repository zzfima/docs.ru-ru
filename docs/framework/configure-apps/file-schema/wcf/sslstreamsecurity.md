---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: f66569f36dc61a063b79a088dcbc405126a074d8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55284602"
---
# <a name="sslstreamsecurity"></a><span data-ttu-id="1cab4-101">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="1cab4-101">\<sslStreamSecurity></span></span>
<span data-ttu-id="1cab4-102">Предоставляет пользовательский элемент привязки, поддерживающий безопасность канала с помощью потока SSL.</span><span class="sxs-lookup"><span data-stu-id="1cab4-102">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="1cab4-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1cab4-103">\<system.serviceModel></span></span>  
<span data-ttu-id="1cab4-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="1cab4-104">\<bindings></span></span>  
<span data-ttu-id="1cab4-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="1cab4-105">\<customBinding></span></span>  
<span data-ttu-id="1cab4-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="1cab4-106">\<binding></span></span>  
<span data-ttu-id="1cab4-107">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="1cab4-107">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cab4-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1cab4-108">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1cab4-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1cab4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1cab4-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1cab4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1cab4-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1cab4-111">Attributes</span></span>  
  
|<span data-ttu-id="1cab4-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1cab4-112">Attribute</span></span>|<span data-ttu-id="1cab4-113">Описание</span><span class="sxs-lookup"><span data-stu-id="1cab4-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1cab4-114">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="1cab4-114">requireClientCertificate</span></span>|<span data-ttu-id="1cab4-115">Логическое значение, указывающее, требуется ли для этой привязки сертификат клиента.</span><span class="sxs-lookup"><span data-stu-id="1cab4-115">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="1cab4-116">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="1cab4-116">The default is `false`.</span></span>|  
|<span data-ttu-id="1cab4-117">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="1cab4-117">sslProtocols</span></span>|<span data-ttu-id="1cab4-118">Значение флага перечисления SslProtocols, указывающее, какие протоколы SslProtocols поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="1cab4-118">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="1cab4-119">Значение по умолчанию — Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="1cab4-119">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1cab4-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1cab4-120">Child Elements</span></span>  
 <span data-ttu-id="1cab4-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1cab4-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1cab4-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1cab4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="1cab4-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="1cab4-123">Element</span></span>|<span data-ttu-id="1cab4-124">Описание</span><span class="sxs-lookup"><span data-stu-id="1cab4-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1cab4-125">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="1cab4-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="1cab4-126">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="1cab4-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1cab4-127">См. также</span><span class="sxs-lookup"><span data-stu-id="1cab4-127">See also</span></span>
- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="1cab4-128">Привязки</span><span class="sxs-lookup"><span data-stu-id="1cab4-128">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="1cab4-129">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="1cab4-129">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="1cab4-130">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="1cab4-130">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="1cab4-131">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="1cab4-131">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
