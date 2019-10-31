---
title: Элемент <forcePerformanceCounterUniqueSharedMemoryReads>
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
ms.openlocfilehash: efa6dce1035f7d2cf63b74c6a03d911b5dede722
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116952"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a><span data-ttu-id="3ba25-102">\<Форцеперформанцекаунтеруникуешаредмемориреадс > элемент</span><span class="sxs-lookup"><span data-stu-id="3ba25-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span></span>
<span data-ttu-id="3ba25-103">Указывает, использует ли файл PerfCounter.dll параметр реестра CategoryOptions в приложении .NET Framework версии 1.1, чтобы определить, следует ли загружать данные счетчиков производительности из общей памяти конкретной категории или глобальной памяти.</span><span class="sxs-lookup"><span data-stu-id="3ba25-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
<span data-ttu-id="3ba25-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3ba25-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3ba25-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="3ba25-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="3ba25-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<форцеперформанцекаунтеруникуешаредмемориреадс >**</span><span class="sxs-lookup"><span data-stu-id="3ba25-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<forcePerformanceCounterUniqueSharedMemoryReads>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ba25-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3ba25-107">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ba25-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3ba25-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3ba25-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3ba25-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ba25-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3ba25-110">Attributes</span></span>  
  
|<span data-ttu-id="3ba25-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3ba25-111">Attribute</span></span>|<span data-ttu-id="3ba25-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3ba25-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="3ba25-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="3ba25-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="3ba25-114">Указывает, использует ли Перфкаунтер. dll параметр реестра Категорйоптионс, чтобы определить, следует ли загружать данные счетчиков производительности из общей памяти конкретной категории или глобальной памяти.</span><span class="sxs-lookup"><span data-stu-id="3ba25-114">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="3ba25-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="3ba25-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="3ba25-116">значения</span><span class="sxs-lookup"><span data-stu-id="3ba25-116">Value</span></span>|<span data-ttu-id="3ba25-117">Описание</span><span class="sxs-lookup"><span data-stu-id="3ba25-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="3ba25-118">Перфкаунтер. dll не использует параметр реестра Категорйоптионс. это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3ba25-118">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="3ba25-119">Перфкаунтер. dll использует параметр реестра Категорйоптионс.</span><span class="sxs-lookup"><span data-stu-id="3ba25-119">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3ba25-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3ba25-120">Child Elements</span></span>  
 <span data-ttu-id="3ba25-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3ba25-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3ba25-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3ba25-122">Parent Elements</span></span>  
  
|<span data-ttu-id="3ba25-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="3ba25-123">Element</span></span>|<span data-ttu-id="3ba25-124">Описание</span><span class="sxs-lookup"><span data-stu-id="3ba25-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3ba25-125">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3ba25-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3ba25-126">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="3ba25-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ba25-127">Заметки</span><span class="sxs-lookup"><span data-stu-id="3ba25-127">Remarks</span></span>  
 <span data-ttu-id="3ba25-128">В версиях .NET Framework до .NET Framework 4 версия Перфкаунтер. dll, которая была загружена, соответствует среде выполнения, загруженной в процессе.</span><span class="sxs-lookup"><span data-stu-id="3ba25-128">In versions of the .NET Framework before the .NET Framework 4, the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="3ba25-129">Если на компьютере установлены как .NET Framework версии 1,1, так и .NET Framework 2,0, то приложение .NET Framework 1,1 загрузит .NET Framework 1,1 версии Перфкаунтер. dll.</span><span class="sxs-lookup"><span data-stu-id="3ba25-129">If a computer had both the .NET Framework version 1.1 and the .NET Framework 2.0 installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="3ba25-130">Начиная с .NET Framework 4, загружается последняя установленная версия Перфкаунтер. dll.</span><span class="sxs-lookup"><span data-stu-id="3ba25-130">Starting with the .NET Framework 4, the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="3ba25-131">Это означает, что приложение .NET Framework 1,1 будет загружать версию Перфкаунтер. dll .NET Framework 4, если на компьютере установлен .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3ba25-131">This means that a .NET Framework 1.1 application will load the .NET Framework 4 version of PerfCounter.dll if the .NET Framework 4 is installed on the computer.</span></span>  
  
 <span data-ttu-id="3ba25-132">Начиная с .NET Framework 4, при использовании счетчиков производительности Перфкаунтер. dll проверяет запись реестра Категорйоптионс для каждого поставщика, чтобы определить, должен ли он выполнять чтение из общей памяти конкретной категории или глобальной общей памяти.</span><span class="sxs-lookup"><span data-stu-id="3ba25-132">Starting with the .NET Framework 4, when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="3ba25-133">.NET Framework 1,1 Перфкаунтер. dll не считывает эту запись реестра, так как она не поддерживает общую память, относящуюся к категории. Он всегда считывает данные из глобальной общей памяти.</span><span class="sxs-lookup"><span data-stu-id="3ba25-133">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="3ba25-134">Для обеспечения обратной совместимости .NET Framework 4 Перфкаунтер. dll не проверяет запись реестра Категорйоптионс при запуске в приложении .NET Framework 1,1.</span><span class="sxs-lookup"><span data-stu-id="3ba25-134">For backward compatibility, the .NET Framework 4 PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="3ba25-135">Он просто использует глобальную общую память так же, как .NET Framework 1,1 Перфкаунтер. dll.</span><span class="sxs-lookup"><span data-stu-id="3ba25-135">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="3ba25-136">Однако можно указать .NET Framework 4 Перфкаунтер. dll, чтобы проверить параметр реестра, включив элемент `<forcePerformanceCounterUniqueSharedMemoryReads>`.</span><span class="sxs-lookup"><span data-stu-id="3ba25-136">However, you can instruct the .NET Framework 4 PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3ba25-137">Включение элемента `<forcePerformanceCounterUniqueSharedMemoryReads>` не гарантирует, что будет использоваться общая память, относящаяся к категории.</span><span class="sxs-lookup"><span data-stu-id="3ba25-137">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="3ba25-138">Параметр Enabled имеет значение `true` приводит к тому, что Перфкаунтер. dll ссылается на параметр реестра Категорйоптионс.</span><span class="sxs-lookup"><span data-stu-id="3ba25-138">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="3ba25-139">Значение по умолчанию для Категорйоптионс — использовать общую память, относящуюся к категории; Однако можно изменить Категорйоптионс, чтобы указать, что следует использовать глобальную общую память.</span><span class="sxs-lookup"><span data-stu-id="3ba25-139">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="3ba25-140">Раздел реестра, содержащий параметр Категорйоптионс, — HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\< categoryName\>\Перформанце.</span><span class="sxs-lookup"><span data-stu-id="3ba25-140">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="3ba25-141">По умолчанию Категорйоптионс имеет значение 3, что указывает Перфкаунтер. dll на использование общей памяти, относящейся к определенной категории.</span><span class="sxs-lookup"><span data-stu-id="3ba25-141">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="3ba25-142">Если Категорйоптионс имеет значение 0, Перфкаунтер. dll использует глобальную общую память.</span><span class="sxs-lookup"><span data-stu-id="3ba25-142">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="3ba25-143">Данные экземпляра будут использоваться повторно только в том случае, если имя создаваемого экземпляра идентично повторно используемому экземпляру.</span><span class="sxs-lookup"><span data-stu-id="3ba25-143">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="3ba25-144">Все версии будут иметь возможность записи в категорию.</span><span class="sxs-lookup"><span data-stu-id="3ba25-144">All versions will be able to write to the category.</span></span> <span data-ttu-id="3ba25-145">Если для Категорйоптионс задано значение 1, используется глобальная общая память, но данные экземпляра могут использоваться повторно, если длина имени категории совпадает с длиной повторно используемого категории.</span><span class="sxs-lookup"><span data-stu-id="3ba25-145">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="3ba25-146">Параметры 0 и 1 могут привести к утечке памяти и заполнению памяти счетчика производительности.</span><span class="sxs-lookup"><span data-stu-id="3ba25-146">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ba25-147">Пример</span><span class="sxs-lookup"><span data-stu-id="3ba25-147">Example</span></span>  
 <span data-ttu-id="3ba25-148">В следующем примере показано, как указать, что Перфкаунтер. dll должна ссылаться на запись реестра Категорйоптионс, чтобы определить, следует ли использовать общую память конкретной категории.</span><span class="sxs-lookup"><span data-stu-id="3ba25-148">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3ba25-149">См. также</span><span class="sxs-lookup"><span data-stu-id="3ba25-149">See also</span></span>

- [<span data-ttu-id="3ba25-150">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="3ba25-150">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3ba25-151">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="3ba25-151">Configuration File Schema</span></span>](../index.md)
