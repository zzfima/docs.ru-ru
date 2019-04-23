---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b6ae5faa2dd2ffef9669a0245a75227b0f669cf7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59118070"
---
# <a name="timeouts"></a><span data-ttu-id="392cb-101">\<время ожидания ></span><span class="sxs-lookup"><span data-stu-id="392cb-101">\<timeOuts></span></span>
<span data-ttu-id="392cb-102">Элемент конфигурации, который задает допустимый интервал времени для открытия или закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="392cb-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="392cb-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="392cb-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="392cb-104">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="392cb-104">\<client></span></span>  
<span data-ttu-id="392cb-105">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="392cb-105">\<endpoint></span></span>  
<span data-ttu-id="392cb-106">\<узел ></span><span class="sxs-lookup"><span data-stu-id="392cb-106">\<host></span></span>  
<span data-ttu-id="392cb-107">\<время ожидания ></span><span class="sxs-lookup"><span data-stu-id="392cb-107">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="392cb-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="392cb-108">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="392cb-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="392cb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="392cb-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="392cb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="392cb-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="392cb-111">Attributes</span></span>  
  
|<span data-ttu-id="392cb-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="392cb-112">Attribute</span></span>|<span data-ttu-id="392cb-113">Описание</span><span class="sxs-lookup"><span data-stu-id="392cb-113">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="392cb-114">Значение <xref:System.TimeSpan>, которое задает временной интервал, выделенный для операции закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="392cb-114">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="392cb-115">Значение <xref:System.TimeSpan>, которое задает временной интервал, выделенный для операции открытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="392cb-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="392cb-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="392cb-116">Child Elements</span></span>  
 <span data-ttu-id="392cb-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="392cb-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="392cb-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="392cb-118">Parent Elements</span></span>  
  
|<span data-ttu-id="392cb-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="392cb-119">Element</span></span>|<span data-ttu-id="392cb-120">Описание</span><span class="sxs-lookup"><span data-stu-id="392cb-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="392cb-121">\<узел ></span><span class="sxs-lookup"><span data-stu-id="392cb-121">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="392cb-122">Элемент конфигурации, который задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="392cb-122">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="392cb-123">См. также</span><span class="sxs-lookup"><span data-stu-id="392cb-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="392cb-124">Размещение</span><span class="sxs-lookup"><span data-stu-id="392cb-124">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
