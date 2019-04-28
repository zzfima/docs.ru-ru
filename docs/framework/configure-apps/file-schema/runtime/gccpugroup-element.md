---
title: Элемент <GCCpuGroup>
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85cfe57f7a3b8cfecfae4c4ae00efaea464e6120
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674094"
---
# <a name="gccpugroup-element"></a><span data-ttu-id="fea39-102">\<GCCpuGroup > элемент</span><span class="sxs-lookup"><span data-stu-id="fea39-102">\<GCCpuGroup> Element</span></span>
<span data-ttu-id="fea39-103">Определяет, поддерживает ли сборка мусора несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="fea39-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>  
  
 <span data-ttu-id="fea39-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="fea39-104">\<configuration></span></span>  
<span data-ttu-id="fea39-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="fea39-105">\<runtime></span></span>  
<span data-ttu-id="fea39-106">\<GCCpuGroup></span><span class="sxs-lookup"><span data-stu-id="fea39-106">\<GCCpuGroup></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fea39-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fea39-107">Syntax</span></span>  
  
```xml  
<GCCpuGroup    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fea39-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fea39-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fea39-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fea39-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fea39-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fea39-110">Attributes</span></span>  
  
|<span data-ttu-id="fea39-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fea39-111">Attribute</span></span>|<span data-ttu-id="fea39-112">Описание</span><span class="sxs-lookup"><span data-stu-id="fea39-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="fea39-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="fea39-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="fea39-114">Определяет, поддерживает ли сборка мусора несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="fea39-114">Specifies whether garbage collection supports multiple CPU groups.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="fea39-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="fea39-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="fea39-116">Значение</span><span class="sxs-lookup"><span data-stu-id="fea39-116">Value</span></span>|<span data-ttu-id="fea39-117">Описание</span><span class="sxs-lookup"><span data-stu-id="fea39-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="fea39-118">Сборка мусора не поддерживает несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="fea39-118">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="fea39-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fea39-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="fea39-120">Сборка мусора поддерживает несколько групп ЦП, если включена серверная сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="fea39-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fea39-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fea39-121">Child Elements</span></span>  
 <span data-ttu-id="fea39-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="fea39-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fea39-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fea39-123">Parent Elements</span></span>  
  
|<span data-ttu-id="fea39-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="fea39-124">Element</span></span>|<span data-ttu-id="fea39-125">Описание</span><span class="sxs-lookup"><span data-stu-id="fea39-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fea39-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fea39-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="fea39-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="fea39-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fea39-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="fea39-128">Remarks</span></span>  
 <span data-ttu-id="fea39-129">Когда компьютер имеет несколько групп ЦП и сборка мусора сервера включена (см. в разделе [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) элемент), включение этого элемента расширяет сбор мусора во всех группах ЦП и использует все ядра в Учетная запись, при создании и балансировки куч.</span><span class="sxs-lookup"><span data-stu-id="fea39-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fea39-130">Этот элемент применяется только к потоки сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="fea39-130">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="fea39-131">Чтобы включить выполнение распределенного пользовательские потоки во всех группах ЦП, необходимо также включить [< Thread_UseAllCpuGroups >](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="fea39-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [<Thread_UseAllCpuGroups>](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fea39-132">Пример</span><span class="sxs-lookup"><span data-stu-id="fea39-132">Example</span></span>  
 <span data-ttu-id="fea39-133">В следующем примере показано включение сбора мусора для нескольких групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="fea39-133">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fea39-134">См. также</span><span class="sxs-lookup"><span data-stu-id="fea39-134">See also</span></span>

- [<span data-ttu-id="fea39-135">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="fea39-135">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="fea39-136">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="fea39-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="fea39-137">Отключение параллельной сборки мусора</span><span class="sxs-lookup"><span data-stu-id="fea39-137">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [<span data-ttu-id="fea39-138">Сборка мусора рабочей станции и сборка мусора сервера</span><span class="sxs-lookup"><span data-stu-id="fea39-138">Workstation and server garbage collection</span></span>](../../../../../docs/standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
