---
title: Элемент <Thread_UseAllCpuGroups>
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9758e009e012c8af5f5f7bd19dcd21f34b8c7d96
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2019
ms.locfileid: "66689738"
---
# <a name="threaduseallcpugroups-element"></a><span data-ttu-id="53b39-102">\<Thread_UseAllCpuGroups > элемент</span><span class="sxs-lookup"><span data-stu-id="53b39-102">\<Thread_UseAllCpuGroups> Element</span></span>

<span data-ttu-id="53b39-103">Указывает, распределяет ли среда выполнения управляемые потоки во всех группах ЦП.</span><span class="sxs-lookup"><span data-stu-id="53b39-103">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>

<span data-ttu-id="53b39-104">\<Конфигурация > \\</span><span class="sxs-lookup"><span data-stu-id="53b39-104">\<configuration>\\</span></span>
<span data-ttu-id="53b39-105">\<Среда выполнения > \\</span><span class="sxs-lookup"><span data-stu-id="53b39-105">\<runtime>\\</span></span>
<span data-ttu-id="53b39-106">\<Thread_UseAllCpuGroups></span><span class="sxs-lookup"><span data-stu-id="53b39-106">\<Thread_UseAllCpuGroups></span></span>

## <a name="syntax"></a><span data-ttu-id="53b39-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="53b39-107">Syntax</span></span>

```xml
<Thread_UseAllCpuGroups
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="53b39-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="53b39-108">Attributes and Elements</span></span>

<span data-ttu-id="53b39-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="53b39-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="53b39-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="53b39-110">Attributes</span></span>

|<span data-ttu-id="53b39-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="53b39-111">Attribute</span></span>|<span data-ttu-id="53b39-112">Описание</span><span class="sxs-lookup"><span data-stu-id="53b39-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="53b39-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="53b39-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="53b39-114">Указывает, распределяет ли среда выполнения управляемые потоки во всех группах ЦП.</span><span class="sxs-lookup"><span data-stu-id="53b39-114">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="53b39-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="53b39-115">enabled Attribute</span></span>

|<span data-ttu-id="53b39-116">Значение</span><span class="sxs-lookup"><span data-stu-id="53b39-116">Value</span></span>|<span data-ttu-id="53b39-117">Описание</span><span class="sxs-lookup"><span data-stu-id="53b39-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="53b39-118">Среда выполнения не распространяет управляемые потоки по нескольким группам ЦП.</span><span class="sxs-lookup"><span data-stu-id="53b39-118">The runtime does not distribute managed threads across multiple CPU groups.</span></span> <span data-ttu-id="53b39-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="53b39-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="53b39-120">Среда выполнения распространяет управляемые потоки по нескольким группам ЦП, если компьютер имеет несколько групп ЦП и [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) включен элемент.</span><span class="sxs-lookup"><span data-stu-id="53b39-120">The runtime distributes managed threads across multiple CPU groups, if the computer has multiple CPU groups and the [\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) element is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="53b39-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="53b39-121">Child Elements</span></span>

<span data-ttu-id="53b39-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="53b39-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="53b39-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="53b39-123">Parent Elements</span></span>

|<span data-ttu-id="53b39-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="53b39-124">Element</span></span>|<span data-ttu-id="53b39-125">Описание</span><span class="sxs-lookup"><span data-stu-id="53b39-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="53b39-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="53b39-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="53b39-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="53b39-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="53b39-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="53b39-128">Remarks</span></span>

<span data-ttu-id="53b39-129">Если компьютер имеет несколько групп ЦП, позволяя причины этого элемента выполнение распределенного управляемые потоки во всех группах ЦП.</span><span class="sxs-lookup"><span data-stu-id="53b39-129">When a computer has multiple CPU groups, enabling this element causes the runtime to distribute managed threads across all CPU groups.</span></span> <span data-ttu-id="53b39-130">Чтобы использовать эту функцию, необходимо также включить [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) элемент, который учитывает все ядра во время создания и распределения куч и расширяет их возможности сбора мусора для всех групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="53b39-130">To use this feature, you must also enable the [\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) element, which extends garbage collection to all CPU groups and takes all cores into account when creating and balancing heaps.</span></span> <span data-ttu-id="53b39-131">Включение [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) элемент требует включения [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="53b39-131">Enabling the [\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) element requires enabling the [\<gcServer>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) element.</span></span> <span data-ttu-id="53b39-132">Если эти элементы не включены, включение `<Thread_UseAllCpuGroups>` элемент не оказывает влияния.</span><span class="sxs-lookup"><span data-stu-id="53b39-132">If these elements are not enabled, enabling the `<Thread_UseAllCpuGroups>` element has no effect.</span></span>

## <a name="example"></a><span data-ttu-id="53b39-133">Пример</span><span class="sxs-lookup"><span data-stu-id="53b39-133">Example</span></span>

<span data-ttu-id="53b39-134">Приведенный ниже показано, как включить поддержку нескольких групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="53b39-134">The following example shows how to enable support for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <Thread_UseAllCpuGroups enabled="true"/>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="53b39-135">См. также</span><span class="sxs-lookup"><span data-stu-id="53b39-135">See also</span></span>

- [<span data-ttu-id="53b39-136">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="53b39-136">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="53b39-137">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="53b39-137">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="53b39-138">\<GCCpuGroup > элемент</span><span class="sxs-lookup"><span data-stu-id="53b39-138">\<GCCpuGroup> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)
