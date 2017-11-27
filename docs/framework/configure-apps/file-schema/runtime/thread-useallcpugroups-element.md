---
title: "&lt;Thread_UseAllCpuGroups&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 187e391acf3b80a5ae2dfe795c4a3b397af815ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltthreaduseallcpugroupsgt-element"></a><span data-ttu-id="79a30-102">&lt;Thread_UseAllCpuGroups&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="79a30-102">&lt;Thread_UseAllCpuGroups&gt; Element</span></span>
<span data-ttu-id="79a30-103">Указывает, распределяет ли среда выполнения управляемые потоки во всех группах ЦП.</span><span class="sxs-lookup"><span data-stu-id="79a30-103">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>  
  
 <span data-ttu-id="79a30-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="79a30-104">\<configuration></span></span>  
<span data-ttu-id="79a30-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="79a30-105">\<runtime></span></span>  
<span data-ttu-id="79a30-106"><Thread_UseAllCpuGroups></span><span class="sxs-lookup"><span data-stu-id="79a30-106"><Thread_UseAllCpuGroups></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79a30-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="79a30-107">Syntax</span></span>  
  
```xml
<Thread_UseAllCpuGroups    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79a30-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="79a30-108">Attributes and Elements</span></span>  
 <span data-ttu-id="79a30-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="79a30-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79a30-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="79a30-110">Attributes</span></span>  
  
|<span data-ttu-id="79a30-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="79a30-111">Attribute</span></span>|<span data-ttu-id="79a30-112">Описание</span><span class="sxs-lookup"><span data-stu-id="79a30-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="79a30-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="79a30-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="79a30-114">Указывает, распределяет ли среда выполнения управляемые потоки во всех группах ЦП.</span><span class="sxs-lookup"><span data-stu-id="79a30-114">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="79a30-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="79a30-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="79a30-116">Значение</span><span class="sxs-lookup"><span data-stu-id="79a30-116">Value</span></span>|<span data-ttu-id="79a30-117">Описание</span><span class="sxs-lookup"><span data-stu-id="79a30-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="79a30-118">Среда выполнения не распределяют управляемые потоки несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="79a30-118">The runtime does not distribute managed threads across multiple CPU groups.</span></span> <span data-ttu-id="79a30-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="79a30-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="79a30-120">Среда выполнения распределяет управляемые потоки несколько групп ЦП, если компьютер имеет несколько групп ЦП и [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) включен элемент.</span><span class="sxs-lookup"><span data-stu-id="79a30-120">The runtime distributes managed threads across multiple CPU groups, if the computer has multiple CPU groups and the [\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) element is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="79a30-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="79a30-121">Child Elements</span></span>  
 <span data-ttu-id="79a30-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="79a30-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="79a30-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="79a30-123">Parent Elements</span></span>  
  
|<span data-ttu-id="79a30-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="79a30-124">Element</span></span>|<span data-ttu-id="79a30-125">Описание</span><span class="sxs-lookup"><span data-stu-id="79a30-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="79a30-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="79a30-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="79a30-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="79a30-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79a30-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="79a30-128">Remarks</span></span>  
 <span data-ttu-id="79a30-129">Если компьютер имеет несколько групп ЦП, включение этого элемента заставляет среду выполнения для распространения управляемые потоки во всех группах ЦП.</span><span class="sxs-lookup"><span data-stu-id="79a30-129">When a computer has multiple CPU groups, enabling this element causes the runtime to distribute managed threads across all CPU groups.</span></span> <span data-ttu-id="79a30-130">Чтобы использовать эту функцию, необходимо также включить [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) элемент, который расширяет сбора мусора для всех групп, ЦП и учитывает все ядра при создании и балансировки кучи.</span><span class="sxs-lookup"><span data-stu-id="79a30-130">To use this feature, you must also enable the [\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) element, which extends garbage collection to all CPU groups and takes all cores into account when creating and balancing heaps.</span></span> <span data-ttu-id="79a30-131">Включение [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) элемента необходимо включить [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="79a30-131">Enabling the [\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) element requires enabling the [\<gcServer>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) element.</span></span> <span data-ttu-id="79a30-132">Если эти элементы не включены, включение `<Thread_UseAllCpuGroups>` элемент не оказывает влияния.</span><span class="sxs-lookup"><span data-stu-id="79a30-132">If these elements are not enabled, enabling the `<Thread_UseAllCpuGroups>` element has no effect.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79a30-133">Пример</span><span class="sxs-lookup"><span data-stu-id="79a30-133">Example</span></span>  
 <span data-ttu-id="79a30-134">Приведенный ниже показано, как включить поддержку несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="79a30-134">The following example shows how to enable support for multiple CPU groups.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Thread_UseAllCpuGroups enabled="true"/>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="79a30-135">См. также</span><span class="sxs-lookup"><span data-stu-id="79a30-135">See Also</span></span>  
 [<span data-ttu-id="79a30-136">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="79a30-136">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="79a30-137">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="79a30-137">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="79a30-138">\<GCCpuGroup > элемент</span><span class="sxs-lookup"><span data-stu-id="79a30-138">\<GCCpuGroup> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)
