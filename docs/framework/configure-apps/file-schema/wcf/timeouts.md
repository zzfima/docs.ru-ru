---
title: '&lt;время ожидания&gt;'
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: 42f4db1d954834cbfa3c526328cca45443751506
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629662"
---
# <a name="lttimeoutsgt"></a><span data-ttu-id="c7b98-102">&lt;время ожидания&gt;</span><span class="sxs-lookup"><span data-stu-id="c7b98-102">&lt;timeOuts&gt;</span></span>
<span data-ttu-id="c7b98-103">Элемент конфигурации, который задает допустимый интервал времени для открытия или закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="c7b98-103">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="c7b98-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c7b98-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c7b98-105">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="c7b98-105">\<client></span></span>  
<span data-ttu-id="c7b98-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="c7b98-106">\<endpoint></span></span>  
<span data-ttu-id="c7b98-107">\<узел ></span><span class="sxs-lookup"><span data-stu-id="c7b98-107">\<host></span></span>  
<span data-ttu-id="c7b98-108">\<время ожидания ></span><span class="sxs-lookup"><span data-stu-id="c7b98-108">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7b98-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7b98-109">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c7b98-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c7b98-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c7b98-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c7b98-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c7b98-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c7b98-112">Attributes</span></span>  
  
|<span data-ttu-id="c7b98-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c7b98-113">Attribute</span></span>|<span data-ttu-id="c7b98-114">Описание</span><span class="sxs-lookup"><span data-stu-id="c7b98-114">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="c7b98-115">Значение <xref:System.TimeSpan>, которое задает временной интервал, выделенный для операции закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="c7b98-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="c7b98-116">Значение <xref:System.TimeSpan>, которое задает временной интервал, выделенный для операции открытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="c7b98-116">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c7b98-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c7b98-117">Child Elements</span></span>  
 <span data-ttu-id="c7b98-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c7b98-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c7b98-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c7b98-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c7b98-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="c7b98-120">Element</span></span>|<span data-ttu-id="c7b98-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="c7b98-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c7b98-122">\<узел ></span><span class="sxs-lookup"><span data-stu-id="c7b98-122">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="c7b98-123">Элемент конфигурации, который задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="c7b98-123">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c7b98-124">См. также</span><span class="sxs-lookup"><span data-stu-id="c7b98-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="c7b98-125">Размещение</span><span class="sxs-lookup"><span data-stu-id="c7b98-125">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
