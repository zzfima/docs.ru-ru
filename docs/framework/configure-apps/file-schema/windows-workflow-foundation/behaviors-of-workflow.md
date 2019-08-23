---
title: <behaviors>рабочего процесса
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 7dd3b0b20c9d7accd80a85b3693e67ffc9b729e5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945994"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="c6037-102">\<> поведения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="c6037-102">\<behaviors> of workflow</span></span>
<span data-ttu-id="c6037-103">Этот элемент содержит коллекцию **serviceBehaviors** .</span><span class="sxs-lookup"><span data-stu-id="c6037-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="c6037-104">Каждый элемент в коллекции определяет элементы поведения, используемые службами рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="c6037-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="c6037-105">Каждый элемент поведения определяется с помощью уникального атрибута **имени** .</span><span class="sxs-lookup"><span data-stu-id="c6037-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
 <span data-ttu-id="c6037-106">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c6037-106">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6037-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6037-107">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6037-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c6037-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c6037-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c6037-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6037-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c6037-110">Attributes</span></span>  
 <span data-ttu-id="c6037-111">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="c6037-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c6037-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c6037-112">Child Elements</span></span>  
  
|<span data-ttu-id="c6037-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="c6037-113">Element</span></span>|<span data-ttu-id="c6037-114">Описание</span><span class="sxs-lookup"><span data-stu-id="c6037-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6037-115">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="c6037-115">\<serviceBehaviors></span></span>](servicebehaviors-of-workflow.md)|<span data-ttu-id="c6037-116">В данном разделе конфигурации представлены все поведения, определенные для конкретной службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="c6037-116">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c6037-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c6037-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c6037-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="c6037-118">Element</span></span>|<span data-ttu-id="c6037-119">Описание</span><span class="sxs-lookup"><span data-stu-id="c6037-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6037-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c6037-120">\<system.serviceModel></span></span>](../wcf/system-servicemodel.md)|<span data-ttu-id="c6037-121">Корневой элемент всех элементов конфигурации рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="c6037-121">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c6037-122">См. также</span><span class="sxs-lookup"><span data-stu-id="c6037-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="c6037-123">Настройка и расширение среды выполнения с помощью поведений</span><span class="sxs-lookup"><span data-stu-id="c6037-123">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
