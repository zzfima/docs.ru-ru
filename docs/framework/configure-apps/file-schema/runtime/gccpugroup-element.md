---
title: Элемент <GCCpuGroup>
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee56b23b6d5fca6d0527d509c9b6a6fc6dd82336
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920786"
---
# <a name="gccpugroup-element"></a><span data-ttu-id="99da3-102">\<Элемент > Гккпуграуп</span><span class="sxs-lookup"><span data-stu-id="99da3-102">\<GCCpuGroup> Element</span></span>

<span data-ttu-id="99da3-103">Определяет, поддерживает ли сборка мусора несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="99da3-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>

<span data-ttu-id="99da3-104">\<> конфигурации </span><span class="sxs-lookup"><span data-stu-id="99da3-104">\<configuration></span></span>\
<span data-ttu-id="99da3-105">\<> среды выполнения </span><span class="sxs-lookup"><span data-stu-id="99da3-105">\<runtime></span></span>\
<span data-ttu-id="99da3-106">\<Гккпуграуп ></span><span class="sxs-lookup"><span data-stu-id="99da3-106">\<GCCpuGroup></span></span>

## <a name="syntax"></a><span data-ttu-id="99da3-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99da3-107">Syntax</span></span>

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="99da3-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="99da3-108">Attributes and Elements</span></span>

<span data-ttu-id="99da3-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="99da3-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="99da3-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="99da3-110">Attributes</span></span>

|<span data-ttu-id="99da3-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="99da3-111">Attribute</span></span>|<span data-ttu-id="99da3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="99da3-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="99da3-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="99da3-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="99da3-114">Определяет, поддерживает ли сборка мусора несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="99da3-114">Specifies whether garbage collection supports multiple CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="99da3-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="99da3-115">enabled Attribute</span></span>

|<span data-ttu-id="99da3-116">Значение</span><span class="sxs-lookup"><span data-stu-id="99da3-116">Value</span></span>|<span data-ttu-id="99da3-117">Описание</span><span class="sxs-lookup"><span data-stu-id="99da3-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="99da3-118">Сборка мусора не поддерживает несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="99da3-118">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="99da3-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="99da3-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="99da3-120">Сборка мусора поддерживает несколько групп ЦП, если включена сборка мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="99da3-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="99da3-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="99da3-121">Child Elements</span></span>

<span data-ttu-id="99da3-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="99da3-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="99da3-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="99da3-123">Parent Elements</span></span>

|<span data-ttu-id="99da3-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="99da3-124">Element</span></span>|<span data-ttu-id="99da3-125">Описание</span><span class="sxs-lookup"><span data-stu-id="99da3-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="99da3-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="99da3-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="99da3-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="99da3-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="99da3-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="99da3-128">Remarks</span></span>

<span data-ttu-id="99da3-129">Если на компьютере установлено несколько групп ЦП и включена сборка мусора сервера (см [ \<. элемент > gcServer](gcserver-element.md) ), включение этого элемента расширяет сбор мусора во всех группах ЦП и учитывает все ядра при создании и сбалансированные кучи.</span><span class="sxs-lookup"><span data-stu-id="99da3-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>

> [!NOTE]
> <span data-ttu-id="99da3-130">Этот элемент применяется только к потокам сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="99da3-130">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="99da3-131">Чтобы среда выполнения распространяла пользовательские потоки во всех группах ЦП, необходимо также включить [ \<элемент > Thread_UseAllCpuGroups](thread-useallcpugroups-element.md) .</span><span class="sxs-lookup"><span data-stu-id="99da3-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) element.</span></span>

## <a name="example"></a><span data-ttu-id="99da3-132">Пример</span><span class="sxs-lookup"><span data-stu-id="99da3-132">Example</span></span>

<span data-ttu-id="99da3-133">В следующем примере показано, как включить сбор мусора для нескольких групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="99da3-133">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="99da3-134">См. также</span><span class="sxs-lookup"><span data-stu-id="99da3-134">See also</span></span>

- [<span data-ttu-id="99da3-135">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="99da3-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="99da3-136">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="99da3-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="99da3-137">Отключение параллельной сборки мусора</span><span class="sxs-lookup"><span data-stu-id="99da3-137">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [<span data-ttu-id="99da3-138">Сборка мусора рабочей станции и сборка мусора сервера</span><span class="sxs-lookup"><span data-stu-id="99da3-138">Workstation and server garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
