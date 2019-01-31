---
title: <bufferReceive>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: 6ed37d73440dac22288ae1da526d81b2d0b990a1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286628"
---
# <a name="bufferreceive"></a><span data-ttu-id="e7da1-101">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="e7da1-101">\<bufferReceive></span></span>
<span data-ttu-id="e7da1-102">Поведение, позволяющее службе рабочего процесса использовать обработку буфера получения, благодаря чему можно обрабатывать неупорядоченные сообщения.</span><span class="sxs-lookup"><span data-stu-id="e7da1-102">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="e7da1-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e7da1-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="e7da1-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="e7da1-104">\<behaviors></span></span>  
<span data-ttu-id="e7da1-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e7da1-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="e7da1-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="e7da1-106">\<behavior></span></span>  
<span data-ttu-id="e7da1-107">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="e7da1-107">\<bufferReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7da1-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7da1-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7da1-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e7da1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e7da1-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e7da1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7da1-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e7da1-111">Attributes</span></span>  
  
|<span data-ttu-id="e7da1-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e7da1-112">Attribute</span></span>|<span data-ttu-id="e7da1-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e7da1-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e7da1-114">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="e7da1-114">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="e7da1-115">Целочисленное значение, указывающее максимальное число отложенных сообщений для каждого канала.</span><span class="sxs-lookup"><span data-stu-id="e7da1-115">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="e7da1-116">Значение по умолчанию — 512.</span><span class="sxs-lookup"><span data-stu-id="e7da1-116">The default value is 512.</span></span> <span data-ttu-id="e7da1-117">Это свойство ограничивает число внеочередных сообщений, которые могут быть получены службой рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="e7da1-117">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e7da1-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e7da1-118">Child Elements</span></span>  
 <span data-ttu-id="e7da1-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e7da1-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e7da1-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e7da1-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e7da1-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="e7da1-121">Element</span></span>|<span data-ttu-id="e7da1-122">Описание</span><span class="sxs-lookup"><span data-stu-id="e7da1-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7da1-123">\<поведение > из \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e7da1-123">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="e7da1-124">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="e7da1-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e7da1-125">См. также</span><span class="sxs-lookup"><span data-stu-id="e7da1-125">See also</span></span>
<!-- <xref:System.ServiceModel.Activities.Description.BufferReceiveServiceBehavior>  -->
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
