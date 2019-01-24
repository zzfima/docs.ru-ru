---
title: '&lt;add&gt; для &lt;baseAddresses&gt;'
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: 31edf570a7374a4b4fe31760d35ec196ecfcb3c6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54553572"
---
# <a name="ltaddgt-of-ltbaseaddressesgt"></a><span data-ttu-id="c5100-102">&lt;add&gt; для &lt;baseAddresses&gt;</span><span class="sxs-lookup"><span data-stu-id="c5100-102">&lt;add&gt; of &lt;baseAddresses&gt;</span></span>
<span data-ttu-id="c5100-103">Представляет элемент конфигурации, который задает базовые адреса, используемые узлом службы.</span><span class="sxs-lookup"><span data-stu-id="c5100-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
 <span data-ttu-id="c5100-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c5100-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c5100-105">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="c5100-105">\<client></span></span>  
<span data-ttu-id="c5100-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="c5100-106">\<endpoint></span></span>  
<span data-ttu-id="c5100-107">\<узел ></span><span class="sxs-lookup"><span data-stu-id="c5100-107">\<host></span></span>  
<span data-ttu-id="c5100-108">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="c5100-108">\<baseAddresses></span></span>  
<span data-ttu-id="c5100-109">\<baseAddress></span><span class="sxs-lookup"><span data-stu-id="c5100-109">\<baseAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5100-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5100-110">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a><span data-ttu-id="c5100-111">Тип</span><span class="sxs-lookup"><span data-stu-id="c5100-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c5100-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c5100-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c5100-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c5100-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c5100-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c5100-114">Attributes</span></span>  
  
|<span data-ttu-id="c5100-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c5100-115">Attribute</span></span>|<span data-ttu-id="c5100-116">Описание</span><span class="sxs-lookup"><span data-stu-id="c5100-116">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="c5100-117">Строка, которая задает базовый адрес, используемый узлом службы.</span><span class="sxs-lookup"><span data-stu-id="c5100-117">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c5100-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c5100-118">Child Elements</span></span>  
 <span data-ttu-id="c5100-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c5100-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c5100-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c5100-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c5100-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="c5100-121">Element</span></span>|<span data-ttu-id="c5100-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="c5100-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c5100-123">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="c5100-123">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="c5100-124">Коллекция элементов `baseAddress`.</span><span class="sxs-lookup"><span data-stu-id="c5100-124">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c5100-125">См. также</span><span class="sxs-lookup"><span data-stu-id="c5100-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="c5100-126">Размещение</span><span class="sxs-lookup"><span data-stu-id="c5100-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
