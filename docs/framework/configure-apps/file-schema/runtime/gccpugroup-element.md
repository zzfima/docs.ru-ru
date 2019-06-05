---
title: Элемент <GCCpuGroup>
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1251f286a4e6168ef1d18b05288e0c5f353ad828
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2019
ms.locfileid: "66689880"
---
# <a name="gccpugroup-element"></a><span data-ttu-id="d6950-102">\<GCCpuGroup > элемент</span><span class="sxs-lookup"><span data-stu-id="d6950-102">\<GCCpuGroup> Element</span></span>

<span data-ttu-id="d6950-103">Определяет, поддерживает ли сборка мусора несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="d6950-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>

<span data-ttu-id="d6950-104">\<Конфигурация > \\</span><span class="sxs-lookup"><span data-stu-id="d6950-104">\<configuration>\\</span></span>
<span data-ttu-id="d6950-105">\<Среда выполнения > \\</span><span class="sxs-lookup"><span data-stu-id="d6950-105">\<runtime>\\</span></span>
<span data-ttu-id="d6950-106">\<GCCpuGroup></span><span class="sxs-lookup"><span data-stu-id="d6950-106">\<GCCpuGroup></span></span>

## <a name="syntax"></a><span data-ttu-id="d6950-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d6950-107">Syntax</span></span>

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d6950-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d6950-108">Attributes and Elements</span></span>

<span data-ttu-id="d6950-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d6950-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d6950-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d6950-110">Attributes</span></span>

|<span data-ttu-id="d6950-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d6950-111">Attribute</span></span>|<span data-ttu-id="d6950-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d6950-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="d6950-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d6950-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="d6950-114">Определяет, поддерживает ли сборка мусора несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="d6950-114">Specifies whether garbage collection supports multiple CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="d6950-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="d6950-115">enabled Attribute</span></span>

|<span data-ttu-id="d6950-116">Значение</span><span class="sxs-lookup"><span data-stu-id="d6950-116">Value</span></span>|<span data-ttu-id="d6950-117">Описание</span><span class="sxs-lookup"><span data-stu-id="d6950-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="d6950-118">Сборка мусора не поддерживает несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="d6950-118">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="d6950-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d6950-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="d6950-120">Сборка мусора поддерживает несколько групп ЦП, если включена серверная сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="d6950-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="d6950-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d6950-121">Child Elements</span></span>

<span data-ttu-id="d6950-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d6950-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d6950-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d6950-123">Parent Elements</span></span>

|<span data-ttu-id="d6950-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="d6950-124">Element</span></span>|<span data-ttu-id="d6950-125">Описание</span><span class="sxs-lookup"><span data-stu-id="d6950-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="d6950-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d6950-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="d6950-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="d6950-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d6950-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="d6950-128">Remarks</span></span>

<span data-ttu-id="d6950-129">Когда компьютер имеет несколько групп ЦП и сборка мусора сервера включена (см. в разделе [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) элемент), включение этого элемента расширяет сбор мусора во всех группах ЦП и использует все ядра в Учетная запись, при создании и балансировки куч.</span><span class="sxs-lookup"><span data-stu-id="d6950-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>

> [!NOTE]
> <span data-ttu-id="d6950-130">Этот элемент применяется только к потоки сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="d6950-130">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="d6950-131">Чтобы включить выполнение распределенного пользовательские потоки во всех группах ЦП, необходимо также включить [ \<Thread_UseAllCpuGroups >](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="d6950-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [\<Thread_UseAllCpuGroups>](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) element.</span></span>

## <a name="example"></a><span data-ttu-id="d6950-132">Пример</span><span class="sxs-lookup"><span data-stu-id="d6950-132">Example</span></span>

<span data-ttu-id="d6950-133">В следующем примере показано включение сбора мусора для нескольких групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="d6950-133">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="d6950-134">См. также</span><span class="sxs-lookup"><span data-stu-id="d6950-134">See also</span></span>

- [<span data-ttu-id="d6950-135">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="d6950-135">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="d6950-136">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="d6950-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="d6950-137">Отключение параллельной сборки мусора</span><span class="sxs-lookup"><span data-stu-id="d6950-137">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [<span data-ttu-id="d6950-138">Сборка мусора рабочей станции и сборка мусора сервера</span><span class="sxs-lookup"><span data-stu-id="d6950-138">Workstation and server garbage collection</span></span>](../../../../../docs/standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
