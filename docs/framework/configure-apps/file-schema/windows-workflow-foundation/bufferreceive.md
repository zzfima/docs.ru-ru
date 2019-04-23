---
title: <bufferReceive>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: 360d26fda964fa33640e833ad22dab7e06e153f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203162"
---
# <a name="bufferreceive"></a><span data-ttu-id="a1174-101">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="a1174-101">\<bufferReceive></span></span>
<span data-ttu-id="a1174-102">Поведение, позволяющее службе рабочего процесса использовать обработку буфера получения, благодаря чему можно обрабатывать неупорядоченные сообщения.</span><span class="sxs-lookup"><span data-stu-id="a1174-102">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="a1174-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a1174-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="a1174-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="a1174-104">\<behaviors></span></span>  
<span data-ttu-id="a1174-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a1174-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="a1174-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="a1174-106">\<behavior></span></span>  
<span data-ttu-id="a1174-107">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="a1174-107">\<bufferReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1174-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a1174-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1174-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a1174-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a1174-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a1174-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1174-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a1174-111">Attributes</span></span>  
  
|<span data-ttu-id="a1174-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a1174-112">Attribute</span></span>|<span data-ttu-id="a1174-113">Описание</span><span class="sxs-lookup"><span data-stu-id="a1174-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a1174-114">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="a1174-114">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="a1174-115">Целочисленное значение, указывающее максимальное число отложенных сообщений для каждого канала.</span><span class="sxs-lookup"><span data-stu-id="a1174-115">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="a1174-116">Значение по умолчанию — 512.</span><span class="sxs-lookup"><span data-stu-id="a1174-116">The default value is 512.</span></span> <span data-ttu-id="a1174-117">Это свойство ограничивает число внеочередных сообщений, которые могут быть получены службой рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="a1174-117">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1174-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a1174-118">Child Elements</span></span>  
 <span data-ttu-id="a1174-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a1174-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a1174-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a1174-120">Parent Elements</span></span>  
  
|<span data-ttu-id="a1174-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="a1174-121">Element</span></span>|<span data-ttu-id="a1174-122">Описание</span><span class="sxs-lookup"><span data-stu-id="a1174-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a1174-123">\<поведение > из \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a1174-123">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="a1174-124">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="a1174-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a1174-125">См. также</span><span class="sxs-lookup"><span data-stu-id="a1174-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.BufferedReceiveServiceBehavior>
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
