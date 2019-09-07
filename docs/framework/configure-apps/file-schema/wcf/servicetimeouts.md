---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 801a7aaf1f0d0fa267fa8cca3d2e7fd02919c475
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399552"
---
# <a name="servicetimeouts"></a><span data-ttu-id="b00f7-101">\<Сервицетимеаутс ></span><span class="sxs-lookup"><span data-stu-id="b00f7-101">\<serviceTimeouts></span></span>
<span data-ttu-id="b00f7-102">Задает время ожидания для службы.</span><span class="sxs-lookup"><span data-stu-id="b00f7-102">Specifies the timeout for a service.</span></span>  
  
<span data-ttu-id="b00f7-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b00f7-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b00f7-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b00f7-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b00f7-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b00f7-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="b00f7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b00f7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="b00f7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b00f7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="b00f7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Сервицетимеаутс >**</span><span class="sxs-lookup"><span data-stu-id="b00f7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTimeouts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b00f7-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b00f7-109">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="b00f7-110">Тип</span><span class="sxs-lookup"><span data-stu-id="b00f7-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b00f7-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b00f7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b00f7-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b00f7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b00f7-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b00f7-113">Attributes</span></span>  
  
|<span data-ttu-id="b00f7-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b00f7-114">Attribute</span></span>|<span data-ttu-id="b00f7-115">Описание</span><span class="sxs-lookup"><span data-stu-id="b00f7-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="b00f7-116">Значение <xref:System.TimeSpan>, задающее интервал времени, в течение которого транзакция должна дойти от клиента до сервера.</span><span class="sxs-lookup"><span data-stu-id="b00f7-116">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="b00f7-117">Значение по умолчанию — "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="b00f7-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b00f7-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b00f7-118">Child Elements</span></span>  
 <span data-ttu-id="b00f7-119">Нет.</span><span class="sxs-lookup"><span data-stu-id="b00f7-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b00f7-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b00f7-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b00f7-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="b00f7-121">Element</span></span>|<span data-ttu-id="b00f7-122">Описание</span><span class="sxs-lookup"><span data-stu-id="b00f7-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b00f7-123">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="b00f7-123">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="b00f7-124">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="b00f7-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b00f7-125">См. также</span><span class="sxs-lookup"><span data-stu-id="b00f7-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
