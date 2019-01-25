---
title: '&lt;bufferReceive&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: 507d58f852544c0eadcefaf997b2345d5e123cfa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607518"
---
# <a name="ltbufferreceivegt"></a><span data-ttu-id="97e5b-102">&lt;bufferReceive&gt;</span><span class="sxs-lookup"><span data-stu-id="97e5b-102">&lt;bufferReceive&gt;</span></span>
<span data-ttu-id="97e5b-103">Поведение, позволяющее службе рабочего процесса использовать обработку буфера получения, благодаря чему можно обрабатывать неупорядоченные сообщения.</span><span class="sxs-lookup"><span data-stu-id="97e5b-103">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="97e5b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="97e5b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="97e5b-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="97e5b-105">\<behaviors></span></span>  
<span data-ttu-id="97e5b-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="97e5b-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="97e5b-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="97e5b-107">\<behavior></span></span>  
<span data-ttu-id="97e5b-108">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="97e5b-108">\<bufferReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97e5b-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="97e5b-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97e5b-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="97e5b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="97e5b-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="97e5b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97e5b-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="97e5b-112">Attributes</span></span>  
  
|<span data-ttu-id="97e5b-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="97e5b-113">Attribute</span></span>|<span data-ttu-id="97e5b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="97e5b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="97e5b-115">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="97e5b-115">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="97e5b-116">Целочисленное значение, указывающее максимальное число отложенных сообщений для каждого канала.</span><span class="sxs-lookup"><span data-stu-id="97e5b-116">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="97e5b-117">Значение по умолчанию — 512.</span><span class="sxs-lookup"><span data-stu-id="97e5b-117">The default value is 512.</span></span> <span data-ttu-id="97e5b-118">Это свойство ограничивает число внеочередных сообщений, которые могут быть получены службой рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="97e5b-118">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="97e5b-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="97e5b-119">Child Elements</span></span>  
 <span data-ttu-id="97e5b-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="97e5b-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="97e5b-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="97e5b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="97e5b-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="97e5b-122">Element</span></span>|<span data-ttu-id="97e5b-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="97e5b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97e5b-124">\<поведение > из \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="97e5b-124">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="97e5b-125">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="97e5b-125">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="97e5b-126">См. также</span><span class="sxs-lookup"><span data-stu-id="97e5b-126">See also</span></span>
<!-- <xref:System.ServiceModel.Activities.Description.BufferReceiveServiceBehavior>  -->
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
