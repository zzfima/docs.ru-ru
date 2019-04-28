---
title: Элемент <performanceCounters>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <performanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
ms.openlocfilehash: 6144bcbda69b2ba799e87c3e7fa2118fbe4d9bf6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673748"
---
# <a name="performancecounters-element"></a><span data-ttu-id="414b9-102">\<performanceCounters > элемент</span><span class="sxs-lookup"><span data-stu-id="414b9-102">\<performanceCounters> Element</span></span>

<span data-ttu-id="414b9-103">Задает размер глобальной памяти, совместно используемой счетчиками производительности.</span><span class="sxs-lookup"><span data-stu-id="414b9-103">Specifies the size of the global memory shared by performance counters.</span></span>

 <span data-ttu-id="414b9-104">\<Конфигурация > \\</span><span class="sxs-lookup"><span data-stu-id="414b9-104">\<configuration>\\</span></span>
<span data-ttu-id="414b9-105">\<System.Diagnostics > \\</span><span class="sxs-lookup"><span data-stu-id="414b9-105">\<system.diagnostics>\\</span></span>
<span data-ttu-id="414b9-106">\<performanceCounters ></span><span class="sxs-lookup"><span data-stu-id="414b9-106">\<performanceCounters></span></span>

## <a name="syntax"></a><span data-ttu-id="414b9-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="414b9-107">Syntax</span></span>

```xml
<performanceCounters filemappingsize="524288" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="414b9-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="414b9-108">Attributes and Elements</span></span>

<span data-ttu-id="414b9-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="414b9-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="414b9-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="414b9-110">Attributes</span></span>

|<span data-ttu-id="414b9-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="414b9-111">Attribute</span></span>|<span data-ttu-id="414b9-112">Описание</span><span class="sxs-lookup"><span data-stu-id="414b9-112">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="414b9-113">FileMappingSize</span><span class="sxs-lookup"><span data-stu-id="414b9-113">filemappingsize</span></span>|<span data-ttu-id="414b9-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="414b9-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="414b9-115">Указывает размер в байтах, глобальной памяти, совместно используемой счетчиками производительности.</span><span class="sxs-lookup"><span data-stu-id="414b9-115">Specifies the size, in bytes, of the global memory shared by performance counters.</span></span> <span data-ttu-id="414b9-116">Значение по умолчанию — 524288.</span><span class="sxs-lookup"><span data-stu-id="414b9-116">The default is 524288.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="414b9-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="414b9-117">Child Elements</span></span>

<span data-ttu-id="414b9-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="414b9-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="414b9-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="414b9-119">Parent Elements</span></span>

|<span data-ttu-id="414b9-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="414b9-120">Element</span></span>|<span data-ttu-id="414b9-121">Описание</span><span class="sxs-lookup"><span data-stu-id="414b9-121">Description</span></span>|
|-------------|-----------------|
|`Configuration`|<span data-ttu-id="414b9-122">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="414b9-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`system.diagnostics`|<span data-ttu-id="414b9-123">Задает корневой элемент для раздела конфигурации ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="414b9-123">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="414b9-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="414b9-124">Remarks</span></span>

<span data-ttu-id="414b9-125">Счетчики производительности используйте отображенного в памяти файла или общей памяти, публикацию данных производительности.</span><span class="sxs-lookup"><span data-stu-id="414b9-125">Performance counters use a memory mapped file, or shared memory, to publish performance data.</span></span>  <span data-ttu-id="414b9-126">Размер общей памяти определяет, сколько экземпляров можно использовать одновременно.</span><span class="sxs-lookup"><span data-stu-id="414b9-126">The size of the shared memory determines how many instances can be used at once.</span></span>  <span data-ttu-id="414b9-127">Существует два типа общей памяти: глобальную общую память и объем отдельной общей памяти.</span><span class="sxs-lookup"><span data-stu-id="414b9-127">There are two types of shared memory: global shared memory and separate shared memory.</span></span>  <span data-ttu-id="414b9-128">Глобальной общей памяти используется всех категорий счетчиков производительности, устанавливается вместе с .NET Framework версии 1.0 или 1.1.</span><span class="sxs-lookup"><span data-stu-id="414b9-128">The global shared memory is used by all performance counter categories installed with the .NET Framework versions 1.0 or 1.1.</span></span>  <span data-ttu-id="414b9-129">Категории счетчиков производительности, вместе с .NET Framework версии 2.0 используйте отдельной общей памяти, у каждого счетчика производительности есть свою собственную память.</span><span class="sxs-lookup"><span data-stu-id="414b9-129">Performance counter categories installed with the .NET Framework version 2.0 use separate shared memory, with each performance counter category having its own memory.</span></span>

<span data-ttu-id="414b9-130">Размер глобальную общую память можно задать только с помощью файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="414b9-130">The size of global shared memory can be set only with a configuration file.</span></span>  <span data-ttu-id="414b9-131">Значение по умолчанию-524 288 байтов, максимальный размер составляет 33 554 432 байтов и минимальный размер — 32 768 байт.</span><span class="sxs-lookup"><span data-stu-id="414b9-131">The default size is 524,288 byes, the maximum size is 33,554,432 bytes, and the minimum size is 32,768 bytes.</span></span>  <span data-ttu-id="414b9-132">Поскольку глобальной общей памяти совместно используется всеми процессами и категориями, создатель первый размер.</span><span class="sxs-lookup"><span data-stu-id="414b9-132">Since the global shared memory is shared by all processes and categories, the first creator specifies the size.</span></span>  <span data-ttu-id="414b9-133">Если размер определяется в файле конфигурации приложения, что размер используется только если приложение является первому приложению, которое вызывает счетчики производительности для выполнения.</span><span class="sxs-lookup"><span data-stu-id="414b9-133">If you define the size in your application configuration file, that size is only used if your application is the first application that causes the performance counters to execute.</span></span>  <span data-ttu-id="414b9-134">Поэтому правильное расположение, чтобы указать `filemappingsize` значением является файл Machine.config.</span><span class="sxs-lookup"><span data-stu-id="414b9-134">Therefore the correct location to specify the `filemappingsize` value is the Machine.config file.</span></span>  <span data-ttu-id="414b9-135">Отдельные счетчики производительности, поэтому в конечном итоге глобальную общую память исчерпана, если большое количество экземпляров счетчиков производительности с разными именами, создаются не освобождать память в глобальную общую память.</span><span class="sxs-lookup"><span data-stu-id="414b9-135">Memory in the global shared memory cannot be released by individual performance counters, so eventually global shared memory is exhausted if a large number of performance counter instances with different names are created.</span></span>

<span data-ttu-id="414b9-136">Размер отдельной общей памяти, значение DWORD FileMappingSize в реестре раздела HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<имя категории >* \Performance указывается ссылка на Во-первых следует значение, указанное для глобальной общей памяти в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="414b9-136">For the size of separate shared memory, the DWORD FileMappingSize value in the registry key HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<category name>* \Performance is referenced first, followed by the value specified for the global shared memory in the configuration file.</span></span> <span data-ttu-id="414b9-137">Если значение FileMappingSize не существует, то размер отдельной общей памяти задается равным одной четвертой (1/4) глобальные настройки в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="414b9-137">If the FileMappingSize value does not exist, then the separate shared memory size is set to one fourth (1/4) the global setting in the configuration file.</span></span>

## <a name="see-also"></a><span data-ttu-id="414b9-138">См. также</span><span class="sxs-lookup"><span data-stu-id="414b9-138">See also</span></span>

- <xref:System.Diagnostics.PerformanceCounter>
- <xref:System.Diagnostics.PerformanceCounterCategory>
- <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>
- <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
