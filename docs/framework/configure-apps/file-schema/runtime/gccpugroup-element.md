---
title: Элемент <GCCpuGroup>
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: ae9c96c9d49cf3f6be94da3f77b91423cab12e0b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430478"
---
# <a name="gccpugroup-element"></a><span data-ttu-id="05c99-102">\<GCCpuGroup> Element</span><span class="sxs-lookup"><span data-stu-id="05c99-102">\<GCCpuGroup> Element</span></span>

<span data-ttu-id="05c99-103">Определяет, поддерживает ли сборка мусора несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="05c99-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>

<span data-ttu-id="05c99-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="05c99-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="05c99-105">&nbsp;&nbsp;[ **\<runtime>** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="05c99-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="05c99-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<GCCpuGroup>**</span><span class="sxs-lookup"><span data-stu-id="05c99-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="05c99-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05c99-107">Syntax</span></span>

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="05c99-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="05c99-108">Attributes and Elements</span></span>

<span data-ttu-id="05c99-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="05c99-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="05c99-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="05c99-110">Attributes</span></span>

|<span data-ttu-id="05c99-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="05c99-111">Attribute</span></span>|<span data-ttu-id="05c99-112">Описание</span><span class="sxs-lookup"><span data-stu-id="05c99-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="05c99-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="05c99-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="05c99-114">Определяет, поддерживает ли сборка мусора несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="05c99-114">Specifies whether garbage collection supports multiple CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="05c99-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="05c99-115">enabled Attribute</span></span>

|<span data-ttu-id="05c99-116">значения</span><span class="sxs-lookup"><span data-stu-id="05c99-116">Value</span></span>|<span data-ttu-id="05c99-117">Описание</span><span class="sxs-lookup"><span data-stu-id="05c99-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="05c99-118">Garbage collection does not support multiple CPU groups.</span><span class="sxs-lookup"><span data-stu-id="05c99-118">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="05c99-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="05c99-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="05c99-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span><span class="sxs-lookup"><span data-stu-id="05c99-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="05c99-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="05c99-121">Child Elements</span></span>

<span data-ttu-id="05c99-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="05c99-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="05c99-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="05c99-123">Parent Elements</span></span>

|<span data-ttu-id="05c99-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="05c99-124">Element</span></span>|<span data-ttu-id="05c99-125">Описание</span><span class="sxs-lookup"><span data-stu-id="05c99-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="05c99-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="05c99-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="05c99-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="05c99-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="05c99-128">Заметки</span><span class="sxs-lookup"><span data-stu-id="05c99-128">Remarks</span></span>

<span data-ttu-id="05c99-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span><span class="sxs-lookup"><span data-stu-id="05c99-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>

> [!NOTE]
> <span data-ttu-id="05c99-130">This element applies only to garbage collection threads.</span><span class="sxs-lookup"><span data-stu-id="05c99-130">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="05c99-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) element.</span><span class="sxs-lookup"><span data-stu-id="05c99-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) element.</span></span>

## <a name="example"></a><span data-ttu-id="05c99-132">Пример</span><span class="sxs-lookup"><span data-stu-id="05c99-132">Example</span></span>

<span data-ttu-id="05c99-133">The following example shows how to enable garbage collection for multiple CPU groups.</span><span class="sxs-lookup"><span data-stu-id="05c99-133">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="05c99-134">См. также</span><span class="sxs-lookup"><span data-stu-id="05c99-134">See also</span></span>

- [<span data-ttu-id="05c99-135">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="05c99-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="05c99-136">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="05c99-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="05c99-137">To disable concurrent garbage collection</span><span class="sxs-lookup"><span data-stu-id="05c99-137">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [<span data-ttu-id="05c99-138">Сборка мусора рабочей станции и сборка мусора сервера</span><span class="sxs-lookup"><span data-stu-id="05c99-138">Workstation and server garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection)
