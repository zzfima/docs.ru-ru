---
title: <add> из <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: d66be51fa2626283063c250905efdb7d47babfb0
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55279946"
---
# <a name="add-of-baseaddresses"></a><span data-ttu-id="2e3b0-102">\<Добавить > из \<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="2e3b0-102">\<add> of \<baseAddresses></span></span>
<span data-ttu-id="2e3b0-103">Представляет элемент конфигурации, который задает базовые адреса, используемые узлом службы.</span><span class="sxs-lookup"><span data-stu-id="2e3b0-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
 <span data-ttu-id="2e3b0-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2e3b0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2e3b0-105">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="2e3b0-105">\<client></span></span>  
<span data-ttu-id="2e3b0-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="2e3b0-106">\<endpoint></span></span>  
<span data-ttu-id="2e3b0-107">\<узел ></span><span class="sxs-lookup"><span data-stu-id="2e3b0-107">\<host></span></span>  
<span data-ttu-id="2e3b0-108">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="2e3b0-108">\<baseAddresses></span></span>  
<span data-ttu-id="2e3b0-109">\<baseAddress></span><span class="sxs-lookup"><span data-stu-id="2e3b0-109">\<baseAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e3b0-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e3b0-110">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a><span data-ttu-id="2e3b0-111">Тип</span><span class="sxs-lookup"><span data-stu-id="2e3b0-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e3b0-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2e3b0-112">Attributes and Elements</span></span>  
 <span data-ttu-id="2e3b0-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2e3b0-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e3b0-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2e3b0-114">Attributes</span></span>  
  
|<span data-ttu-id="2e3b0-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2e3b0-115">Attribute</span></span>|<span data-ttu-id="2e3b0-116">Описание</span><span class="sxs-lookup"><span data-stu-id="2e3b0-116">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="2e3b0-117">Строка, которая задает базовый адрес, используемый узлом службы.</span><span class="sxs-lookup"><span data-stu-id="2e3b0-117">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2e3b0-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2e3b0-118">Child Elements</span></span>  
 <span data-ttu-id="2e3b0-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2e3b0-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2e3b0-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2e3b0-120">Parent Elements</span></span>  
  
|<span data-ttu-id="2e3b0-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="2e3b0-121">Element</span></span>|<span data-ttu-id="2e3b0-122">Описание</span><span class="sxs-lookup"><span data-stu-id="2e3b0-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e3b0-123">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="2e3b0-123">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="2e3b0-124">Коллекция элементов `baseAddress`.</span><span class="sxs-lookup"><span data-stu-id="2e3b0-124">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2e3b0-125">См. также</span><span class="sxs-lookup"><span data-stu-id="2e3b0-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="2e3b0-126">Размещение</span><span class="sxs-lookup"><span data-stu-id="2e3b0-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
