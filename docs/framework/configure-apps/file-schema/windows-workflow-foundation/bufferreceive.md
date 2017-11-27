---
title: '&lt;bufferReceive&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 623ff924e171282c399bddcdc212a0606a3416d6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltbufferreceivegt"></a><span data-ttu-id="7b7fb-102">&lt;bufferReceive&gt;</span><span class="sxs-lookup"><span data-stu-id="7b7fb-102">&lt;bufferReceive&gt;</span></span>
<span data-ttu-id="7b7fb-103">Поведение, позволяющее службе рабочего процесса использовать обработку буфера получения, благодаря чему можно обрабатывать неупорядоченные сообщения.</span><span class="sxs-lookup"><span data-stu-id="7b7fb-103">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="7b7fb-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7b7fb-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7b7fb-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="7b7fb-105">\<behaviors></span></span>  
<span data-ttu-id="7b7fb-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="7b7fb-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="7b7fb-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="7b7fb-107">\<behavior></span></span>  
<span data-ttu-id="7b7fb-108">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="7b7fb-108">\<bufferReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b7fb-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b7fb-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b7fb-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7b7fb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7b7fb-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7b7fb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b7fb-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7b7fb-112">Attributes</span></span>  
  
|<span data-ttu-id="7b7fb-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7b7fb-113">Attribute</span></span>|<span data-ttu-id="7b7fb-114">Описание</span><span class="sxs-lookup"><span data-stu-id="7b7fb-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7b7fb-115">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="7b7fb-115">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="7b7fb-116">Целочисленное значение, указывающее максимальное число отложенных сообщений для каждого канала.</span><span class="sxs-lookup"><span data-stu-id="7b7fb-116">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="7b7fb-117">Значение по умолчанию — 512.</span><span class="sxs-lookup"><span data-stu-id="7b7fb-117">The default value is 512.</span></span> <span data-ttu-id="7b7fb-118">Это свойство ограничивает число внеочередных сообщений, которые могут быть получены службой рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="7b7fb-118">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7b7fb-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7b7fb-119">Child Elements</span></span>  
 <span data-ttu-id="7b7fb-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7b7fb-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7b7fb-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7b7fb-121">Parent Elements</span></span>  
  
|<span data-ttu-id="7b7fb-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="7b7fb-122">Element</span></span>|<span data-ttu-id="7b7fb-123">Описание</span><span class="sxs-lookup"><span data-stu-id="7b7fb-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7b7fb-124">\<поведение > из \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="7b7fb-124">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="7b7fb-125">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="7b7fb-125">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7b7fb-126">См. также</span><span class="sxs-lookup"><span data-stu-id="7b7fb-126">See Also</span></span>  
<!-- <xref:System.ServiceModel.Activities.Description.BufferReceiveServiceBehavior>  -->
 <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
