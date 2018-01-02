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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5b5b6176e7c5b982bc9f41b13c669af104bf784f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltbufferreceivegt"></a><span data-ttu-id="d5eca-102">&lt;bufferReceive&gt;</span><span class="sxs-lookup"><span data-stu-id="d5eca-102">&lt;bufferReceive&gt;</span></span>
<span data-ttu-id="d5eca-103">Поведение, позволяющее службе рабочего процесса использовать обработку буфера получения, благодаря чему можно обрабатывать неупорядоченные сообщения.</span><span class="sxs-lookup"><span data-stu-id="d5eca-103">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="d5eca-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d5eca-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d5eca-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="d5eca-105">\<behaviors></span></span>  
<span data-ttu-id="d5eca-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d5eca-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="d5eca-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="d5eca-107">\<behavior></span></span>  
<span data-ttu-id="d5eca-108">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="d5eca-108">\<bufferReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5eca-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5eca-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5eca-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d5eca-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d5eca-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d5eca-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5eca-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d5eca-112">Attributes</span></span>  
  
|<span data-ttu-id="d5eca-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d5eca-113">Attribute</span></span>|<span data-ttu-id="d5eca-114">Описание</span><span class="sxs-lookup"><span data-stu-id="d5eca-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d5eca-115">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="d5eca-115">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="d5eca-116">Целочисленное значение, указывающее максимальное число отложенных сообщений для каждого канала.</span><span class="sxs-lookup"><span data-stu-id="d5eca-116">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="d5eca-117">Значение по умолчанию — 512.</span><span class="sxs-lookup"><span data-stu-id="d5eca-117">The default value is 512.</span></span> <span data-ttu-id="d5eca-118">Это свойство ограничивает число внеочередных сообщений, которые могут быть получены службой рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d5eca-118">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d5eca-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d5eca-119">Child Elements</span></span>  
 <span data-ttu-id="d5eca-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d5eca-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d5eca-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d5eca-121">Parent Elements</span></span>  
  
|<span data-ttu-id="d5eca-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="d5eca-122">Element</span></span>|<span data-ttu-id="d5eca-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="d5eca-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5eca-124">\<поведение > из \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d5eca-124">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="d5eca-125">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="d5eca-125">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d5eca-126">См. также</span><span class="sxs-lookup"><span data-stu-id="d5eca-126">See Also</span></span>  
<!-- <xref:System.ServiceModel.Activities.Description.BufferReceiveServiceBehavior>  -->
 <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
