---
title: Элемент <forcePerformanceCounterUniqueSharedMemoryReads>
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
ms.openlocfilehash: 742b444c445ba67d6977b622e615a6a8f591826e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154144"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a><span data-ttu-id="9b6f6-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Элемент</span><span class="sxs-lookup"><span data-stu-id="9b6f6-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span></span>
<span data-ttu-id="9b6f6-103">Указывает, использует ли файл PerfCounter.dll параметр реестра CategoryOptions в приложении .NET Framework версии 1.1, чтобы определить, следует ли загружать данные счетчиков производительности из общей памяти конкретной категории или глобальной памяти.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
<span data-ttu-id="9b6f6-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9b6f6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9b6f6-105">&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="9b6f6-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="9b6f6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<forcePerformanceCounterUniqueSharedMemoryReads>**</span><span class="sxs-lookup"><span data-stu-id="9b6f6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<forcePerformanceCounterUniqueSharedMemoryReads>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b6f6-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b6f6-107">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b6f6-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9b6f6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9b6f6-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b6f6-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9b6f6-110">Attributes</span></span>  
  
|<span data-ttu-id="9b6f6-111">attribute</span><span class="sxs-lookup"><span data-stu-id="9b6f6-111">Attribute</span></span>|<span data-ttu-id="9b6f6-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9b6f6-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="9b6f6-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="9b6f6-114">Указывает, использует ли PerfCounter.dll настройки реестра CategoryOptions для определения того, следует ли загружать данные счетчика производительности из общей памяти, специфичной для категории, или глобальной памяти.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-114">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="9b6f6-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="9b6f6-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="9b6f6-116">Значение</span><span class="sxs-lookup"><span data-stu-id="9b6f6-116">Value</span></span>|<span data-ttu-id="9b6f6-117">Описание</span><span class="sxs-lookup"><span data-stu-id="9b6f6-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="9b6f6-118">PerfCounter.dll не использует настройки реестра CategoryOptions Это по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-118">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="9b6f6-119">PerfCounter.dll использует настройки реестра CategoryOptions.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-119">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b6f6-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9b6f6-120">Child Elements</span></span>  
 <span data-ttu-id="9b6f6-121">Нет.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b6f6-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9b6f6-122">Parent Elements</span></span>  
  
|<span data-ttu-id="9b6f6-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="9b6f6-123">Element</span></span>|<span data-ttu-id="9b6f6-124">Описание</span><span class="sxs-lookup"><span data-stu-id="9b6f6-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9b6f6-125">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9b6f6-126">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b6f6-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="9b6f6-127">Remarks</span></span>  
 <span data-ttu-id="9b6f6-128">В версиях рамочного соглашения .NET перед .NET Framework 4 загруженная версия PerfCounter.dll соответствовала времени выполнения, загруженного в процессе.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-128">In versions of the .NET Framework before the .NET Framework 4, the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="9b6f6-129">Если бы компьютер установил как версию .NET Framework 1.1, так и .NET Framework 2.0, приложение .NET Framework 1.1 загрузило бы версию PerfCounter.dll .NET Framework 1.1.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-129">If a computer had both the .NET Framework version 1.1 and the .NET Framework 2.0 installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="9b6f6-130">Начиная с .NET Framework 4, загружается новейшая установленная версия PerfCounter.dll.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-130">Starting with the .NET Framework 4, the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="9b6f6-131">Это означает, что приложение .NET Framework 1.1 загрузит версию PerfCounter.dll .NET Framework 4, если на компьютере будет установлена система .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-131">This means that a .NET Framework 1.1 application will load the .NET Framework 4 version of PerfCounter.dll if the .NET Framework 4 is installed on the computer.</span></span>  
  
 <span data-ttu-id="9b6f6-132">Начиная с .NET Framework 4, perfCounter.dll проверяет вход в реестр CategoryOptions для каждого поставщика, чтобы определить, следует ли читать из общей памяти, специфичная для категории, или глобальной общей памяти.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-132">Starting with the .NET Framework 4, when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="9b6f6-133">В .NET Framework 1.1 PerfCounter.dll не читает сярвод, поскольку он не знает об общей памяти, специфичном для категории; он всегда читает из глобальной общей памяти.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-133">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="9b6f6-134">Для обратной совместимости,в .NET Framework 4 PerfCounter.dll не проверяет вход в реестр CategoryOptions при запуске в приложении .NET Framework 1.1.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-134">For backward compatibility, the .NET Framework 4 PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="9b6f6-135">Он просто использует глобальную общую память, как и .NET Framework 1.1 PerfCounter.dll.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-135">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="9b6f6-136">Тем не менее, вы можете поручить .NET Framework 4 PerfCounter.dll проверить настройки реестра, включив `<forcePerformanceCounterUniqueSharedMemoryReads>` элемент.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-136">However, you can instruct the .NET Framework 4 PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9b6f6-137">Включение `<forcePerformanceCounterUniqueSharedMemoryReads>` элемента не гарантирует использования общей памяти, относясь к категории.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-137">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="9b6f6-138">Установка включена `true` только вызывает PerfCounter.dll ссылаться на настройки реестра CategoryOptions.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-138">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="9b6f6-139">Настройка по умолчанию для CategoryOptions заключается в использовании общей памяти, специфичной для категории; однако можно изменить варианты категории, чтобы указать, что глобальная общая память должна использоваться.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-139">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="9b6f6-140">Ключ реестра, содержащий настройки CategoryOptions, является HKEY_LOCAL_MACHINE »Система»-ТекущийКонтрольSet»Услуги\\<категорииName\>«Производительность».</span><span class="sxs-lookup"><span data-stu-id="9b6f6-140">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="9b6f6-141">По умолчанию категорияOptions устанавливается до 3, что инструктирует PerfCounter.dll использовать общую память, специфичную для категории.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-141">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="9b6f6-142">Если категорияOptions установлена до 0, PerfCounter.dll использует глобальную общую память.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-142">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="9b6f6-143">Данные экземпляра будут повторно использоваться только в том случае, если имя создаваемого экземпляра идентично повторноиспользуемому экземпляру.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-143">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="9b6f6-144">Все версии смогут писать в категорию.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-144">All versions will be able to write to the category.</span></span> <span data-ttu-id="9b6f6-145">Если категорияOptions установлена до 1, используется глобальная общая память, но данные экземпляра могут быть использованы повторно, если имя категории имеет такую же длину, как и повторно используемая категория.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-145">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="9b6f6-146">Настройки 0 и 1 могут привести к утечке памяти и заполнению памяти счетчика производительности.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-146">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b6f6-147">Пример</span><span class="sxs-lookup"><span data-stu-id="9b6f6-147">Example</span></span>  
 <span data-ttu-id="9b6f6-148">В следующем примере показано, как указать, что PerfCounter.dll должен ссылаться на вход в реестр CategoryOptions, чтобы определить, следует ли использовать общую память категории.</span><span class="sxs-lookup"><span data-stu-id="9b6f6-148">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b6f6-149">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9b6f6-149">See also</span></span>

- [<span data-ttu-id="9b6f6-150">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="9b6f6-150">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9b6f6-151">Схема конфигурации файлов</span><span class="sxs-lookup"><span data-stu-id="9b6f6-151">Configuration File Schema</span></span>](../index.md)
