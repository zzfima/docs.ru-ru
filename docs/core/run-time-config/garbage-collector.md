---
title: Параметры конфигурации сборщика мусора
description: Сведения о параметрах времени выполнения, определяющих, как сборщик мусора управляет памятью для приложений .NET Core.
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: 044083d69601f5092724a46d358b2ee5673d428d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733517"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="6e984-103">Параметры конфигурации времени выполнения для сборки мусора</span><span class="sxs-lookup"><span data-stu-id="6e984-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="6e984-104">Эта страница содержит сведения о параметрах сборщика мусора (GC), которые можно изменить во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="6e984-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="6e984-105">Если вы пытаетесь добиться пиковой производительности запущенных приложений, рекомендуется использовать эти параметры.</span><span class="sxs-lookup"><span data-stu-id="6e984-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="6e984-106">Однако значения по умолчанию обеспечивают оптимальную производительность для большинства приложений в типичных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="6e984-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="6e984-107">На этой странице параметры упорядочены по группам.</span><span class="sxs-lookup"><span data-stu-id="6e984-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="6e984-108">Параметры в каждой группе обычно используются совместно друг с другом для достижения определенного результата.</span><span class="sxs-lookup"><span data-stu-id="6e984-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="6e984-109">Эти параметры также могут динамически изменяться приложением во время его выполнения, поэтому любые заданные параметры времени выполнения могут быть переопределены.</span><span class="sxs-lookup"><span data-stu-id="6e984-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="6e984-110">Некоторые параметры, такие как [уровень задержки](../../standard/garbage-collection/latency.md), обычно задаются только через API во время разработки.</span><span class="sxs-lookup"><span data-stu-id="6e984-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="6e984-111">Такие параметры будут пропущены на этой странице.</span><span class="sxs-lookup"><span data-stu-id="6e984-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="6e984-112">Для числовых значений используйте десятичную нотацию для параметров в файле *runtimeconfig.json* и шестнадцатеричную нотацию для параметров переменных среды.</span><span class="sxs-lookup"><span data-stu-id="6e984-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="6e984-113">Шестнадцатеричные значения можно указать с помощью префикса "0x" или без него.</span><span class="sxs-lookup"><span data-stu-id="6e984-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="6e984-114">Варианты сборки мусора</span><span class="sxs-lookup"><span data-stu-id="6e984-114">Flavors of garbage collection</span></span>

<span data-ttu-id="6e984-115">Два основных варианта сборки мусора — это сборка мусора рабочей станции и сборка мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="6e984-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="6e984-116">Дополнительные сведения о различиях между этими двумя вариантами см. в статье [Основы сборки мусора](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span><span class="sxs-lookup"><span data-stu-id="6e984-116">For more information about differences between the two, see [Fundamentals of garbage collection](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span></span>

<span data-ttu-id="6e984-117">Подвиды сборки мусора представлены фоновым и непараллельным выполнением.</span><span class="sxs-lookup"><span data-stu-id="6e984-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="6e984-118">Чтобы выбрать варианты сборки мусора, используйте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="6e984-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="6e984-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="6e984-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="6e984-120">Указывает, использует ли приложение сборку мусора рабочей станции или сборку мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="6e984-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="6e984-121">По умолчанию: сборка мусора рабочей станции (`false`).</span><span class="sxs-lookup"><span data-stu-id="6e984-121">Default: Workstation garbage collection (`false`).</span></span>

| | <span data-ttu-id="6e984-122">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="6e984-122">Setting name</span></span> | <span data-ttu-id="6e984-123">Значения</span><span class="sxs-lookup"><span data-stu-id="6e984-123">Values</span></span> | <span data-ttu-id="6e984-124">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="6e984-124">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6e984-125">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="6e984-125">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="6e984-126">`false` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="6e984-126">`false` - workstation</span></span><br/><span data-ttu-id="6e984-127">`true` — сервер</span><span class="sxs-lookup"><span data-stu-id="6e984-127">`true` - server</span></span> | <span data-ttu-id="6e984-128">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="6e984-128">.NET Core 1.0</span></span> |
| <span data-ttu-id="6e984-129">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="6e984-129">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="6e984-130">`false` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="6e984-130">`false` - workstation</span></span><br/><span data-ttu-id="6e984-131">`true` — сервер</span><span class="sxs-lookup"><span data-stu-id="6e984-131">`true` - server</span></span> | <span data-ttu-id="6e984-132">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="6e984-132">.NET Core 1.0</span></span> |
| <span data-ttu-id="6e984-133">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="6e984-133">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="6e984-134">`0` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="6e984-134">`0` - workstation</span></span><br/><span data-ttu-id="6e984-135">`1` — сервер</span><span class="sxs-lookup"><span data-stu-id="6e984-135">`1` - server</span></span> | <span data-ttu-id="6e984-136">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="6e984-136">.NET Core 1.0</span></span> |
| <span data-ttu-id="6e984-137">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="6e984-137">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="6e984-138">GCServer</span><span class="sxs-lookup"><span data-stu-id="6e984-138">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="6e984-139">`false` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="6e984-139">`false` - workstation</span></span><br/><span data-ttu-id="6e984-140">`true` — сервер</span><span class="sxs-lookup"><span data-stu-id="6e984-140">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="6e984-141">Примеры</span><span class="sxs-lookup"><span data-stu-id="6e984-141">Examples</span></span>

<span data-ttu-id="6e984-142">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="6e984-142">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="6e984-143">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="6e984-143">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="6e984-144">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="6e984-144">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="6e984-145">Указывает, включена ли фоновая (параллельная) сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="6e984-145">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="6e984-146">По умолчанию: включено (`true`).</span><span class="sxs-lookup"><span data-stu-id="6e984-146">Default: Enabled (`true`).</span></span>
- <span data-ttu-id="6e984-147">Дополнительные сведения см. в статьях [Фоновая сборка мусора](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) и [Фоновая сборка мусора сервера](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span><span class="sxs-lookup"><span data-stu-id="6e984-147">For more information, see [Background garbage collection](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) and [Background server garbage collection](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span></span>

| | <span data-ttu-id="6e984-148">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="6e984-148">Setting name</span></span> | <span data-ttu-id="6e984-149">Значения</span><span class="sxs-lookup"><span data-stu-id="6e984-149">Values</span></span> | <span data-ttu-id="6e984-150">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="6e984-150">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6e984-151">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="6e984-151">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="6e984-152">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="6e984-152">`true` - background GC</span></span><br/><span data-ttu-id="6e984-153">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="6e984-153">`false` - non-concurrent GC</span></span> | <span data-ttu-id="6e984-154">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="6e984-154">.NET Core 1.0</span></span> |
| <span data-ttu-id="6e984-155">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="6e984-155">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="6e984-156">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="6e984-156">`true` - background GC</span></span><br/><span data-ttu-id="6e984-157">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="6e984-157">`false` - non-concurrent GC</span></span> | <span data-ttu-id="6e984-158">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="6e984-158">.NET Core 1.0</span></span> |
| <span data-ttu-id="6e984-159">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="6e984-159">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="6e984-160">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="6e984-160">`true` - background GC</span></span><br/><span data-ttu-id="6e984-161">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="6e984-161">`false` - non-concurrent GC</span></span> | <span data-ttu-id="6e984-162">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="6e984-162">.NET Core 1.0</span></span> |
| <span data-ttu-id="6e984-163">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="6e984-163">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="6e984-164">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="6e984-164">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="6e984-165">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="6e984-165">`true` - background GC</span></span><br/><span data-ttu-id="6e984-166">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="6e984-166">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="6e984-167">Примеры</span><span class="sxs-lookup"><span data-stu-id="6e984-167">Examples</span></span>

<span data-ttu-id="6e984-168">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="6e984-168">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="6e984-169">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="6e984-169">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="6e984-170">Управление использованием ресурсов</span><span class="sxs-lookup"><span data-stu-id="6e984-170">Manage resource usage</span></span>

<span data-ttu-id="6e984-171">Используйте параметры, описанные в этом разделе, для управления использованием памяти и ЦП в сборщике мусора.</span><span class="sxs-lookup"><span data-stu-id="6e984-171">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="6e984-172">Дополнительные сведения о некоторых из этих параметров см. в записи блога о [компромиссе между сборкой мусора рабочей станции и сервера](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/).</span><span class="sxs-lookup"><span data-stu-id="6e984-172">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="6e984-173">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="6e984-173">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="6e984-174">Ограничивает число куч, создаваемых сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="6e984-174">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="6e984-175">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="6e984-175">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="6e984-176">Если включено сходство процессоров сборки мусора, что используется по умолчанию, параметр счетчика куч реализует сходство `n` куч/потоков сборки мусора с первыми `n` процессорами.</span><span class="sxs-lookup"><span data-stu-id="6e984-176">If GC processor affinity is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="6e984-177">(Используйте параметры сходства маски или сходства диапазонов, чтобы указать, для каких именно процессоров следует реализовать сходство.)</span><span class="sxs-lookup"><span data-stu-id="6e984-177">(Use the affinitize mask or affinitize ranges settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="6e984-178">Если сходство процессоров сборки мусора отключено, этот параметр будет ограничивать количество куч сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="6e984-178">If GC processor affinity is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="6e984-179">Дополнительные сведения см. в [примечаниях по GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="6e984-179">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="6e984-180">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="6e984-180">Setting name</span></span> | <span data-ttu-id="6e984-181">Значения</span><span class="sxs-lookup"><span data-stu-id="6e984-181">Values</span></span> | <span data-ttu-id="6e984-182">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="6e984-182">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6e984-183">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="6e984-183">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="6e984-184">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="6e984-184">*decimal value*</span></span> | <span data-ttu-id="6e984-185">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6e984-185">.NET Core 3.0</span></span> |
| <span data-ttu-id="6e984-186">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="6e984-186">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="6e984-187">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="6e984-187">*hexadecimal value*</span></span> | <span data-ttu-id="6e984-188">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6e984-188">.NET Core 3.0</span></span> |
| <span data-ttu-id="6e984-189">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="6e984-189">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="6e984-190">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="6e984-190">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="6e984-191">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="6e984-191">*decimal value*</span></span> | <span data-ttu-id="6e984-192">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="6e984-192">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="6e984-193">Пример.</span><span class="sxs-lookup"><span data-stu-id="6e984-193">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapCount": 16
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="6e984-194">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="6e984-194">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="6e984-195">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="6e984-195">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="6e984-196">Например, чтобы ограничить число куч значением 16, для JSON-файла нужно указать 16, а для переменной среды — 0x10 или 10.</span><span class="sxs-lookup"><span data-stu-id="6e984-196">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="6e984-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="6e984-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="6e984-198">Указывает конкретные процессоры, которые должны использоваться потоками сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="6e984-198">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="6e984-199">Если сходство процессоров отключено посредством задания значения `true` для `System.GC.NoAffinitize`, этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="6e984-199">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="6e984-200">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="6e984-200">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="6e984-201">Это значение представляет собой битовую маску, которая определяет доступные процессу процессоры.</span><span class="sxs-lookup"><span data-stu-id="6e984-201">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="6e984-202">Например, десятичное значение 1023 (или шестнадцатеричное значение 0x3FF или 3FF, если вы используете переменную среды), равно 0011 1111 1111 в двоичной нотации.</span><span class="sxs-lookup"><span data-stu-id="6e984-202">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="6e984-203">При этом будут использоваться первые 10 процессоров.</span><span class="sxs-lookup"><span data-stu-id="6e984-203">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="6e984-204">Чтобы указать следующие 10 процессоров, то есть процессоры 10–19, задайте десятичное значение 1047552 (или шестнадцатеричное значение 0xFFC00 или FFC00), которое эквивалентно двоичному значению 1111 1111 1100 0000 0000.</span><span class="sxs-lookup"><span data-stu-id="6e984-204">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="6e984-205">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="6e984-205">Setting name</span></span> | <span data-ttu-id="6e984-206">Значения</span><span class="sxs-lookup"><span data-stu-id="6e984-206">Values</span></span> | <span data-ttu-id="6e984-207">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="6e984-207">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6e984-208">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="6e984-208">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="6e984-209">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="6e984-209">*decimal value*</span></span> | <span data-ttu-id="6e984-210">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6e984-210">.NET Core 3.0</span></span> |
| <span data-ttu-id="6e984-211">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="6e984-211">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="6e984-212">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="6e984-212">*hexadecimal value*</span></span> | <span data-ttu-id="6e984-213">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6e984-213">.NET Core 3.0</span></span> |
| <span data-ttu-id="6e984-214">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="6e984-214">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="6e984-215">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="6e984-215">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="6e984-216">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="6e984-216">*decimal value*</span></span> | <span data-ttu-id="6e984-217">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="6e984-217">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="6e984-218">Пример.</span><span class="sxs-lookup"><span data-stu-id="6e984-218">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="6e984-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="6e984-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="6e984-220">Указывает список процессоров, используемых для потоков сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="6e984-220">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="6e984-221">Этот параметр аналогичен `System.GC.HeapAffinitizeMask`, за исключением того, что он позволяет указать больше 64 процессоров.</span><span class="sxs-lookup"><span data-stu-id="6e984-221">This setting is similar to `System.GC.HeapAffinitizeMask`, except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="6e984-222">Для операционных систем Windows добавьте к номеру или диапазону процессоров префикс в виде соответствующей [группы ЦП](/windows/win32/procthread/processor-groups), например "0:1-10,0:12,1:50-52,1:70".</span><span class="sxs-lookup"><span data-stu-id="6e984-222">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="6e984-223">Если сходство процессоров отключено посредством задания значения `true` для `System.GC.NoAffinitize`, этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="6e984-223">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="6e984-224">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="6e984-224">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="6e984-225">Дополнительные сведения см. в записи об [улучшении конфигурации ЦП для сборки мусора на компьютерах, имеющих более 64 ЦП](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/), в блоге Майони Стивенс (Maoni Stephens).</span><span class="sxs-lookup"><span data-stu-id="6e984-225">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="6e984-226">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="6e984-226">Setting name</span></span> | <span data-ttu-id="6e984-227">Значения</span><span class="sxs-lookup"><span data-stu-id="6e984-227">Values</span></span> | <span data-ttu-id="6e984-228">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="6e984-228">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6e984-229">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="6e984-229">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="6e984-230">Разделенный запятыми список номеров процессоров или диапазонов номеров процессоров.</span><span class="sxs-lookup"><span data-stu-id="6e984-230">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="6e984-231">Пример для Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="6e984-231">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="6e984-232">Пример для Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="6e984-232">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="6e984-233">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6e984-233">.NET Core 3.0</span></span> |
| <span data-ttu-id="6e984-234">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="6e984-234">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="6e984-235">Разделенный запятыми список номеров процессоров или диапазонов номеров процессоров.</span><span class="sxs-lookup"><span data-stu-id="6e984-235">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="6e984-236">Пример для Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="6e984-236">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="6e984-237">Пример для Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="6e984-237">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="6e984-238">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6e984-238">.NET Core 3.0</span></span> |

<span data-ttu-id="6e984-239">Пример.</span><span class="sxs-lookup"><span data-stu-id="6e984-239">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="6e984-240">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="6e984-240">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="6e984-241">Указывает, использует ли сборщик мусора [группы ЦП](/windows/win32/procthread/processor-groups).</span><span class="sxs-lookup"><span data-stu-id="6e984-241">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="6e984-242">Когда 64-разрядный компьютер с Windows имеет несколько групп ЦП, то есть доступно более 64 процессоров, включение этого элемента расширяет действие сборки мусора на все группы ЦП.</span><span class="sxs-lookup"><span data-stu-id="6e984-242">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="6e984-243">Сборщик мусора использует все ядра для создания и балансировки куч.</span><span class="sxs-lookup"><span data-stu-id="6e984-243">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="6e984-244">Применяется только к сборке мусора сервера в 64-разрядных операционных системах Windows.</span><span class="sxs-lookup"><span data-stu-id="6e984-244">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="6e984-245">По умолчанию: отключено (`0`).</span><span class="sxs-lookup"><span data-stu-id="6e984-245">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="6e984-246">Дополнительные сведения см. в записи об [улучшении конфигурации ЦП для сборки мусора на компьютерах, имеющих более 64 ЦП](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/), в блоге Майони Стивенс (Maoni Stephens).</span><span class="sxs-lookup"><span data-stu-id="6e984-246">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="6e984-247">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="6e984-247">Setting name</span></span> | <span data-ttu-id="6e984-248">Значения</span><span class="sxs-lookup"><span data-stu-id="6e984-248">Values</span></span> | <span data-ttu-id="6e984-249">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="6e984-249">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6e984-250">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="6e984-250">**runtimeconfig.json**</span></span> | <span data-ttu-id="6e984-251">Н/Д</span><span class="sxs-lookup"><span data-stu-id="6e984-251">N/A</span></span> | <span data-ttu-id="6e984-252">Н/Д</span><span class="sxs-lookup"><span data-stu-id="6e984-252">N/A</span></span> | <span data-ttu-id="6e984-253">Н/Д</span><span class="sxs-lookup"><span data-stu-id="6e984-253">N/A</span></span> |
| <span data-ttu-id="6e984-254">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="6e984-254">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="6e984-255">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="6e984-255">`0` - disabled</span></span><br/><span data-ttu-id="6e984-256">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="6e984-256">`1` - enabled</span></span> | <span data-ttu-id="6e984-257">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="6e984-257">.NET Core 1.0</span></span> |
| <span data-ttu-id="6e984-258">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="6e984-258">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="6e984-259">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="6e984-259">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="6e984-260">`false` — отключено</span><span class="sxs-lookup"><span data-stu-id="6e984-260">`false` - disabled</span></span><br/><span data-ttu-id="6e984-261">`true` — включено</span><span class="sxs-lookup"><span data-stu-id="6e984-261">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="6e984-262">Чтобы настроить среду CLR для распределения потоков из пула потоков по всем группам ЦП, включите параметр [Элемент Thread_UseAllCpuGroups](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md).</span><span class="sxs-lookup"><span data-stu-id="6e984-262">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="6e984-263">Для приложений .NET Core этот параметр можно включить, задав для переменной среды `COMPlus_Thread_UseAllCpuGroups` значение `1`.</span><span class="sxs-lookup"><span data-stu-id="6e984-263">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="6e984-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="6e984-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="6e984-265">Указывает, следует ли *реализовать сходство* потоков сборки мусора с процессорами.</span><span class="sxs-lookup"><span data-stu-id="6e984-265">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="6e984-266">Реализация сходства потока сборки мусора означает, что он может выполняться только на определенном ЦП.</span><span class="sxs-lookup"><span data-stu-id="6e984-266">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="6e984-267">Куча создается для каждого потока сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="6e984-267">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="6e984-268">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="6e984-268">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="6e984-269">По умолчанию: реализация сходства потоков сборки мусора с процессорами (`false`).</span><span class="sxs-lookup"><span data-stu-id="6e984-269">Default: Affinitize garbage collection threads with processors (`false`).</span></span>

| | <span data-ttu-id="6e984-270">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="6e984-270">Setting name</span></span> | <span data-ttu-id="6e984-271">Значения</span><span class="sxs-lookup"><span data-stu-id="6e984-271">Values</span></span> | <span data-ttu-id="6e984-272">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="6e984-272">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6e984-273">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="6e984-273">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="6e984-274">`false` — реализовать сходство</span><span class="sxs-lookup"><span data-stu-id="6e984-274">`false` - affinitize</span></span><br/><span data-ttu-id="6e984-275">`true` — не реализовывать сходство</span><span class="sxs-lookup"><span data-stu-id="6e984-275">`true` - don't affinitize</span></span> | <span data-ttu-id="6e984-276">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6e984-276">.NET Core 3.0</span></span> |
| <span data-ttu-id="6e984-277">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="6e984-277">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="6e984-278">`0` — реализовать сходство</span><span class="sxs-lookup"><span data-stu-id="6e984-278">`0` - affinitize</span></span><br/><span data-ttu-id="6e984-279">`1` — не реализовывать сходство</span><span class="sxs-lookup"><span data-stu-id="6e984-279">`1` - don't affinitize</span></span> | <span data-ttu-id="6e984-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6e984-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="6e984-281">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="6e984-281">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="6e984-282">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="6e984-282">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="6e984-283">`false` — реализовать сходство</span><span class="sxs-lookup"><span data-stu-id="6e984-283">`false` - affinitize</span></span><br/><span data-ttu-id="6e984-284">`true` — не реализовывать сходство</span><span class="sxs-lookup"><span data-stu-id="6e984-284">`true` - don't affinitize</span></span> | <span data-ttu-id="6e984-285">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="6e984-285">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="6e984-286">Пример.</span><span class="sxs-lookup"><span data-stu-id="6e984-286">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="6e984-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="6e984-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="6e984-288">Указывает максимальный размер фиксации в байтах для кучи сборки мусора и учета сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="6e984-288">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>

| | <span data-ttu-id="6e984-289">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="6e984-289">Setting name</span></span> | <span data-ttu-id="6e984-290">Значения</span><span class="sxs-lookup"><span data-stu-id="6e984-290">Values</span></span> | <span data-ttu-id="6e984-291">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="6e984-291">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6e984-292">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="6e984-292">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="6e984-293">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="6e984-293">*decimal value*</span></span> | <span data-ttu-id="6e984-294">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6e984-294">.NET Core 3.0</span></span> |
| <span data-ttu-id="6e984-295">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="6e984-295">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="6e984-296">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="6e984-296">*hexadecimal value*</span></span> | <span data-ttu-id="6e984-297">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6e984-297">.NET Core 3.0</span></span> |

<span data-ttu-id="6e984-298">Пример.</span><span class="sxs-lookup"><span data-stu-id="6e984-298">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapHardLimit": 209715200
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="6e984-299">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="6e984-299">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="6e984-300">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="6e984-300">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="6e984-301">Например, чтобы задать для куч жесткое ограничение в 200 мебибайт (Миб), для JSON-файла нужно указать значение 209715200, а для переменной среды — значение 0xC800000 или C800000.</span><span class="sxs-lookup"><span data-stu-id="6e984-301">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="6e984-302">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="6e984-302">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="6e984-303">Указывает использование кучи сборки мусора в процентах от общего объема памяти.</span><span class="sxs-lookup"><span data-stu-id="6e984-303">Specifies the GC heap usage as a percentage of the total memory.</span></span>

| | <span data-ttu-id="6e984-304">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="6e984-304">Setting name</span></span> | <span data-ttu-id="6e984-305">Значения</span><span class="sxs-lookup"><span data-stu-id="6e984-305">Values</span></span> | <span data-ttu-id="6e984-306">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="6e984-306">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6e984-307">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="6e984-307">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="6e984-308">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="6e984-308">*decimal value*</span></span> | <span data-ttu-id="6e984-309">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6e984-309">.NET Core 3.0</span></span> |
| <span data-ttu-id="6e984-310">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="6e984-310">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="6e984-311">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="6e984-311">*hexadecimal value*</span></span> | <span data-ttu-id="6e984-312">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6e984-312">.NET Core 3.0</span></span> |

<span data-ttu-id="6e984-313">Пример.</span><span class="sxs-lookup"><span data-stu-id="6e984-313">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapHardLimitPercent": 30
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="6e984-314">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="6e984-314">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="6e984-315">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="6e984-315">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="6e984-316">Например, чтобы ограничить использование кучи значением 30 %, для JSON-файла нужно указать 30, а для переменной среды — 0x1E или 1E.</span><span class="sxs-lookup"><span data-stu-id="6e984-316">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="6e984-317">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="6e984-317">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="6e984-318">Настраивает, будут ли удаляемые сегменты помещаться в список ожидания для будущего использования или возвращаться операционной системе (ОС).</span><span class="sxs-lookup"><span data-stu-id="6e984-318">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="6e984-319">По умолчанию: возвращение сегментов операционной системе (`false`).</span><span class="sxs-lookup"><span data-stu-id="6e984-319">Default: Release segments back to the operating system (`false`).</span></span>

| | <span data-ttu-id="6e984-320">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="6e984-320">Setting name</span></span> | <span data-ttu-id="6e984-321">Значения</span><span class="sxs-lookup"><span data-stu-id="6e984-321">Values</span></span> | <span data-ttu-id="6e984-322">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="6e984-322">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6e984-323">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="6e984-323">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="6e984-324">`false` — возвращение операционной системе</span><span class="sxs-lookup"><span data-stu-id="6e984-324">`false` - release to OS</span></span><br/><span data-ttu-id="6e984-325">`true` — помещение в режим ожидания</span><span class="sxs-lookup"><span data-stu-id="6e984-325">`true` - put on standby</span></span> | <span data-ttu-id="6e984-326">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="6e984-326">.NET Core 1.0</span></span> |
| <span data-ttu-id="6e984-327">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="6e984-327">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="6e984-328">`false` — возвращение операционной системе</span><span class="sxs-lookup"><span data-stu-id="6e984-328">`false` - release to OS</span></span><br/><span data-ttu-id="6e984-329">`true` — помещение в режим ожидания</span><span class="sxs-lookup"><span data-stu-id="6e984-329">`true` - put on standby</span></span> | <span data-ttu-id="6e984-330">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="6e984-330">.NET Core 1.0</span></span> |
| <span data-ttu-id="6e984-331">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="6e984-331">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="6e984-332">`0` — возвращение операционной системе</span><span class="sxs-lookup"><span data-stu-id="6e984-332">`0` - release to OS</span></span><br/><span data-ttu-id="6e984-333">`1` — помещение в режим ожидания</span><span class="sxs-lookup"><span data-stu-id="6e984-333">`1` - put on standby</span></span> | <span data-ttu-id="6e984-334">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="6e984-334">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="6e984-335">Примеры</span><span class="sxs-lookup"><span data-stu-id="6e984-335">Examples</span></span>

<span data-ttu-id="6e984-336">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="6e984-336">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="6e984-337">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="6e984-337">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="6e984-338">Большие страницы</span><span class="sxs-lookup"><span data-stu-id="6e984-338">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="6e984-339">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="6e984-339">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="6e984-340">Указывает, следует ли использовать большие страницы, когда задано жесткое ограничение куч.</span><span class="sxs-lookup"><span data-stu-id="6e984-340">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="6e984-341">По умолчанию: отключено (`0`).</span><span class="sxs-lookup"><span data-stu-id="6e984-341">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="6e984-342">Это экспериментальный параметр.</span><span class="sxs-lookup"><span data-stu-id="6e984-342">This is an experimental setting.</span></span>

| | <span data-ttu-id="6e984-343">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="6e984-343">Setting name</span></span> | <span data-ttu-id="6e984-344">Значения</span><span class="sxs-lookup"><span data-stu-id="6e984-344">Values</span></span> | <span data-ttu-id="6e984-345">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="6e984-345">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6e984-346">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="6e984-346">**runtimeconfig.json**</span></span> | <span data-ttu-id="6e984-347">Н/Д</span><span class="sxs-lookup"><span data-stu-id="6e984-347">N/A</span></span> | <span data-ttu-id="6e984-348">Н/Д</span><span class="sxs-lookup"><span data-stu-id="6e984-348">N/A</span></span> | <span data-ttu-id="6e984-349">Н/Д</span><span class="sxs-lookup"><span data-stu-id="6e984-349">N/A</span></span> |
| <span data-ttu-id="6e984-350">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="6e984-350">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="6e984-351">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="6e984-351">`0` - disabled</span></span><br/><span data-ttu-id="6e984-352">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="6e984-352">`1` - enabled</span></span> | <span data-ttu-id="6e984-353">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6e984-353">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="6e984-354">Большие объекты</span><span class="sxs-lookup"><span data-stu-id="6e984-354">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="6e984-355">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="6e984-355">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="6e984-356">Настраивает для сборщика мусора на 64-разрядных платформах поддержку массивов, размер которых превышает 2 гигабайта (ГБ).</span><span class="sxs-lookup"><span data-stu-id="6e984-356">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="6e984-357">По умолчанию: включено (`1`).</span><span class="sxs-lookup"><span data-stu-id="6e984-357">Default: Enabled (`1`).</span></span>
- <span data-ttu-id="6e984-358">В будущей версии .NET этот параметр может быть объявлен устаревшим.</span><span class="sxs-lookup"><span data-stu-id="6e984-358">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="6e984-359">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="6e984-359">Setting name</span></span> | <span data-ttu-id="6e984-360">Значения</span><span class="sxs-lookup"><span data-stu-id="6e984-360">Values</span></span> | <span data-ttu-id="6e984-361">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="6e984-361">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6e984-362">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="6e984-362">**runtimeconfig.json**</span></span> | <span data-ttu-id="6e984-363">Н/Д</span><span class="sxs-lookup"><span data-stu-id="6e984-363">N/A</span></span> | <span data-ttu-id="6e984-364">Н/Д</span><span class="sxs-lookup"><span data-stu-id="6e984-364">N/A</span></span> | <span data-ttu-id="6e984-365">Н/Д</span><span class="sxs-lookup"><span data-stu-id="6e984-365">N/A</span></span> |
| <span data-ttu-id="6e984-366">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="6e984-366">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="6e984-367">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="6e984-367">`1` - enabled</span></span><br/> <span data-ttu-id="6e984-368">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="6e984-368">`0` - disabled</span></span> | <span data-ttu-id="6e984-369">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="6e984-369">.NET Core 1.0</span></span> |
| <span data-ttu-id="6e984-370">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="6e984-370">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="6e984-371">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="6e984-371">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="6e984-372">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="6e984-372">`1` - enabled</span></span><br/> <span data-ttu-id="6e984-373">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="6e984-373">`0` - disabled</span></span> | <span data-ttu-id="6e984-374">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="6e984-374">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="6e984-375">Пороговое значение кучи больших объектов</span><span class="sxs-lookup"><span data-stu-id="6e984-375">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="6e984-376">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="6e984-376">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="6e984-377">Указывает пороговый размер (в байтах), при котором объекты попадают в кучу больших объектов (LOH).</span><span class="sxs-lookup"><span data-stu-id="6e984-377">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="6e984-378">Пороговое значение по умолчанию — 85 000 байт.</span><span class="sxs-lookup"><span data-stu-id="6e984-378">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="6e984-379">Указанное значение должно быть больше порогового значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6e984-379">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="6e984-380">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="6e984-380">Setting name</span></span> | <span data-ttu-id="6e984-381">Значения</span><span class="sxs-lookup"><span data-stu-id="6e984-381">Values</span></span> | <span data-ttu-id="6e984-382">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="6e984-382">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6e984-383">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="6e984-383">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="6e984-384">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="6e984-384">*decimal value*</span></span> | <span data-ttu-id="6e984-385">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="6e984-385">.NET Core 1.0</span></span> |
| <span data-ttu-id="6e984-386">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="6e984-386">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="6e984-387">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="6e984-387">*hexadecimal value*</span></span> | <span data-ttu-id="6e984-388">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="6e984-388">.NET Core 1.0</span></span> |
| <span data-ttu-id="6e984-389">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="6e984-389">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="6e984-390">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="6e984-390">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="6e984-391">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="6e984-391">*decimal value*</span></span> | <span data-ttu-id="6e984-392">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="6e984-392">.NET Framework 4.8</span></span> |

<span data-ttu-id="6e984-393">Пример.</span><span class="sxs-lookup"><span data-stu-id="6e984-393">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.LOHThreshold": 120000
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="6e984-394">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="6e984-394">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="6e984-395">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="6e984-395">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="6e984-396">Например, чтобы задать порог размера в 120 000 байт, для JSON-файла нужно указать значение 120000, а для переменной среды — значение 0x1D4C0 или 1D4C0.</span><span class="sxs-lookup"><span data-stu-id="6e984-396">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="6e984-397">Автономный сборщик мусора</span><span class="sxs-lookup"><span data-stu-id="6e984-397">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="6e984-398">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="6e984-398">COMPlus_GCName</span></span>

- <span data-ttu-id="6e984-399">Указывает путь к библиотеке, содержащей сборщик мусора, который среда выполнения намеревается загрузить.</span><span class="sxs-lookup"><span data-stu-id="6e984-399">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="6e984-400">Дополнительные сведения см. в статье [Проектирования загрузчика автономного сборщика мусора](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span><span class="sxs-lookup"><span data-stu-id="6e984-400">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="6e984-401">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="6e984-401">Setting name</span></span> | <span data-ttu-id="6e984-402">Значения</span><span class="sxs-lookup"><span data-stu-id="6e984-402">Values</span></span> | <span data-ttu-id="6e984-403">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="6e984-403">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6e984-404">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="6e984-404">**runtimeconfig.json**</span></span> | <span data-ttu-id="6e984-405">Н/Д</span><span class="sxs-lookup"><span data-stu-id="6e984-405">N/A</span></span> | <span data-ttu-id="6e984-406">Н/Д</span><span class="sxs-lookup"><span data-stu-id="6e984-406">N/A</span></span> | <span data-ttu-id="6e984-407">Н/Д</span><span class="sxs-lookup"><span data-stu-id="6e984-407">N/A</span></span> |
| <span data-ttu-id="6e984-408">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="6e984-408">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="6e984-409">*string_path*</span><span class="sxs-lookup"><span data-stu-id="6e984-409">*string_path*</span></span> | <span data-ttu-id="6e984-410">.NET Core 2.0;</span><span class="sxs-lookup"><span data-stu-id="6e984-410">.NET Core 2.0</span></span> |
