---
title: '&lt;время ожидания&gt;'
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: 1f0638f85177d2acb6f61e3246a1a5ee9a4e2f5c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="lttimeoutsgt"></a><span data-ttu-id="0e8fc-102">&lt;время ожидания&gt;</span><span class="sxs-lookup"><span data-stu-id="0e8fc-102">&lt;timeOuts&gt;</span></span>
<span data-ttu-id="0e8fc-103">Элемент конфигурации, который задает допустимый интервал времени для открытия или закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="0e8fc-103">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="0e8fc-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="0e8fc-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0e8fc-105">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="0e8fc-105">\<client></span></span>  
<span data-ttu-id="0e8fc-106">\<Конечная точка ></span><span class="sxs-lookup"><span data-stu-id="0e8fc-106">\<endpoint></span></span>  
<span data-ttu-id="0e8fc-107">\<узел ></span><span class="sxs-lookup"><span data-stu-id="0e8fc-107">\<host></span></span>  
<span data-ttu-id="0e8fc-108">\<время ожидания ></span><span class="sxs-lookup"><span data-stu-id="0e8fc-108">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e8fc-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0e8fc-109">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"  
   openTimeout="TimeSpan" >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e8fc-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0e8fc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0e8fc-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0e8fc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e8fc-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0e8fc-112">Attributes</span></span>  
  
|<span data-ttu-id="0e8fc-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0e8fc-113">Attribute</span></span>|<span data-ttu-id="0e8fc-114">Описание</span><span class="sxs-lookup"><span data-stu-id="0e8fc-114">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="0e8fc-115">Значение <xref:System.TimeSpan>, которое задает временной интервал, выделенный для операции закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="0e8fc-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="0e8fc-116">Значение <xref:System.TimeSpan>, которое задает временной интервал, выделенный для операции открытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="0e8fc-116">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e8fc-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0e8fc-117">Child Elements</span></span>  
 <span data-ttu-id="0e8fc-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0e8fc-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0e8fc-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0e8fc-119">Parent Elements</span></span>  
  
|<span data-ttu-id="0e8fc-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="0e8fc-120">Element</span></span>|<span data-ttu-id="0e8fc-121">Описание</span><span class="sxs-lookup"><span data-stu-id="0e8fc-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0e8fc-122">\<узел ></span><span class="sxs-lookup"><span data-stu-id="0e8fc-122">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="0e8fc-123">Элемент конфигурации, который задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="0e8fc-123">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0e8fc-124">См. также</span><span class="sxs-lookup"><span data-stu-id="0e8fc-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="0e8fc-125">Размещение</span><span class="sxs-lookup"><span data-stu-id="0e8fc-125">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
