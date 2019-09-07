---
title: <behaviors>рабочего процесса
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 05a15cdf5c043eb5d94b36028324310d2b7a8413
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398879"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="676fd-102">\<> поведения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="676fd-102">\<behaviors> of workflow</span></span>
<span data-ttu-id="676fd-103">Этот элемент содержит коллекцию **serviceBehaviors** .</span><span class="sxs-lookup"><span data-stu-id="676fd-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="676fd-104">Каждый элемент в коллекции определяет элементы поведения, используемые службами рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="676fd-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="676fd-105">Каждый элемент поведения определяется с помощью уникального атрибута **имени** .</span><span class="sxs-lookup"><span data-stu-id="676fd-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
<span data-ttu-id="676fd-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="676fd-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="676fd-107">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="676fd-107">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="676fd-108">&nbsp;&nbsp;&nbsp;&nbsp; **\<> поведения**</span><span class="sxs-lookup"><span data-stu-id="676fd-108">&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="676fd-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="676fd-109">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="676fd-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="676fd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="676fd-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="676fd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="676fd-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="676fd-112">Attributes</span></span>  
 <span data-ttu-id="676fd-113">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="676fd-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="676fd-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="676fd-114">Child Elements</span></span>  
  
|<span data-ttu-id="676fd-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="676fd-115">Element</span></span>|<span data-ttu-id="676fd-116">Описание</span><span class="sxs-lookup"><span data-stu-id="676fd-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="676fd-117">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="676fd-117">\<serviceBehaviors></span></span>](servicebehaviors-of-workflow.md)|<span data-ttu-id="676fd-118">В данном разделе конфигурации представлены все поведения, определенные для конкретной службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="676fd-118">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="676fd-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="676fd-119">Parent Elements</span></span>  
  
|<span data-ttu-id="676fd-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="676fd-120">Element</span></span>|<span data-ttu-id="676fd-121">Описание</span><span class="sxs-lookup"><span data-stu-id="676fd-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="676fd-122">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="676fd-122">\<system.serviceModel></span></span>](../wcf/system-servicemodel.md)|<span data-ttu-id="676fd-123">Корневой элемент всех элементов конфигурации рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="676fd-123">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="676fd-124">См. также</span><span class="sxs-lookup"><span data-stu-id="676fd-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="676fd-125">Настройка и расширение среды выполнения с помощью поведений</span><span class="sxs-lookup"><span data-stu-id="676fd-125">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
