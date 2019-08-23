---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: f7349bf61082c5d8e5bd4249e01b8835a1861cb9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934259"
---
# <a name="privacynoticeat"></a><span data-ttu-id="11bde-101">\<Привацинотицеат ></span><span class="sxs-lookup"><span data-stu-id="11bde-101">\<privacyNoticeAt></span></span>
<span data-ttu-id="11bde-102">Представляет элемент конфигурации, который задает уведомление о конфиденциальности, используемое в привязке `wsFederationHttp`.</span><span class="sxs-lookup"><span data-stu-id="11bde-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
 <span data-ttu-id="11bde-103">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="11bde-103">\<system.serviceModel></span></span>  
<span data-ttu-id="11bde-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="11bde-104">\<bindings></span></span>  
<span data-ttu-id="11bde-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="11bde-105">\<customBinding></span></span>  
<span data-ttu-id="11bde-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="11bde-106">\<binding></span></span>  
<span data-ttu-id="11bde-107">\<privacyNotice ></span><span class="sxs-lookup"><span data-stu-id="11bde-107">\<privacyNotice></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11bde-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11bde-108">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="11bde-109">Тип</span><span class="sxs-lookup"><span data-stu-id="11bde-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="11bde-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="11bde-110">Attributes and Elements</span></span>  
 <span data-ttu-id="11bde-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="11bde-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="11bde-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="11bde-112">Attributes</span></span>  
  
|<span data-ttu-id="11bde-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="11bde-113">Attribute</span></span>|<span data-ttu-id="11bde-114">Описание</span><span class="sxs-lookup"><span data-stu-id="11bde-114">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="11bde-115">Строка, задающая универсальный код ресурса (URI), определяющий расположение примечания о конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="11bde-115">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="11bde-116">Целое число, определяющее версию этого уведомления о конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="11bde-116">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="11bde-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="11bde-117">Child Elements</span></span>  
 <span data-ttu-id="11bde-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="11bde-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="11bde-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="11bde-119">Parent Elements</span></span>  
  
|<span data-ttu-id="11bde-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="11bde-120">Element</span></span>|<span data-ttu-id="11bde-121">Описание</span><span class="sxs-lookup"><span data-stu-id="11bde-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="11bde-122">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="11bde-122">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="11bde-123">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="11bde-123">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11bde-124">См. также</span><span class="sxs-lookup"><span data-stu-id="11bde-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="11bde-125">Привязки</span><span class="sxs-lookup"><span data-stu-id="11bde-125">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="11bde-126">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="11bde-126">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="11bde-127">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="11bde-127">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="11bde-128">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="11bde-128">\<customBinding></span></span>](custombinding.md)
