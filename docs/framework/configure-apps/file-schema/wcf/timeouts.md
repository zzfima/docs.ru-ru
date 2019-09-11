---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b9c67ac03f0eb73a2a4cdd43ab48fe12871a1cc3
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854964"
---
# <a name="timeouts"></a><span data-ttu-id="916c3-101">\<> времени ожидания</span><span class="sxs-lookup"><span data-stu-id="916c3-101">\<timeOuts></span></span>
<span data-ttu-id="916c3-102">Элемент конфигурации, который задает допустимый интервал времени для открытия или закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="916c3-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
<span data-ttu-id="916c3-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="916c3-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="916c3-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="916c3-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="916c3-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<службы >** ](services.md)</span><span class="sxs-lookup"><span data-stu-id="916c3-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="916c3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> службы**](service.md)</span><span class="sxs-lookup"><span data-stu-id="916c3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="916c3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> узла**](host.md)</span><span class="sxs-lookup"><span data-stu-id="916c3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)</span></span>\
<span data-ttu-id="916c3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> времени ожидания**</span><span class="sxs-lookup"><span data-stu-id="916c3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<timeOuts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="916c3-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="916c3-109">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="916c3-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="916c3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="916c3-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="916c3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="916c3-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="916c3-112">Attributes</span></span>  
  
|<span data-ttu-id="916c3-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="916c3-113">Attribute</span></span>|<span data-ttu-id="916c3-114">Описание</span><span class="sxs-lookup"><span data-stu-id="916c3-114">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="916c3-115">Значение <xref:System.TimeSpan>, которое задает временной интервал, выделенный для операции закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="916c3-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="916c3-116">Значение <xref:System.TimeSpan>, которое задает временной интервал, выделенный для операции открытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="916c3-116">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="916c3-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="916c3-117">Child Elements</span></span>  
 <span data-ttu-id="916c3-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="916c3-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="916c3-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="916c3-119">Parent Elements</span></span>  
  
|<span data-ttu-id="916c3-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="916c3-120">Element</span></span>|<span data-ttu-id="916c3-121">Описание</span><span class="sxs-lookup"><span data-stu-id="916c3-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="916c3-122">\<> узла</span><span class="sxs-lookup"><span data-stu-id="916c3-122">\<host></span></span>](host.md)|<span data-ttu-id="916c3-123">Элемент конфигурации, который задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="916c3-123">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="916c3-124">См. также</span><span class="sxs-lookup"><span data-stu-id="916c3-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="916c3-125">Размещение</span><span class="sxs-lookup"><span data-stu-id="916c3-125">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
