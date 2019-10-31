---
title: Элемент <Thread_UseAllCpuGroups>
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
ms.openlocfilehash: a3a612c0ffbcb211157b9623d298ce8ad7a13e94
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115399"
---
# <a name="thread_useallcpugroups-element"></a><span data-ttu-id="076d4-102">\<Thread_UseAllCpuGroups > элемент</span><span class="sxs-lookup"><span data-stu-id="076d4-102">\<Thread_UseAllCpuGroups> Element</span></span>

<span data-ttu-id="076d4-103">Указывает, распределяет ли среда выполнения управляемые потоки во всех группах ЦП.</span><span class="sxs-lookup"><span data-stu-id="076d4-103">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>

<span data-ttu-id="076d4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="076d4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="076d4-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="076d4-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="076d4-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Thread_UseAllCpuGroups >**</span><span class="sxs-lookup"><span data-stu-id="076d4-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Thread_UseAllCpuGroups>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="076d4-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="076d4-107">Syntax</span></span>

```xml
<Thread_UseAllCpuGroups
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="076d4-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="076d4-108">Attributes and Elements</span></span>

<span data-ttu-id="076d4-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="076d4-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="076d4-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="076d4-110">Attributes</span></span>

|<span data-ttu-id="076d4-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="076d4-111">Attribute</span></span>|<span data-ttu-id="076d4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="076d4-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="076d4-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="076d4-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="076d4-114">Указывает, распределяет ли среда выполнения управляемые потоки во всех группах ЦП.</span><span class="sxs-lookup"><span data-stu-id="076d4-114">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="076d4-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="076d4-115">enabled Attribute</span></span>

|<span data-ttu-id="076d4-116">значения</span><span class="sxs-lookup"><span data-stu-id="076d4-116">Value</span></span>|<span data-ttu-id="076d4-117">Описание</span><span class="sxs-lookup"><span data-stu-id="076d4-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="076d4-118">Среда выполнения не распределяет управляемые потоки между несколькими группами ЦП.</span><span class="sxs-lookup"><span data-stu-id="076d4-118">The runtime does not distribute managed threads across multiple CPU groups.</span></span> <span data-ttu-id="076d4-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="076d4-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="076d4-120">Среда выполнения распределяет управляемые потоки между несколькими группами ЦП, если компьютер имеет несколько групп ЦП, а элемент [\<гккпуграуп >](gccpugroup-element.md) включен.</span><span class="sxs-lookup"><span data-stu-id="076d4-120">The runtime distributes managed threads across multiple CPU groups, if the computer has multiple CPU groups and the [\<GCCpuGroup>](gccpugroup-element.md) element is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="076d4-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="076d4-121">Child Elements</span></span>

<span data-ttu-id="076d4-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="076d4-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="076d4-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="076d4-123">Parent Elements</span></span>

|<span data-ttu-id="076d4-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="076d4-124">Element</span></span>|<span data-ttu-id="076d4-125">Описание</span><span class="sxs-lookup"><span data-stu-id="076d4-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="076d4-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="076d4-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="076d4-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="076d4-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="076d4-128">Заметки</span><span class="sxs-lookup"><span data-stu-id="076d4-128">Remarks</span></span>

<span data-ttu-id="076d4-129">Если компьютер имеет несколько групп ЦП, включение этого элемента приводит к тому, что среда выполнения распределяет управляемые потоки по всем группам ЦП.</span><span class="sxs-lookup"><span data-stu-id="076d4-129">When a computer has multiple CPU groups, enabling this element causes the runtime to distribute managed threads across all CPU groups.</span></span> <span data-ttu-id="076d4-130">Чтобы использовать эту функцию, необходимо также включить элемент [\<гккпуграуп >](gccpugroup-element.md) , который расширяет сбор мусора на все группы ЦП и учитывает все ядра при создании и балансировке куч.</span><span class="sxs-lookup"><span data-stu-id="076d4-130">To use this feature, you must also enable the [\<GCCpuGroup>](gccpugroup-element.md) element, which extends garbage collection to all CPU groups and takes all cores into account when creating and balancing heaps.</span></span> <span data-ttu-id="076d4-131">Чтобы включить элемент [\<гккпуграуп >](gccpugroup-element.md) , необходимо включить элемент [\<gcServer >](gcserver-element.md) .</span><span class="sxs-lookup"><span data-stu-id="076d4-131">Enabling the [\<GCCpuGroup>](gccpugroup-element.md) element requires enabling the [\<gcServer>](gcserver-element.md) element.</span></span> <span data-ttu-id="076d4-132">Если эти элементы не включены, включение элемента `<Thread_UseAllCpuGroups>` не оказывает никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="076d4-132">If these elements are not enabled, enabling the `<Thread_UseAllCpuGroups>` element has no effect.</span></span>

## <a name="example"></a><span data-ttu-id="076d4-133">Пример</span><span class="sxs-lookup"><span data-stu-id="076d4-133">Example</span></span>

<span data-ttu-id="076d4-134">В следующем примере показано, как включить поддержку нескольких групп ЦП.</span><span class="sxs-lookup"><span data-stu-id="076d4-134">The following example shows how to enable support for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <Thread_UseAllCpuGroups enabled="true"/>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="076d4-135">См. также</span><span class="sxs-lookup"><span data-stu-id="076d4-135">See also</span></span>

- [<span data-ttu-id="076d4-136">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="076d4-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="076d4-137">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="076d4-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="076d4-138">\<Гккпуграуп > элемент</span><span class="sxs-lookup"><span data-stu-id="076d4-138">\<GCCpuGroup> Element</span></span>](gccpugroup-element.md)
