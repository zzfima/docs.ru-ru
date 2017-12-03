---
title: "&lt;варианты поведения&gt; рабочего процесса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bffe7cbf3cadf072a8bab88555b069983d262e38
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltbehaviorsgt-of-workflow"></a><span data-ttu-id="f1a8b-102">&lt;варианты поведения&gt; рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="f1a8b-102">&lt;behaviors&gt; of workflow</span></span>
<span data-ttu-id="f1a8b-103">Этот элемент содержит **serviceBehaviors** коллекции.</span><span class="sxs-lookup"><span data-stu-id="f1a8b-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="f1a8b-104">Каждый элемент в коллекции определяет элементы поведения, используемые службами рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f1a8b-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="f1a8b-105">Каждый элемент поведения идентифицируется по уникальному **имя** атрибута.</span><span class="sxs-lookup"><span data-stu-id="f1a8b-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
 <span data-ttu-id="f1a8b-106">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f1a8b-106">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1a8b-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f1a8b-107">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1a8b-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f1a8b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f1a8b-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f1a8b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1a8b-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f1a8b-110">Attributes</span></span>  
 <span data-ttu-id="f1a8b-111">Нет</span><span class="sxs-lookup"><span data-stu-id="f1a8b-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f1a8b-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f1a8b-112">Child Elements</span></span>  
  
|<span data-ttu-id="f1a8b-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="f1a8b-113">Element</span></span>|<span data-ttu-id="f1a8b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="f1a8b-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1a8b-115">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="f1a8b-115">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="f1a8b-116">В данном разделе конфигурации представлены все поведения, определенные для конкретной службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f1a8b-116">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f1a8b-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f1a8b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f1a8b-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="f1a8b-118">Element</span></span>|<span data-ttu-id="f1a8b-119">Описание</span><span class="sxs-lookup"><span data-stu-id="f1a8b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1a8b-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f1a8b-120">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="f1a8b-121">Корневой элемент всех элементов конфигурации рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f1a8b-121">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f1a8b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="f1a8b-122">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>  
 [<span data-ttu-id="f1a8b-123">Настройка и расширение среды выполнения с помощью поведений</span><span class="sxs-lookup"><span data-stu-id="f1a8b-123">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
