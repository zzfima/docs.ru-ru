---
title: Элемент <forcePerformanceCounterUniqueSharedMemoryReads>
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26fed0a10b9a25f25a580c7ac9a468cbedeb3671
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489469"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a><span data-ttu-id="29c41-102">\<forcePerformanceCounterUniqueSharedMemoryReads > элемент</span><span class="sxs-lookup"><span data-stu-id="29c41-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span></span>
<span data-ttu-id="29c41-103">Указывает, использует ли файл PerfCounter.dll параметр реестра CategoryOptions в приложении .NET Framework версии 1.1, чтобы определить, следует ли загружать данные счетчиков производительности из общей памяти конкретной категории или глобальной памяти.</span><span class="sxs-lookup"><span data-stu-id="29c41-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
 <span data-ttu-id="29c41-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="29c41-104">\<configuration></span></span>  
<span data-ttu-id="29c41-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="29c41-105">\<runtime></span></span>  
<span data-ttu-id="29c41-106">\<forcePerformanceCounterUniqueSharedMemoryReads ></span><span class="sxs-lookup"><span data-stu-id="29c41-106">\<forcePerformanceCounterUniqueSharedMemoryReads></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29c41-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="29c41-107">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29c41-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="29c41-108">Attributes and Elements</span></span>  
 <span data-ttu-id="29c41-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="29c41-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29c41-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="29c41-110">Attributes</span></span>  
  
|<span data-ttu-id="29c41-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="29c41-111">Attribute</span></span>|<span data-ttu-id="29c41-112">Описание</span><span class="sxs-lookup"><span data-stu-id="29c41-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="29c41-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="29c41-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="29c41-114">Указывает, использует ли файл PerfCounter.dll параметр реестра, чтобы определить, следует ли загружать данные счетчиков производительности из общей памяти конкретной категории или глобальной памяти.</span><span class="sxs-lookup"><span data-stu-id="29c41-114">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="29c41-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="29c41-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="29c41-116">Значение</span><span class="sxs-lookup"><span data-stu-id="29c41-116">Value</span></span>|<span data-ttu-id="29c41-117">Описание</span><span class="sxs-lookup"><span data-stu-id="29c41-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="29c41-118">PerfCounter.dll не использует параметр реестра, установка этого параметра значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="29c41-118">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="29c41-119">PerfCounter.dll используйте PerfCounter.dll параметр реестра.</span><span class="sxs-lookup"><span data-stu-id="29c41-119">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="29c41-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="29c41-120">Child Elements</span></span>  
 <span data-ttu-id="29c41-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="29c41-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="29c41-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="29c41-122">Parent Elements</span></span>  
  
|<span data-ttu-id="29c41-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="29c41-123">Element</span></span>|<span data-ttu-id="29c41-124">Описание</span><span class="sxs-lookup"><span data-stu-id="29c41-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="29c41-125">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="29c41-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="29c41-126">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="29c41-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29c41-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="29c41-127">Remarks</span></span>  
 <span data-ttu-id="29c41-128">В версиях .NET Framework до .NET Framework 4 версия PerfCounter.dll, который был загружен предоставивших в среду выполнения, который был загружен в процессе.</span><span class="sxs-lookup"><span data-stu-id="29c41-128">In versions of the .NET Framework before the .NET Framework 4, the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="29c41-129">Если компьютер имеет оба в .NET Framework версии 1.1 и [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)] установки приложения .NET Framework 1.1 будет загрузки версии .NET Framework 1.1 PerfCounter.dll.</span><span class="sxs-lookup"><span data-stu-id="29c41-129">If a computer had both the .NET Framework version 1.1 and the [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)] installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="29c41-130">Начиная с .NET Framework 4, загружается последняя установленная версия PerfCounter.dll.</span><span class="sxs-lookup"><span data-stu-id="29c41-130">Starting with the .NET Framework 4, the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="29c41-131">Это означает, что приложения .NET Framework 1.1 загрузит PerfCounter.dll версии .NET Framework 4, если .NET Framework 4 установлена на компьютере.</span><span class="sxs-lookup"><span data-stu-id="29c41-131">This means that a .NET Framework 1.1 application will load the .NET Framework 4 version of PerfCounter.dll if the .NET Framework 4 is installed on the computer.</span></span>  
  
 <span data-ttu-id="29c41-132">Начиная с .NET Framework 4, при использовании счетчиков производительности, PerfCounter.dll проверяет запись реестра CategoryOptions для каждого поставщика, чтобы определить, следует ли чтение из общей памяти конкретной категории или глобальной общей памяти.</span><span class="sxs-lookup"><span data-stu-id="29c41-132">Starting with the .NET Framework 4, when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="29c41-133">.NET Framework 1.1 PerfCounter.dll не поддерживает эту запись реестра, так как он не учитывает общей памяти конкретной категории; он считывает из глобальную общую память.</span><span class="sxs-lookup"><span data-stu-id="29c41-133">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="29c41-134">Для обеспечения обратной совместимости .NET Framework 4 PerfCounter.dll не проверяет запись реестра CategoryOptions при работе в приложении .NET Framework 1.1.</span><span class="sxs-lookup"><span data-stu-id="29c41-134">For backward compatibility, the .NET Framework 4 PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="29c41-135">Он просто использует глобальную общую память, так же, как .NET Framework 1.1 PerfCounter.dll.</span><span class="sxs-lookup"><span data-stu-id="29c41-135">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="29c41-136">Тем не менее, вы можете сообщить о .NET Framework 4 PerfCounter.dll для проверки параметра реестра, включив `<forcePerformanceCounterUniqueSharedMemoryReads>` элемент.</span><span class="sxs-lookup"><span data-stu-id="29c41-136">However, you can instruct the .NET Framework 4 PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="29c41-137">Включение `<forcePerformanceCounterUniqueSharedMemoryReads>` элемент не гарантирует, что будет использоваться общей памяти конкретной категории.</span><span class="sxs-lookup"><span data-stu-id="29c41-137">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="29c41-138">Параметр включен для `true` только вызывает PerfCounter.dll параметр реестра CategoryOptions ссылок.</span><span class="sxs-lookup"><span data-stu-id="29c41-138">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="29c41-139">Параметр по умолчанию является использование общей памяти конкретной категории; Тем не менее можно изменить параметр, чтобы указать, что следует использовать глобальную общую память.</span><span class="sxs-lookup"><span data-stu-id="29c41-139">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="29c41-140">Раздел реестра, который содержит параметр CategoryOptions является HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\< categoryName\>\Performance.</span><span class="sxs-lookup"><span data-stu-id="29c41-140">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="29c41-141">По умолчанию параметр имеет значение 3, предписывающее PerfCounter.dll для использования общей памяти конкретной категории.</span><span class="sxs-lookup"><span data-stu-id="29c41-141">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="29c41-142">Если параметр имеет значение 0, PerfCounter.dll использует глобальную общую память.</span><span class="sxs-lookup"><span data-stu-id="29c41-142">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="29c41-143">Данные экземпляра будет использоваться повторно, только в том случае, если имя экземпляра не идентичен используемому экземпляру.</span><span class="sxs-lookup"><span data-stu-id="29c41-143">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="29c41-144">Все версии будут иметь возможность записи в категорию.</span><span class="sxs-lookup"><span data-stu-id="29c41-144">All versions will be able to write to the category.</span></span> <span data-ttu-id="29c41-145">Если параметр имеет значение 1, использовать глобальную общую память, но данные экземпляра можно использовать повторно, если имя категории, имеют одинаковую длину категорию используются повторно.</span><span class="sxs-lookup"><span data-stu-id="29c41-145">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="29c41-146">Параметры 0 и 1 может привести к утечке памяти и заполнению памяти счетчиков производительности.</span><span class="sxs-lookup"><span data-stu-id="29c41-146">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29c41-147">Пример</span><span class="sxs-lookup"><span data-stu-id="29c41-147">Example</span></span>  
 <span data-ttu-id="29c41-148">Приведенный ниже показано, как указать, что PerfCounter.dll должны ссылаться реестра CategoryOptions, чтобы определить, какой сериализатор следует использовать общей памяти конкретной категории.</span><span class="sxs-lookup"><span data-stu-id="29c41-148">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="29c41-149">См. также</span><span class="sxs-lookup"><span data-stu-id="29c41-149">See also</span></span>

- [<span data-ttu-id="29c41-150">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="29c41-150">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="29c41-151">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="29c41-151">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
