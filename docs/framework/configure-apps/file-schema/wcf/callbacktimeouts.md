---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: e1b40718638ded54e59743730159ea6e65a51a57
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398186"
---
# <a name="callbacktimeouts"></a><span data-ttu-id="2f668-101">\<Каллбакктимеаутс ></span><span class="sxs-lookup"><span data-stu-id="2f668-101">\<callbackTimeouts></span></span>
<span data-ttu-id="2f668-102">Задает значение времени ожидания при потоке транзакций от сервера к клиенту в сценарии с дуплексным контрактом обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="2f668-102">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
<span data-ttu-id="2f668-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2f668-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2f668-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2f668-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2f668-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2f668-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="2f668-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2f668-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="2f668-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2f668-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="2f668-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Каллбакктимеаутс >**</span><span class="sxs-lookup"><span data-stu-id="2f668-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackTimeOuts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f668-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f668-109">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="2f668-110">Тип</span><span class="sxs-lookup"><span data-stu-id="2f668-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f668-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2f668-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2f668-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2f668-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f668-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2f668-113">Attributes</span></span>  
  
|<span data-ttu-id="2f668-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2f668-114">Attribute</span></span>|<span data-ttu-id="2f668-115">Описание</span><span class="sxs-lookup"><span data-stu-id="2f668-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="2f668-116">Значение <xref:System.TimeSpan>, задающее интервал времени, в течение которого транзакции должны завершаться или автоматически прерываться.</span><span class="sxs-lookup"><span data-stu-id="2f668-116">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="2f668-117">Значение по умолчанию — "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="2f668-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f668-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2f668-118">Child Elements</span></span>  
 <span data-ttu-id="2f668-119">Нет.</span><span class="sxs-lookup"><span data-stu-id="2f668-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2f668-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2f668-120">Parent Elements</span></span>  
  
|<span data-ttu-id="2f668-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="2f668-121">Element</span></span>|<span data-ttu-id="2f668-122">Описание</span><span class="sxs-lookup"><span data-stu-id="2f668-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f668-123">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="2f668-123">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="2f668-124">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="2f668-124">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2f668-125">См. также</span><span class="sxs-lookup"><span data-stu-id="2f668-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
