---
title: '&lt;время ожидания&gt;'
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: e39deeb251865b87eb7734e4447088ca2f221d1d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148335"
---
# <a name="lttimeoutsgt"></a><span data-ttu-id="59f0c-102">&lt;время ожидания&gt;</span><span class="sxs-lookup"><span data-stu-id="59f0c-102">&lt;timeOuts&gt;</span></span>
<span data-ttu-id="59f0c-103">Элемент конфигурации, который задает допустимый интервал времени для открытия или закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="59f0c-103">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="59f0c-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="59f0c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="59f0c-105">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="59f0c-105">\<client></span></span>  
<span data-ttu-id="59f0c-106">\<Конечная точка ></span><span class="sxs-lookup"><span data-stu-id="59f0c-106">\<endpoint></span></span>  
<span data-ttu-id="59f0c-107">\<узел ></span><span class="sxs-lookup"><span data-stu-id="59f0c-107">\<host></span></span>  
<span data-ttu-id="59f0c-108">\<время ожидания ></span><span class="sxs-lookup"><span data-stu-id="59f0c-108">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59f0c-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59f0c-109">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59f0c-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="59f0c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="59f0c-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="59f0c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59f0c-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="59f0c-112">Attributes</span></span>  
  
|<span data-ttu-id="59f0c-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="59f0c-113">Attribute</span></span>|<span data-ttu-id="59f0c-114">Описание</span><span class="sxs-lookup"><span data-stu-id="59f0c-114">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="59f0c-115">Значение <xref:System.TimeSpan>, которое задает временной интервал, выделенный для операции закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="59f0c-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="59f0c-116">Значение <xref:System.TimeSpan>, которое задает временной интервал, выделенный для операции открытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="59f0c-116">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59f0c-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="59f0c-117">Child Elements</span></span>  
 <span data-ttu-id="59f0c-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="59f0c-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59f0c-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="59f0c-119">Parent Elements</span></span>  
  
|<span data-ttu-id="59f0c-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="59f0c-120">Element</span></span>|<span data-ttu-id="59f0c-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="59f0c-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59f0c-122">\<узел ></span><span class="sxs-lookup"><span data-stu-id="59f0c-122">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="59f0c-123">Элемент конфигурации, который задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="59f0c-123">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="59f0c-124">См. также</span><span class="sxs-lookup"><span data-stu-id="59f0c-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="59f0c-125">Размещение</span><span class="sxs-lookup"><span data-stu-id="59f0c-125">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
