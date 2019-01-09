---
title: '&lt;privacyNoticeAt&gt;'
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 104b2b6399ea31273045e43be716947db110715d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147321"
---
# <a name="ltprivacynoticeatgt"></a><span data-ttu-id="8eb77-102">&lt;privacyNoticeAt&gt;</span><span class="sxs-lookup"><span data-stu-id="8eb77-102">&lt;privacyNoticeAt&gt;</span></span>
<span data-ttu-id="8eb77-103">Представляет элемент конфигурации, который задает уведомление о конфиденциальности, используемое в привязке `wsFederationHttp`.</span><span class="sxs-lookup"><span data-stu-id="8eb77-103">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
 <span data-ttu-id="8eb77-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="8eb77-104">\<system.serviceModel></span></span>  
<span data-ttu-id="8eb77-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="8eb77-105">\<bindings></span></span>  
<span data-ttu-id="8eb77-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="8eb77-106">\<customBinding></span></span>  
<span data-ttu-id="8eb77-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="8eb77-107">\<binding></span></span>  
<span data-ttu-id="8eb77-108">\<privacyNotice ></span><span class="sxs-lookup"><span data-stu-id="8eb77-108">\<privacyNotice></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8eb77-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8eb77-109">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="8eb77-110">Тип</span><span class="sxs-lookup"><span data-stu-id="8eb77-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8eb77-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8eb77-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8eb77-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8eb77-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8eb77-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8eb77-113">Attributes</span></span>  
  
|<span data-ttu-id="8eb77-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8eb77-114">Attribute</span></span>|<span data-ttu-id="8eb77-115">Описание</span><span class="sxs-lookup"><span data-stu-id="8eb77-115">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="8eb77-116">Строка, задающая универсальный код ресурса (URI), определяющий расположение примечания о конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="8eb77-116">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="8eb77-117">Целое число, определяющее версию этого уведомления о конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="8eb77-117">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8eb77-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8eb77-118">Child Elements</span></span>  
 <span data-ttu-id="8eb77-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8eb77-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8eb77-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8eb77-120">Parent Elements</span></span>  
  
|<span data-ttu-id="8eb77-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="8eb77-121">Element</span></span>|<span data-ttu-id="8eb77-122">Описание</span><span class="sxs-lookup"><span data-stu-id="8eb77-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8eb77-123">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="8eb77-123">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="8eb77-124">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="8eb77-124">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8eb77-125">См. также</span><span class="sxs-lookup"><span data-stu-id="8eb77-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>  
 <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="8eb77-126">Привязки</span><span class="sxs-lookup"><span data-stu-id="8eb77-126">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="8eb77-127">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="8eb77-127">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="8eb77-128">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="8eb77-128">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="8eb77-129">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="8eb77-129">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
