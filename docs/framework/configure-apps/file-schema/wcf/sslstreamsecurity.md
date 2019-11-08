---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: c5c7ec2b18143ff4d71540a60e24b8225ca4db16
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738595"
---
# <a name="sslstreamsecurity"></a><span data-ttu-id="a0dc3-101">\<раздел sslstreamsecurity ></span><span class="sxs-lookup"><span data-stu-id="a0dc3-101">\<sslStreamSecurity></span></span>
<span data-ttu-id="a0dc3-102">Представляет пользовательский элемент привязки, который поддерживает безопасность канала с помощью потока SSL.</span><span class="sxs-lookup"><span data-stu-id="a0dc3-102">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
<span data-ttu-id="a0dc3-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a0dc3-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a0dc3-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a0dc3-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a0dc3-105">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="a0dc3-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="a0dc3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="a0dc3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="a0dc3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="a0dc3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="a0dc3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<раздел sslstreamsecurity >**</span><span class="sxs-lookup"><span data-stu-id="a0dc3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sslStreamSecurity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0dc3-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0dc3-109">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0dc3-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a0dc3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a0dc3-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a0dc3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0dc3-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a0dc3-112">Attributes</span></span>  
  
|<span data-ttu-id="a0dc3-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a0dc3-113">Attribute</span></span>|<span data-ttu-id="a0dc3-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a0dc3-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a0dc3-115">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="a0dc3-115">requireClientCertificate</span></span>|<span data-ttu-id="a0dc3-116">Логическое значение, указывающее, требуется ли для этой привязки сертификат клиента.</span><span class="sxs-lookup"><span data-stu-id="a0dc3-116">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="a0dc3-117">Значение по умолчанию: `false`.</span><span class="sxs-lookup"><span data-stu-id="a0dc3-117">The default is `false`.</span></span>|  
|<span data-ttu-id="a0dc3-118">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="a0dc3-118">sslProtocols</span></span>|<span data-ttu-id="a0dc3-119">Значение флага перечисления SslProtocols, указывающее, какие протоколы SslProtocols поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="a0dc3-119">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="a0dc3-120">Значение по умолчанию&#124;—&#124;Ssl3&#124;TLS Tls11 Tls12.</span><span class="sxs-lookup"><span data-stu-id="a0dc3-120">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a0dc3-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a0dc3-121">Child Elements</span></span>  
 <span data-ttu-id="a0dc3-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a0dc3-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a0dc3-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a0dc3-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a0dc3-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="a0dc3-124">Element</span></span>|<span data-ttu-id="a0dc3-125">Описание</span><span class="sxs-lookup"><span data-stu-id="a0dc3-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0dc3-126">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="a0dc3-126">\<binding></span></span>](bindings.md)|<span data-ttu-id="a0dc3-127">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="a0dc3-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a0dc3-128">См. также</span><span class="sxs-lookup"><span data-stu-id="a0dc3-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="a0dc3-129">Привязки</span><span class="sxs-lookup"><span data-stu-id="a0dc3-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a0dc3-130">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="a0dc3-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="a0dc3-131">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="a0dc3-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="a0dc3-132">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="a0dc3-132">\<customBinding></span></span>](custombinding.md)
