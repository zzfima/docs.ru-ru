---
title: GCLOHThreshold element
ms.date: 11/20/2019
helpviewer_keywords:
- GCLOHThreshold element
- <GCLOHThreshold> element
ms.openlocfilehash: d72dc9d27984f60dfb6296217263ce8b176093c6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74451326"
---
# <a name="gclohthreshold-element"></a><span data-ttu-id="b2056-102">GCLOHThreshold element</span><span class="sxs-lookup"><span data-stu-id="b2056-102">GCLOHThreshold element</span></span>

<span data-ttu-id="b2056-103">Specifies the threshold size, in bytes, that causes the garbage collector to put objects on the large object heap (LOH).</span><span class="sxs-lookup"><span data-stu-id="b2056-103">Specifies the threshold size, in bytes, that causes the garbage collector to put objects on the large object heap (LOH).</span></span>

<span data-ttu-id="b2056-104">[\<configuration>](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b2056-104">[\<configuration>](../configuration-element.md)</span></span>\
<span data-ttu-id="b2056-105">&nbsp;&nbsp;[\<runtime>](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="b2056-105">&nbsp;&nbsp;[\<runtime>](runtime-element.md)</span></span>\
<span data-ttu-id="b2056-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCLOHThreshold></span><span class="sxs-lookup"><span data-stu-id="b2056-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCLOHThreshold></span></span>

## <a name="syntax"></a><span data-ttu-id="b2056-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2056-107">Syntax</span></span>

```xml
<GCLOHThreshold
   enabled="nnnn"/>
```

## <a name="attributes"></a><span data-ttu-id="b2056-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b2056-108">Attributes</span></span>

|<span data-ttu-id="b2056-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b2056-109">Attribute</span></span>|<span data-ttu-id="b2056-110">Описание</span><span class="sxs-lookup"><span data-stu-id="b2056-110">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="b2056-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b2056-111">Required attribute.</span></span><br /><br /><span data-ttu-id="b2056-112">Specifies the threshold size that causes objects to go on the large object heap.</span><span class="sxs-lookup"><span data-stu-id="b2056-112">Specifies the threshold size that causes objects to go on the large object heap.</span></span>|

### <a name="enabled-attribute"></a><span data-ttu-id="b2056-113">enabled attribute</span><span class="sxs-lookup"><span data-stu-id="b2056-113">enabled attribute</span></span>

|<span data-ttu-id="b2056-114">значения</span><span class="sxs-lookup"><span data-stu-id="b2056-114">Value</span></span>|<span data-ttu-id="b2056-115">Описание</span><span class="sxs-lookup"><span data-stu-id="b2056-115">Description</span></span>|
|-----------|-----------------|
|`nnnn`|<span data-ttu-id="b2056-116">The threshold size, in bytes, that causes objects to go on the large object heap.</span><span class="sxs-lookup"><span data-stu-id="b2056-116">The threshold size, in bytes, that causes objects to go on the large object heap.</span></span>|

## <a name="child-elements"></a><span data-ttu-id="b2056-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b2056-117">Child elements</span></span>

<span data-ttu-id="b2056-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b2056-118">None.</span></span>

## <a name="parent-elements"></a><span data-ttu-id="b2056-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b2056-119">Parent elements</span></span>

|<span data-ttu-id="b2056-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="b2056-120">Element</span></span>|<span data-ttu-id="b2056-121">Описание</span><span class="sxs-lookup"><span data-stu-id="b2056-121">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="b2056-122">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b2056-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="b2056-123">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="b2056-123">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b2056-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="b2056-124">Remarks</span></span>

<span data-ttu-id="b2056-125">This setting was introduced in .NET Framework 4.8.</span><span class="sxs-lookup"><span data-stu-id="b2056-125">This setting was introduced in .NET Framework 4.8.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2056-126">См. также</span><span class="sxs-lookup"><span data-stu-id="b2056-126">See also</span></span>

- [<span data-ttu-id="b2056-127">Run-time settings schema</span><span class="sxs-lookup"><span data-stu-id="b2056-127">Run-time settings schema</span></span>](index.md)
- [<span data-ttu-id="b2056-128">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="b2056-128">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="b2056-129">Основы сборки мусора</span><span class="sxs-lookup"><span data-stu-id="b2056-129">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="b2056-130">NET Core run-time config options for GC</span><span class="sxs-lookup"><span data-stu-id="b2056-130">NET Core run-time config options for GC</span></span>](../../../../core/run-time-config/garbage-collector.md)
