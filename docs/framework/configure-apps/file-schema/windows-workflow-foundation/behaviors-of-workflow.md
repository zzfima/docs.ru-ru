---
title: <behaviors> рабочего процесса
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: b7c5cf93a82ac88c25f9c478ad52cf41eb6f6d65
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129211"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="c0d6f-102">\<варианты поведения > рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="c0d6f-102">\<behaviors> of workflow</span></span>
<span data-ttu-id="c0d6f-103">Этот элемент содержит **serviceBehaviors** коллекции.</span><span class="sxs-lookup"><span data-stu-id="c0d6f-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="c0d6f-104">Каждый элемент в коллекции определяет элементы поведения, используемые службами рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="c0d6f-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="c0d6f-105">Каждый элемент поведения идентифицируется по уникальному **имя** атрибута.</span><span class="sxs-lookup"><span data-stu-id="c0d6f-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
 <span data-ttu-id="c0d6f-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c0d6f-106">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0d6f-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0d6f-107">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0d6f-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c0d6f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c0d6f-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c0d6f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0d6f-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c0d6f-110">Attributes</span></span>  
 <span data-ttu-id="c0d6f-111">Нет</span><span class="sxs-lookup"><span data-stu-id="c0d6f-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c0d6f-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c0d6f-112">Child Elements</span></span>  
  
|<span data-ttu-id="c0d6f-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="c0d6f-113">Element</span></span>|<span data-ttu-id="c0d6f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="c0d6f-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0d6f-115">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="c0d6f-115">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="c0d6f-116">В данном разделе конфигурации представлены все поведения, определенные для конкретной службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="c0d6f-116">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c0d6f-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c0d6f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c0d6f-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="c0d6f-118">Element</span></span>|<span data-ttu-id="c0d6f-119">Описание</span><span class="sxs-lookup"><span data-stu-id="c0d6f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0d6f-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c0d6f-120">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="c0d6f-121">Корневой элемент всех элементов конфигурации рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="c0d6f-121">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c0d6f-122">См. также</span><span class="sxs-lookup"><span data-stu-id="c0d6f-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="c0d6f-123">Настройка и расширение среды выполнения с помощью поведений</span><span class="sxs-lookup"><span data-stu-id="c0d6f-123">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
