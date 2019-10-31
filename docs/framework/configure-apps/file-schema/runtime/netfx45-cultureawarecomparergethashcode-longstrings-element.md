---
title: Элемент <NetFx45_CultureAwareComparerGetHashCode_LongStrings>
ms.date: 03/30/2017
helpviewer_keywords:
- NetFx45_CultureAwareComparerGetHashCode_LongStrings element
- <NetFx45_CultureAwareComparerGetHashCode_LongStrings> element
- GetHashCode method
- hash codes, calculating
ms.assetid: 3a5f38d1-ebc8-44de-aaeb-2929f6e6b48f
ms.openlocfilehash: 193f9a15768e4060d977063117c07558bbb1d766
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116134"
---
# <a name="netfx45_cultureawarecomparergethashcode_longstrings-element"></a><span data-ttu-id="fc7a1-102">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings > элемент</span><span class="sxs-lookup"><span data-stu-id="fc7a1-102">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings> Element</span></span>

<span data-ttu-id="fc7a1-103">Определяет, использует ли среда выполнения постоянный объем памяти для вычисления хэш-кодов методом <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="fc7a1-103">Specifies whether the runtime uses a fixed amount of memory to calculate hash codes for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="fc7a1-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fc7a1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fc7a1-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="fc7a1-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="fc7a1-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<NetFx45_CultureAwareComparerGetHashCode_LongStrings >**</span><span class="sxs-lookup"><span data-stu-id="fc7a1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx45_CultureAwareComparerGetHashCode_LongStrings>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="fc7a1-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc7a1-107">Syntax</span></span>

```xml
<NetFx45_CultureAwareComparerGetHashCode_LongStrings enabled="0|1">
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fc7a1-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fc7a1-108">Attributes and Elements</span></span>

<span data-ttu-id="fc7a1-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fc7a1-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="fc7a1-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fc7a1-110">Attributes</span></span>

|<span data-ttu-id="fc7a1-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fc7a1-111">Attribute</span></span>|<span data-ttu-id="fc7a1-112">Описание</span><span class="sxs-lookup"><span data-stu-id="fc7a1-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="fc7a1-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="fc7a1-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="fc7a1-114">Определяет, выделяет ли среда CLR постоянный объем памяти при вычислении хэш-кодов.</span><span class="sxs-lookup"><span data-stu-id="fc7a1-114">Specifies whether the common language runtime allocates a fixed amount of memory when calculating hash codes.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="fc7a1-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="fc7a1-115">enabled Attribute</span></span>

|<span data-ttu-id="fc7a1-116">значения</span><span class="sxs-lookup"><span data-stu-id="fc7a1-116">Value</span></span>|<span data-ttu-id="fc7a1-117">Описание</span><span class="sxs-lookup"><span data-stu-id="fc7a1-117">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="fc7a1-118">0</span><span class="sxs-lookup"><span data-stu-id="fc7a1-118">0</span></span>|<span data-ttu-id="fc7a1-119">Среда CLR выделяет переменный объем памяти методу <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> для вычисления хэш-кодов.</span><span class="sxs-lookup"><span data-stu-id="fc7a1-119">The common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span> <span data-ttu-id="fc7a1-120">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fc7a1-120">This is the default.</span></span>|
|<span data-ttu-id="fc7a1-121">1</span><span class="sxs-lookup"><span data-stu-id="fc7a1-121">1</span></span>|<span data-ttu-id="fc7a1-122">Среда CLR выделяет постоянный объем памяти методу <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> для вычисления хэш-кодов.</span><span class="sxs-lookup"><span data-stu-id="fc7a1-122">The common language runtime allocates a fixed amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="fc7a1-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fc7a1-123">Child Elements</span></span>

<span data-ttu-id="fc7a1-124">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="fc7a1-124">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fc7a1-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fc7a1-125">Parent Elements</span></span>

|<span data-ttu-id="fc7a1-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="fc7a1-126">Element</span></span>|<span data-ttu-id="fc7a1-127">Описание</span><span class="sxs-lookup"><span data-stu-id="fc7a1-127">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="fc7a1-128">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fc7a1-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="fc7a1-129">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="fc7a1-129">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fc7a1-130">Заметки</span><span class="sxs-lookup"><span data-stu-id="fc7a1-130">Remarks</span></span>

<span data-ttu-id="fc7a1-131">По умолчанию среда CLR выделяет переменный объем памяти для метода <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> и при попытке вычисления этим методом хэш-кодов очень больших строк (длиной свыше нескольких миллионов символов) может быть создано исключение <xref:System.ArgumentException> .</span><span class="sxs-lookup"><span data-stu-id="fc7a1-131">By default, the common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method, and an <xref:System.ArgumentException> can be thrown when the method attempts to compute the hash code of very large strings (over several million characters long).</span></span> <span data-ttu-id="fc7a1-132">Добавив этот элемент в файл конфигурации приложения и присвоив его атрибуту `enabled` значение "1", можно определить, что метод <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> использует другой алгоритм, который выделяет для вычисления хэш-кодов постоянный объем памяти.</span><span class="sxs-lookup"><span data-stu-id="fc7a1-132">By adding this element to an application configuration file and setting its `enabled` attribute to "1", you can specify that the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method use an alternate algorithm that allocates a fixed amount of memory for the computation of hash codes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc7a1-133">В `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` и более поздних версиях элемент [!INCLUDE[win8](../../../../../includes/win8-md.md)] не используется.</span><span class="sxs-lookup"><span data-stu-id="fc7a1-133">The `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` element is not used in [!INCLUDE[win8](../../../../../includes/win8-md.md)] and later versions.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc7a1-134">См. также</span><span class="sxs-lookup"><span data-stu-id="fc7a1-134">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="fc7a1-135">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="fc7a1-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="fc7a1-136">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="fc7a1-136">Configuration File Schema</span></span>](../index.md)
