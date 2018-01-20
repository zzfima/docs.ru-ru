---
title: "&lt;GCCpuGroup&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dcead28d7bf66e0626a0108015add4f22c5fa476
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="ltgccpugroupgt-element"></a><span data-ttu-id="73bf6-102">&lt;GCCpuGroup&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="73bf6-102">&lt;GCCpuGroup&gt; Element</span></span>
<span data-ttu-id="73bf6-103">Определяет, поддерживает ли сборка мусора несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="73bf6-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>  
  
 <span data-ttu-id="73bf6-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="73bf6-104">\<configuration></span></span>  
<span data-ttu-id="73bf6-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="73bf6-105">\<runtime></span></span>  
<span data-ttu-id="73bf6-106">\<GCCpuGroup></span><span class="sxs-lookup"><span data-stu-id="73bf6-106">\<GCCpuGroup></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73bf6-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="73bf6-107">Syntax</span></span>  
  
```xml  
<GCCpuGroup    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73bf6-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="73bf6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="73bf6-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="73bf6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73bf6-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="73bf6-110">Attributes</span></span>  
  
|<span data-ttu-id="73bf6-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="73bf6-111">Attribute</span></span>|<span data-ttu-id="73bf6-112">Описание</span><span class="sxs-lookup"><span data-stu-id="73bf6-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="73bf6-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="73bf6-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="73bf6-114">Определяет, поддерживает ли сборка мусора несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="73bf6-114">Specifies whether garbage collection supports multiple CPU groups.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="73bf6-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="73bf6-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="73bf6-116">Значение</span><span class="sxs-lookup"><span data-stu-id="73bf6-116">Value</span></span>|<span data-ttu-id="73bf6-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="73bf6-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="73bf6-118">Сборщик мусора не поддерживает несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="73bf6-118">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="73bf6-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="73bf6-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="73bf6-120">Сборщик мусора поддерживает несколько групп ЦП, если включена серверная сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="73bf6-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="73bf6-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="73bf6-121">Child Elements</span></span>  
 <span data-ttu-id="73bf6-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="73bf6-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="73bf6-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="73bf6-123">Parent Elements</span></span>  
  
|<span data-ttu-id="73bf6-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="73bf6-124">Element</span></span>|<span data-ttu-id="73bf6-125">Описание:</span><span class="sxs-lookup"><span data-stu-id="73bf6-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="73bf6-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="73bf6-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="73bf6-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="73bf6-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73bf6-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="73bf6-128">Remarks</span></span>  
 <span data-ttu-id="73bf6-129">Если компьютер имеет несколько групп ЦП и включена серверная сборка мусора (в разделе [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) элемент), включение этого элемента расширяет сбора мусора для всех групп ЦП и принимает все ядра в Учетная запись, при создании и балансировки кучи.</span><span class="sxs-lookup"><span data-stu-id="73bf6-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73bf6-130">Этот элемент применяется только к потоки сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="73bf6-130">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="73bf6-131">Чтобы включить распространение пользовательские потоки во всех группах ЦП в среде выполнения, необходимо также включить [< Thread_UseAllCpuGroups >](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="73bf6-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [<Thread_UseAllCpuGroups>](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73bf6-132">Пример</span><span class="sxs-lookup"><span data-stu-id="73bf6-132">Example</span></span>  
 <span data-ttu-id="73bf6-133">Приведенный ниже показано, как включить сбор мусора для несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="73bf6-133">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="73bf6-134">См. также</span><span class="sxs-lookup"><span data-stu-id="73bf6-134">See Also</span></span>  
 [<span data-ttu-id="73bf6-135">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="73bf6-135">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="73bf6-136">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="73bf6-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="73bf6-137">Как: отключить параллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="73bf6-137">How to: Disable Concurrent Garbage Collection</span></span>](http://msdn.microsoft.com/library/ba2c6c67-5778-497c-9fac-5f793b5500c7)  
 [<span data-ttu-id="73bf6-138">Сборка мусора рабочей станции и сервера</span><span class="sxs-lookup"><span data-stu-id="73bf6-138">Workstation and server garbage collection</span></span>](../../../../../docs/standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
