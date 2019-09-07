---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 624b52c0618362f48063c8f7e7c53c5a68d7de8f
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400028"
---
# <a name="privacynoticeat"></a><span data-ttu-id="6e625-101">\<Привацинотицеат ></span><span class="sxs-lookup"><span data-stu-id="6e625-101">\<privacyNoticeAt></span></span>
<span data-ttu-id="6e625-102">Представляет элемент конфигурации, который задает уведомление о конфиденциальности, используемое в привязке `wsFederationHttp`.</span><span class="sxs-lookup"><span data-stu-id="6e625-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
<span data-ttu-id="6e625-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6e625-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6e625-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="6e625-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6e625-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="6e625-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="6e625-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="6e625-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="6e625-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="6e625-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="6e625-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<privacyNotice >**</span><span class="sxs-lookup"><span data-stu-id="6e625-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<privacyNotice>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e625-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6e625-109">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="6e625-110">Тип</span><span class="sxs-lookup"><span data-stu-id="6e625-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e625-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6e625-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6e625-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6e625-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e625-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6e625-113">Attributes</span></span>  
  
|<span data-ttu-id="6e625-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6e625-114">Attribute</span></span>|<span data-ttu-id="6e625-115">Описание</span><span class="sxs-lookup"><span data-stu-id="6e625-115">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="6e625-116">Строка, задающая универсальный код ресурса (URI), определяющий расположение примечания о конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="6e625-116">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="6e625-117">Целое число, определяющее версию этого уведомления о конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="6e625-117">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6e625-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6e625-118">Child Elements</span></span>  
 <span data-ttu-id="6e625-119">Нет.</span><span class="sxs-lookup"><span data-stu-id="6e625-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6e625-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6e625-120">Parent Elements</span></span>  
  
|<span data-ttu-id="6e625-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="6e625-121">Element</span></span>|<span data-ttu-id="6e625-122">Описание</span><span class="sxs-lookup"><span data-stu-id="6e625-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6e625-123">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="6e625-123">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="6e625-124">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="6e625-124">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6e625-125">См. также</span><span class="sxs-lookup"><span data-stu-id="6e625-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="6e625-126">Привязки</span><span class="sxs-lookup"><span data-stu-id="6e625-126">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6e625-127">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="6e625-127">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="6e625-128">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="6e625-128">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="6e625-129">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="6e625-129">\<customBinding></span></span>](custombinding.md)
