---
title: <bufferReceive>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: be5173ea43c6f7fca7180a311885a26c889b12db
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398831"
---
# <a name="bufferreceive"></a><span data-ttu-id="a1920-101">\<Буфферрецеиве ></span><span class="sxs-lookup"><span data-stu-id="a1920-101">\<bufferReceive></span></span>
<span data-ttu-id="a1920-102">Поведение, позволяющее службе рабочего процесса использовать обработку буфера получения, благодаря чему можно обрабатывать неупорядоченные сообщения.</span><span class="sxs-lookup"><span data-stu-id="a1920-102">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="a1920-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a1920-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a1920-104">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="a1920-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="a1920-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="a1920-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="a1920-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="a1920-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="a1920-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="a1920-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="a1920-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Буфферрецеиве >**</span><span class="sxs-lookup"><span data-stu-id="a1920-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bufferReceive>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1920-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a1920-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1920-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a1920-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a1920-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a1920-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1920-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a1920-112">Attributes</span></span>  
  
|<span data-ttu-id="a1920-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a1920-113">Attribute</span></span>|<span data-ttu-id="a1920-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a1920-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a1920-115">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="a1920-115">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="a1920-116">Целочисленное значение, указывающее максимальное число отложенных сообщений для каждого канала.</span><span class="sxs-lookup"><span data-stu-id="a1920-116">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="a1920-117">Значение по умолчанию — 512.</span><span class="sxs-lookup"><span data-stu-id="a1920-117">The default value is 512.</span></span> <span data-ttu-id="a1920-118">Это свойство ограничивает число внеочередных сообщений, которые могут быть получены службой рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="a1920-118">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1920-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a1920-119">Child Elements</span></span>  
 <span data-ttu-id="a1920-120">Нет.</span><span class="sxs-lookup"><span data-stu-id="a1920-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a1920-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a1920-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a1920-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="a1920-122">Element</span></span>|<span data-ttu-id="a1920-123">Описание</span><span class="sxs-lookup"><span data-stu-id="a1920-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a1920-124">\<> поведения > \<serviceBehaviors</span><span class="sxs-lookup"><span data-stu-id="a1920-124">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="a1920-125">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="a1920-125">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a1920-126">См. также</span><span class="sxs-lookup"><span data-stu-id="a1920-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.BufferedReceiveServiceBehavior>
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
