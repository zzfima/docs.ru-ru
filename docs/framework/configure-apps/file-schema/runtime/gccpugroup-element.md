---
title: '&lt;GCCpuGroup&gt; элемент'
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25d083b730117a791fb8ab550b36f7b2e6c5f5be
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613717"
---
# <a name="ltgccpugroupgt-element"></a><span data-ttu-id="2649f-102">&lt;GCCpuGroup&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="2649f-102">&lt;GCCpuGroup&gt; Element</span></span>
<span data-ttu-id="2649f-103">Определяет, поддерживает ли сборка мусора несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="2649f-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>  
  
 <span data-ttu-id="2649f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2649f-104">\<configuration></span></span>  
<span data-ttu-id="2649f-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="2649f-105">\<runtime></span></span>  
<span data-ttu-id="2649f-106">\<GCCpuGroup ></span><span class="sxs-lookup"><span data-stu-id="2649f-106">\<GCCpuGroup></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2649f-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2649f-107">Syntax</span></span>  
  
```xml  
<GCCpuGroup    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2649f-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2649f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2649f-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2649f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2649f-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2649f-110">Attributes</span></span>  
  
|<span data-ttu-id="2649f-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2649f-111">Attribute</span></span>|<span data-ttu-id="2649f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="2649f-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="2649f-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="2649f-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="2649f-114">Определяет, поддерживает ли сборка мусора несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="2649f-114">Specifies whether garbage collection supports multiple CPU groups.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="2649f-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="2649f-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="2649f-116">Значение</span><span class="sxs-lookup"><span data-stu-id="2649f-116">Value</span></span>|<span data-ttu-id="2649f-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="2649f-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="2649f-118">Сборка мусора не поддерживает несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="2649f-118">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="2649f-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2649f-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="2649f-120">Сборка мусора поддерживает несколько групп ЦП, если включена серверная сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="2649f-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2649f-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2649f-121">Child Elements</span></span>  
 <span data-ttu-id="2649f-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2649f-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2649f-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2649f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="2649f-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="2649f-124">Element</span></span>|<span data-ttu-id="2649f-125">Описание:</span><span class="sxs-lookup"><span data-stu-id="2649f-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2649f-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2649f-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="2649f-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="2649f-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2649f-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="2649f-128">Remarks</span></span>  
 <span data-ttu-id="2649f-129">Когда компьютер имеет несколько групп ЦП и сборка мусора сервера включена (см. в разделе [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) элемент), включение этого элемента расширяет сбор мусора во всех группах ЦП и использует все ядра в Учетная запись, при создании и балансировки куч.</span><span class="sxs-lookup"><span data-stu-id="2649f-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2649f-130">Этот элемент применяется только к потоки сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="2649f-130">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="2649f-131">Чтобы включить выполнение распределенного пользовательские потоки во всех группах ЦП, необходимо также включить [< Thread_UseAllCpuGroups >](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="2649f-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [<Thread_UseAllCpuGroups>](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2649f-132">Пример</span><span class="sxs-lookup"><span data-stu-id="2649f-132">Example</span></span>  
 <span data-ttu-id="2649f-133">В следующем примере показано включение сбора мусора для нескольких групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="2649f-133">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2649f-134">См. также</span><span class="sxs-lookup"><span data-stu-id="2649f-134">See Also</span></span>  
- [<span data-ttu-id="2649f-135">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="2649f-135">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [<span data-ttu-id="2649f-136">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="2649f-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="2649f-137">Практическое руководство. Отключение параллельной сборки мусора</span><span class="sxs-lookup"><span data-stu-id="2649f-137">How to: Disable Concurrent Garbage Collection</span></span>](https://msdn.microsoft.com/library/ba2c6c67-5778-497c-9fac-5f793b5500c7)  
- [<span data-ttu-id="2649f-138">Сборка мусора рабочей станции и сборка мусора сервера</span><span class="sxs-lookup"><span data-stu-id="2649f-138">Workstation and server garbage collection</span></span>](../../../../../docs/standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
