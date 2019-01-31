---
title: <behaviors> рабочего процесса
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: e61a2078c5989a3b100e77e6b2f753b0ee5dd934
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271798"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="077c8-102">\<варианты поведения > рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="077c8-102">\<behaviors> of workflow</span></span>
<span data-ttu-id="077c8-103">Этот элемент содержит **serviceBehaviors** коллекции.</span><span class="sxs-lookup"><span data-stu-id="077c8-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="077c8-104">Каждый элемент в коллекции определяет элементы поведения, используемые службами рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="077c8-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="077c8-105">Каждый элемент поведения идентифицируется по уникальному **имя** атрибута.</span><span class="sxs-lookup"><span data-stu-id="077c8-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
 <span data-ttu-id="077c8-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="077c8-106">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="077c8-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="077c8-107">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="077c8-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="077c8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="077c8-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="077c8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="077c8-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="077c8-110">Attributes</span></span>  
 <span data-ttu-id="077c8-111">Нет</span><span class="sxs-lookup"><span data-stu-id="077c8-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="077c8-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="077c8-112">Child Elements</span></span>  
  
|<span data-ttu-id="077c8-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="077c8-113">Element</span></span>|<span data-ttu-id="077c8-114">Описание</span><span class="sxs-lookup"><span data-stu-id="077c8-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="077c8-115">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="077c8-115">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="077c8-116">В данном разделе конфигурации представлены все поведения, определенные для конкретной службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="077c8-116">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="077c8-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="077c8-117">Parent Elements</span></span>  
  
|<span data-ttu-id="077c8-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="077c8-118">Element</span></span>|<span data-ttu-id="077c8-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="077c8-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="077c8-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="077c8-120">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="077c8-121">Корневой элемент всех элементов конфигурации рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="077c8-121">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="077c8-122">См. также</span><span class="sxs-lookup"><span data-stu-id="077c8-122">See also</span></span>
- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="077c8-123">Настройка и расширение среды выполнения с помощью поведений</span><span class="sxs-lookup"><span data-stu-id="077c8-123">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
