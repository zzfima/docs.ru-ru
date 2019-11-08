---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 2ff70d3a8636970434582e417e4549ab6b433fc1
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738763"
---
# <a name="privacynoticeat"></a><span data-ttu-id="35f3d-101">\<Привацинотицеат ></span><span class="sxs-lookup"><span data-stu-id="35f3d-101">\<privacyNoticeAt></span></span>
<span data-ttu-id="35f3d-102">Представляет элемент конфигурации, который задает уведомление о конфиденциальности, используемое в привязке `wsFederationHttp`.</span><span class="sxs-lookup"><span data-stu-id="35f3d-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
<span data-ttu-id="35f3d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="35f3d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="35f3d-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="35f3d-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="35f3d-105">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="35f3d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="35f3d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="35f3d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="35f3d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="35f3d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="35f3d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<privacyNotice >**</span><span class="sxs-lookup"><span data-stu-id="35f3d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<privacyNotice>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35f3d-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="35f3d-109">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="35f3d-110">Type</span><span class="sxs-lookup"><span data-stu-id="35f3d-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35f3d-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="35f3d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="35f3d-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="35f3d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35f3d-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="35f3d-113">Attributes</span></span>  
  
|<span data-ttu-id="35f3d-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="35f3d-114">Attribute</span></span>|<span data-ttu-id="35f3d-115">Описание</span><span class="sxs-lookup"><span data-stu-id="35f3d-115">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="35f3d-116">Строка, задающая универсальный код ресурса (URI), определяющий расположение примечания о конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="35f3d-116">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="35f3d-117">Целое число, определяющее версию этого уведомления о конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="35f3d-117">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="35f3d-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="35f3d-118">Child Elements</span></span>  
 <span data-ttu-id="35f3d-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="35f3d-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="35f3d-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="35f3d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="35f3d-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="35f3d-121">Element</span></span>|<span data-ttu-id="35f3d-122">Описание</span><span class="sxs-lookup"><span data-stu-id="35f3d-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="35f3d-123">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="35f3d-123">\<binding></span></span>](bindings.md)|<span data-ttu-id="35f3d-124">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="35f3d-124">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="35f3d-125">См. также</span><span class="sxs-lookup"><span data-stu-id="35f3d-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="35f3d-126">Привязки</span><span class="sxs-lookup"><span data-stu-id="35f3d-126">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="35f3d-127">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="35f3d-127">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="35f3d-128">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="35f3d-128">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="35f3d-129">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="35f3d-129">\<customBinding></span></span>](custombinding.md)
