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
# <a name="gccpugroup-element"></a><span data-ttu-id="ba090-102">\<Гккпуграуп > элемент</span><span class="sxs-lookup"><span data-stu-id="ba090-102">\<GCCpuGroup> Element</span></span>

<span data-ttu-id="ba090-103">Определяет, поддерживает ли сборка мусора несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="ba090-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>

<span data-ttu-id="ba090-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ba090-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ba090-105">[ **> среды выполнения\<** ](runtime-element.md) &nbsp;&nbsp;</span><span class="sxs-lookup"><span data-stu-id="ba090-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="ba090-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<гккпуграуп >**</span><span class="sxs-lookup"><span data-stu-id="ba090-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ba090-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba090-107">Syntax</span></span>

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ba090-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ba090-108">Attributes and Elements</span></span>

<span data-ttu-id="ba090-109">Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ba090-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ba090-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ba090-110">Attributes</span></span>

|<span data-ttu-id="ba090-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ba090-111">Attribute</span></span>|<span data-ttu-id="ba090-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ba090-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="ba090-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ba090-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="ba090-114">Определяет, поддерживает ли сборка мусора несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="ba090-114">Specifies whether garbage collection supports multiple CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="ba090-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="ba090-115">enabled Attribute</span></span>

|<span data-ttu-id="ba090-116">Значение</span><span class="sxs-lookup"><span data-stu-id="ba090-116">Value</span></span>|<span data-ttu-id="ba090-117">Описание</span><span class="sxs-lookup"><span data-stu-id="ba090-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="ba090-118">Сборка мусора не поддерживает несколько групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="ba090-118">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="ba090-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ba090-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="ba090-120">Сборка мусора поддерживает несколько групп ЦП, если включена сборка мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="ba090-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="ba090-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ba090-121">Child Elements</span></span>

<span data-ttu-id="ba090-122">Нет</span><span class="sxs-lookup"><span data-stu-id="ba090-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ba090-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ba090-123">Parent Elements</span></span>

|<span data-ttu-id="ba090-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="ba090-124">Element</span></span>|<span data-ttu-id="ba090-125">Описание</span><span class="sxs-lookup"><span data-stu-id="ba090-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="ba090-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ba090-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="ba090-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="ba090-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ba090-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="ba090-128">Remarks</span></span>

<span data-ttu-id="ba090-129">Если на компьютере установлено несколько групп ЦП и включена сборка мусора сервера (см. элемент [\<gcServer >](gcserver-element.md) ), включение этого элемента расширяет сбор мусора во всех группах ЦП и учитывает все ядра при создании и балансировке куч.</span><span class="sxs-lookup"><span data-stu-id="ba090-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>

> [!NOTE]
> <span data-ttu-id="ba090-130">Этот элемент применяется только к потокам сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ba090-130">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="ba090-131">Чтобы среда выполнения распространяла пользовательские потоки во всех группах ЦП, необходимо также включить элемент [\<Thread_UseAllCpuGroups >](thread-useallcpugroups-element.md) .</span><span class="sxs-lookup"><span data-stu-id="ba090-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) element.</span></span>

## <a name="example"></a><span data-ttu-id="ba090-132">Пример</span><span class="sxs-lookup"><span data-stu-id="ba090-132">Example</span></span>

<span data-ttu-id="ba090-133">В следующем примере показано, как включить сбор мусора для нескольких групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="ba090-133">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="ba090-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="ba090-134">See also</span></span>

- [<span data-ttu-id="ba090-135">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="ba090-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ba090-136">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="ba090-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="ba090-137">Отключение параллельной сборки мусора</span><span class="sxs-lookup"><span data-stu-id="ba090-137">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [<span data-ttu-id="ba090-138">Сборка мусора рабочей станции и сборка мусора сервера</span><span class="sxs-lookup"><span data-stu-id="ba090-138">Workstation and server garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection)
