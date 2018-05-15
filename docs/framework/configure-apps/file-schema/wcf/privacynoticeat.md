---
title: '&lt;privacyNoticeAt&gt;'
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 2914a3716b9e2adb6ebc47fd73ccee027a3b65da
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltprivacynoticeatgt"></a><span data-ttu-id="e5198-102">&lt;privacyNoticeAt&gt;</span><span class="sxs-lookup"><span data-stu-id="e5198-102">&lt;privacyNoticeAt&gt;</span></span>
<span data-ttu-id="e5198-103">Представляет элемент конфигурации, который задает уведомление о конфиденциальности, используемое в привязке `wsFederationHttp`.</span><span class="sxs-lookup"><span data-stu-id="e5198-103">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
 <span data-ttu-id="e5198-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="e5198-104">\<system.serviceModel></span></span>  
<span data-ttu-id="e5198-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="e5198-105">\<bindings></span></span>  
<span data-ttu-id="e5198-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="e5198-106">\<customBinding></span></span>  
<span data-ttu-id="e5198-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="e5198-107">\<binding></span></span>  
<span data-ttu-id="e5198-108">\<privacyNotice ></span><span class="sxs-lookup"><span data-stu-id="e5198-108">\<privacyNotice></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5198-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5198-109">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"  
        version="Integer" />  
```  
  
## <a name="type"></a><span data-ttu-id="e5198-110">Тип</span><span class="sxs-lookup"><span data-stu-id="e5198-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5198-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e5198-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e5198-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e5198-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5198-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e5198-113">Attributes</span></span>  
  
|<span data-ttu-id="e5198-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e5198-114">Attribute</span></span>|<span data-ttu-id="e5198-115">Описание</span><span class="sxs-lookup"><span data-stu-id="e5198-115">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="e5198-116">Строка, задающая универсальный код ресурса (URI), определяющий расположение примечания о конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="e5198-116">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="e5198-117">Целое число, определяющее версию этого уведомления о конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="e5198-117">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5198-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e5198-118">Child Elements</span></span>  
 <span data-ttu-id="e5198-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e5198-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e5198-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e5198-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e5198-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="e5198-121">Element</span></span>|<span data-ttu-id="e5198-122">Описание</span><span class="sxs-lookup"><span data-stu-id="e5198-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5198-123">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="e5198-123">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="e5198-124">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="e5198-124">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5198-125">См. также</span><span class="sxs-lookup"><span data-stu-id="e5198-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>  
 <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="e5198-126">Привязки</span><span class="sxs-lookup"><span data-stu-id="e5198-126">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="e5198-127">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="e5198-127">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="e5198-128">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="e5198-128">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="e5198-129">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="e5198-129">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
