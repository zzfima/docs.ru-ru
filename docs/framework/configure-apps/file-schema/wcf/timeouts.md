---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b159488efa2a80a9dea625e4c6dfe2f215dfc457
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939187"
---
# <a name="timeouts"></a><span data-ttu-id="6ba83-101">\<> времени ожидания</span><span class="sxs-lookup"><span data-stu-id="6ba83-101">\<timeOuts></span></span>
<span data-ttu-id="6ba83-102">Элемент конфигурации, который задает допустимый интервал времени для открытия или закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="6ba83-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="6ba83-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6ba83-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="6ba83-104">\<> клиента</span><span class="sxs-lookup"><span data-stu-id="6ba83-104">\<client></span></span>  
<span data-ttu-id="6ba83-105">\<> конечной точки</span><span class="sxs-lookup"><span data-stu-id="6ba83-105">\<endpoint></span></span>  
<span data-ttu-id="6ba83-106">\<> узла</span><span class="sxs-lookup"><span data-stu-id="6ba83-106">\<host></span></span>  
<span data-ttu-id="6ba83-107">\<> времени ожидания</span><span class="sxs-lookup"><span data-stu-id="6ba83-107">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ba83-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6ba83-108">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ba83-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6ba83-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6ba83-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6ba83-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6ba83-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6ba83-111">Attributes</span></span>  
  
|<span data-ttu-id="6ba83-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6ba83-112">Attribute</span></span>|<span data-ttu-id="6ba83-113">Описание</span><span class="sxs-lookup"><span data-stu-id="6ba83-113">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="6ba83-114">Значение <xref:System.TimeSpan>, которое задает временной интервал, выделенный для операции закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="6ba83-114">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="6ba83-115">Значение <xref:System.TimeSpan>, которое задает временной интервал, выделенный для операции открытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="6ba83-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6ba83-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6ba83-116">Child Elements</span></span>  
 <span data-ttu-id="6ba83-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="6ba83-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6ba83-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6ba83-118">Parent Elements</span></span>  
  
|<span data-ttu-id="6ba83-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="6ba83-119">Element</span></span>|<span data-ttu-id="6ba83-120">Описание</span><span class="sxs-lookup"><span data-stu-id="6ba83-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6ba83-121">\<> узла</span><span class="sxs-lookup"><span data-stu-id="6ba83-121">\<host></span></span>](host.md)|<span data-ttu-id="6ba83-122">Элемент конфигурации, который задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="6ba83-122">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6ba83-123">См. также</span><span class="sxs-lookup"><span data-stu-id="6ba83-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="6ba83-124">Размещение</span><span class="sxs-lookup"><span data-stu-id="6ba83-124">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
