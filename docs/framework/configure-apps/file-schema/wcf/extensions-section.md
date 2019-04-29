---
title: Раздел <extensions>
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: 0f77f621bbf9bbef00b206ef43a174f6f69364d5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673008"
---
# <a name="extensions-section"></a><span data-ttu-id="cba25-102">\<расширения > раздела</span><span class="sxs-lookup"><span data-stu-id="cba25-102">\<extensions> section</span></span>
<span data-ttu-id="cba25-103">Данный раздел конфигурации содержит коллекцию расширений, которые позволяют пользователю создавать пользовательские привязки, поведения и другие возможности расширений.</span><span class="sxs-lookup"><span data-stu-id="cba25-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
<span data-ttu-id="cba25-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cba25-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cba25-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cba25-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <extensions>
    <bindingExtensions>
    </bindingExtensions>
    <behaviorExtensions>
    </behaviorExtensions>
    <bindingElementExtensions>
    </bindingElementExtensions>
    <endpointExtensions>
    </endpointExtensions>
  </extensions>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cba25-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cba25-106">Attributes and Elements</span></span>  
 <span data-ttu-id="cba25-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cba25-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cba25-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cba25-108">Attributes</span></span>  
 <span data-ttu-id="cba25-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cba25-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cba25-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cba25-110">Child Elements</span></span>  
  
|<span data-ttu-id="cba25-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="cba25-111">Element</span></span>|<span data-ttu-id="cba25-112">Описание</span><span class="sxs-lookup"><span data-stu-id="cba25-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cba25-113">\<behaviorExtensions ></span><span class="sxs-lookup"><span data-stu-id="cba25-113">\<behaviorExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behaviorextensions.md)|<span data-ttu-id="cba25-114">Этот раздел содержит дочерние элементы, которые задают расширения поведений, которые позволяют пользователю настроить поведения службы или конечной точки.</span><span class="sxs-lookup"><span data-stu-id="cba25-114">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[<span data-ttu-id="cba25-115">\<bindingElementExtensions ></span><span class="sxs-lookup"><span data-stu-id="cba25-115">\<bindingElementExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindingelementextensions.md)|<span data-ttu-id="cba25-116">В этом разделе описывается, как обеспечивается использование пользовательского элемента привязки в файле конфигурации компьютера или приложения.</span><span class="sxs-lookup"><span data-stu-id="cba25-116">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[<span data-ttu-id="cba25-117">\<bindingExtensions ></span><span class="sxs-lookup"><span data-stu-id="cba25-117">\<bindingExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindingextensions.md)|<span data-ttu-id="cba25-118">Этот раздел содержит дочерние элементы, которые задают расширения привязки, которые позволяют пользователю настроить привязки.</span><span class="sxs-lookup"><span data-stu-id="cba25-118">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[<span data-ttu-id="cba25-119">\<endpointExtensions ></span><span class="sxs-lookup"><span data-stu-id="cba25-119">\<endpointExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointextensions.md)|<span data-ttu-id="cba25-120">Этот раздел содержит дочерние элементы, которые регистрируют стандартные конечные точки.</span><span class="sxs-lookup"><span data-stu-id="cba25-120">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cba25-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cba25-121">Parent Elements</span></span>  
  
|<span data-ttu-id="cba25-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="cba25-122">Element</span></span>|<span data-ttu-id="cba25-123">Описание</span><span class="sxs-lookup"><span data-stu-id="cba25-123">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cba25-124">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="cba25-124">system.ServiceModel</span></span>|<span data-ttu-id="cba25-125">Корневой элемент всех элементов конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="cba25-125">The root element of all WCF configuration elements.</span></span>|
