---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: e2ce2111e4bb26cc6a51b4a772b1d8a4d3238c70
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200770"
---
# <a name="privacynoticeat"></a><span data-ttu-id="e7b69-101">\<privacyNoticeAt></span><span class="sxs-lookup"><span data-stu-id="e7b69-101">\<privacyNoticeAt></span></span>
<span data-ttu-id="e7b69-102">Представляет элемент конфигурации, который задает уведомление о конфиденциальности, используемое в привязке `wsFederationHttp`.</span><span class="sxs-lookup"><span data-stu-id="e7b69-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
 <span data-ttu-id="e7b69-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e7b69-103">\<system.serviceModel></span></span>  
<span data-ttu-id="e7b69-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="e7b69-104">\<bindings></span></span>  
<span data-ttu-id="e7b69-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="e7b69-105">\<customBinding></span></span>  
<span data-ttu-id="e7b69-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="e7b69-106">\<binding></span></span>  
<span data-ttu-id="e7b69-107">\<privacyNotice></span><span class="sxs-lookup"><span data-stu-id="e7b69-107">\<privacyNotice></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7b69-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7b69-108">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="e7b69-109">Тип</span><span class="sxs-lookup"><span data-stu-id="e7b69-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7b69-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e7b69-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e7b69-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e7b69-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7b69-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e7b69-112">Attributes</span></span>  
  
|<span data-ttu-id="e7b69-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e7b69-113">Attribute</span></span>|<span data-ttu-id="e7b69-114">Описание</span><span class="sxs-lookup"><span data-stu-id="e7b69-114">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="e7b69-115">Строка, задающая универсальный код ресурса (URI), определяющий расположение примечания о конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="e7b69-115">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="e7b69-116">Целое число, определяющее версию этого уведомления о конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="e7b69-116">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e7b69-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e7b69-117">Child Elements</span></span>  
 <span data-ttu-id="e7b69-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e7b69-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e7b69-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e7b69-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e7b69-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="e7b69-120">Element</span></span>|<span data-ttu-id="e7b69-121">Описание</span><span class="sxs-lookup"><span data-stu-id="e7b69-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7b69-122">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="e7b69-122">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="e7b69-123">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="e7b69-123">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e7b69-124">См. также</span><span class="sxs-lookup"><span data-stu-id="e7b69-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="e7b69-125">Привязки</span><span class="sxs-lookup"><span data-stu-id="e7b69-125">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="e7b69-126">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="e7b69-126">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e7b69-127">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="e7b69-127">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="e7b69-128">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="e7b69-128">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
