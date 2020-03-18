---
title: Параметры конфигурации сборщика мусора
description: Сведения о параметрах времени выполнения, определяющих, как сборщик мусора управляет памятью для приложений .NET Core.
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: 044083d69601f5092724a46d358b2ee5673d428d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "76733517"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="439be-103">Параметры конфигурации времени выполнения для сборки мусора</span><span class="sxs-lookup"><span data-stu-id="439be-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="439be-104">Эта страница содержит сведения о параметрах сборщика мусора (GC), которые можно изменить во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="439be-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="439be-105">Если вы пытаетесь добиться пиковой производительности запущенных приложений, рекомендуется использовать эти параметры.</span><span class="sxs-lookup"><span data-stu-id="439be-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="439be-106">Однако значения по умолчанию обеспечивают оптимальную производительность для большинства приложений в типичных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="439be-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="439be-107">На этой странице параметры упорядочены по группам.</span><span class="sxs-lookup"><span data-stu-id="439be-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="439be-108">Параметры в каждой группе обычно используются совместно друг с другом для достижения определенного результата.</span><span class="sxs-lookup"><span data-stu-id="439be-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="439be-109">Эти параметры также могут динамически изменяться приложением во время его выполнения, поэтому любые заданные параметры времени выполнения могут быть переопределены.</span><span class="sxs-lookup"><span data-stu-id="439be-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="439be-110">Некоторые параметры, такие как [уровень задержки](../../standard/garbage-collection/latency.md), обычно задаются только через API во время разработки.</span><span class="sxs-lookup"><span data-stu-id="439be-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="439be-111">Такие параметры будут пропущены на этой странице.</span><span class="sxs-lookup"><span data-stu-id="439be-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="439be-112">Для числовых значений используйте десятичную нотацию для параметров в файле *runtimeconfig.json* и шестнадцатеричную нотацию для параметров переменных среды.</span><span class="sxs-lookup"><span data-stu-id="439be-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="439be-113">Шестнадцатеричные значения можно указать с помощью префикса "0x" или без него.</span><span class="sxs-lookup"><span data-stu-id="439be-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="439be-114">Варианты сборки мусора</span><span class="sxs-lookup"><span data-stu-id="439be-114">Flavors of garbage collection</span></span>

<span data-ttu-id="439be-115">Два основных варианта сборки мусора — это сборка мусора рабочей станции и сборка мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="439be-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="439be-116">Дополнительные сведения о различиях между этими двумя вариантами см. в статье [Основы сборки мусора](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span><span class="sxs-lookup"><span data-stu-id="439be-116">For more information about differences between the two, see [Fundamentals of garbage collection](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span></span>

<span data-ttu-id="439be-117">Подвиды сборки мусора представлены фоновым и непараллельным выполнением.</span><span class="sxs-lookup"><span data-stu-id="439be-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="439be-118">Чтобы выбрать варианты сборки мусора, используйте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="439be-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="439be-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="439be-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="439be-120">Указывает, использует ли приложение сборку мусора рабочей станции или сборку мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="439be-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="439be-121">По умолчанию: сборка мусора рабочей станции (`false`).</span><span class="sxs-lookup"><span data-stu-id="439be-121">Default: Workstation garbage collection (`false`).</span></span>

| | <span data-ttu-id="439be-122">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="439be-122">Setting name</span></span> | <span data-ttu-id="439be-123">Значения</span><span class="sxs-lookup"><span data-stu-id="439be-123">Values</span></span> | <span data-ttu-id="439be-124">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="439be-124">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="439be-125">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="439be-125">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="439be-126">`false` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="439be-126">`false` - workstation</span></span><br/><span data-ttu-id="439be-127">`true` — сервер</span><span class="sxs-lookup"><span data-stu-id="439be-127">`true` - server</span></span> | <span data-ttu-id="439be-128">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="439be-128">.NET Core 1.0</span></span> |
| <span data-ttu-id="439be-129">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="439be-129">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="439be-130">`false` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="439be-130">`false` - workstation</span></span><br/><span data-ttu-id="439be-131">`true` — сервер</span><span class="sxs-lookup"><span data-stu-id="439be-131">`true` - server</span></span> | <span data-ttu-id="439be-132">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="439be-132">.NET Core 1.0</span></span> |
| <span data-ttu-id="439be-133">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="439be-133">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="439be-134">`0` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="439be-134">`0` - workstation</span></span><br/><span data-ttu-id="439be-135">`1` — сервер</span><span class="sxs-lookup"><span data-stu-id="439be-135">`1` - server</span></span> | <span data-ttu-id="439be-136">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="439be-136">.NET Core 1.0</span></span> |
| <span data-ttu-id="439be-137">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="439be-137">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="439be-138">GCServer</span><span class="sxs-lookup"><span data-stu-id="439be-138">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="439be-139">`false` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="439be-139">`false` - workstation</span></span><br/><span data-ttu-id="439be-140">`true` — сервер</span><span class="sxs-lookup"><span data-stu-id="439be-140">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="439be-141">Примеры</span><span class="sxs-lookup"><span data-stu-id="439be-141">Examples</span></span>

<span data-ttu-id="439be-142">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="439be-142">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="439be-143">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="439be-143">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="439be-144">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="439be-144">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="439be-145">Указывает, включена ли фоновая (параллельная) сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="439be-145">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="439be-146">По умолчанию: включено (`true`).</span><span class="sxs-lookup"><span data-stu-id="439be-146">Default: Enabled (`true`).</span></span>
- <span data-ttu-id="439be-147">Дополнительные сведения см. в статьях [Фоновая сборка мусора](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) и [Фоновая сборка мусора сервера](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span><span class="sxs-lookup"><span data-stu-id="439be-147">For more information, see [Background garbage collection](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) and [Background server garbage collection](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span></span>

| | <span data-ttu-id="439be-148">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="439be-148">Setting name</span></span> | <span data-ttu-id="439be-149">Значения</span><span class="sxs-lookup"><span data-stu-id="439be-149">Values</span></span> | <span data-ttu-id="439be-150">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="439be-150">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="439be-151">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="439be-151">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="439be-152">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="439be-152">`true` - background GC</span></span><br/><span data-ttu-id="439be-153">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="439be-153">`false` - non-concurrent GC</span></span> | <span data-ttu-id="439be-154">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="439be-154">.NET Core 1.0</span></span> |
| <span data-ttu-id="439be-155">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="439be-155">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="439be-156">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="439be-156">`true` - background GC</span></span><br/><span data-ttu-id="439be-157">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="439be-157">`false` - non-concurrent GC</span></span> | <span data-ttu-id="439be-158">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="439be-158">.NET Core 1.0</span></span> |
| <span data-ttu-id="439be-159">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="439be-159">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="439be-160">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="439be-160">`true` - background GC</span></span><br/><span data-ttu-id="439be-161">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="439be-161">`false` - non-concurrent GC</span></span> | <span data-ttu-id="439be-162">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="439be-162">.NET Core 1.0</span></span> |
| <span data-ttu-id="439be-163">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="439be-163">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="439be-164">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="439be-164">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="439be-165">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="439be-165">`true` - background GC</span></span><br/><span data-ttu-id="439be-166">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="439be-166">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="439be-167">Примеры</span><span class="sxs-lookup"><span data-stu-id="439be-167">Examples</span></span>

<span data-ttu-id="439be-168">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="439be-168">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="439be-169">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="439be-169">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="439be-170">Управление использованием ресурсов</span><span class="sxs-lookup"><span data-stu-id="439be-170">Manage resource usage</span></span>

<span data-ttu-id="439be-171">Используйте параметры, описанные в этом разделе, для управления использованием памяти и ЦП в сборщике мусора.</span><span class="sxs-lookup"><span data-stu-id="439be-171">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="439be-172">Дополнительные сведения о некоторых из этих параметров см. в записи блога о [компромиссе между сборкой мусора рабочей станции и сервера](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/).</span><span class="sxs-lookup"><span data-stu-id="439be-172">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="439be-173">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="439be-173">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="439be-174">Ограничивает число куч, создаваемых сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="439be-174">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="439be-175">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="439be-175">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="439be-176">Если включено сходство процессоров сборки мусора, что используется по умолчанию, параметр счетчика куч реализует сходство `n` куч/потоков сборки мусора с первыми `n` процессорами.</span><span class="sxs-lookup"><span data-stu-id="439be-176">If GC processor affinity is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="439be-177">(Используйте параметры сходства маски или сходства диапазонов, чтобы указать, для каких именно процессоров следует реализовать сходство.)</span><span class="sxs-lookup"><span data-stu-id="439be-177">(Use the affinitize mask or affinitize ranges settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="439be-178">Если сходство процессоров сборки мусора отключено, этот параметр будет ограничивать количество куч сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="439be-178">If GC processor affinity is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="439be-179">Дополнительные сведения см. в [примечаниях по GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="439be-179">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="439be-180">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="439be-180">Setting name</span></span> | <span data-ttu-id="439be-181">Значения</span><span class="sxs-lookup"><span data-stu-id="439be-181">Values</span></span> | <span data-ttu-id="439be-182">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="439be-182">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="439be-183">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="439be-183">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="439be-184">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="439be-184">*decimal value*</span></span> | <span data-ttu-id="439be-185">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="439be-185">.NET Core 3.0</span></span> |
| <span data-ttu-id="439be-186">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="439be-186">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="439be-187">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="439be-187">*hexadecimal value*</span></span> | <span data-ttu-id="439be-188">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="439be-188">.NET Core 3.0</span></span> |
| <span data-ttu-id="439be-189">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="439be-189">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="439be-190">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="439be-190">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="439be-191">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="439be-191">*decimal value*</span></span> | <span data-ttu-id="439be-192">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="439be-192">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="439be-193">Пример.</span><span class="sxs-lookup"><span data-stu-id="439be-193">Example:</span></span>

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
> <span data-ttu-id="439be-194">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="439be-194">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="439be-195">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="439be-195">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="439be-196">Например, чтобы ограничить число куч значением 16, для JSON-файла нужно указать 16, а для переменной среды — 0x10 или 10.</span><span class="sxs-lookup"><span data-stu-id="439be-196">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="439be-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="439be-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="439be-198">Указывает конкретные процессоры, которые должны использоваться потоками сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="439be-198">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="439be-199">Если сходство процессоров отключено посредством задания значения `true` для `System.GC.NoAffinitize`, этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="439be-199">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="439be-200">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="439be-200">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="439be-201">Это значение представляет собой битовую маску, которая определяет доступные процессу процессоры.</span><span class="sxs-lookup"><span data-stu-id="439be-201">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="439be-202">Например, десятичное значение 1023 (или шестнадцатеричное значение 0x3FF или 3FF, если вы используете переменную среды), равно 0011 1111 1111 в двоичной нотации.</span><span class="sxs-lookup"><span data-stu-id="439be-202">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="439be-203">При этом будут использоваться первые 10 процессоров.</span><span class="sxs-lookup"><span data-stu-id="439be-203">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="439be-204">Чтобы указать следующие 10 процессоров, то есть процессоры 10–19, задайте десятичное значение 1047552 (или шестнадцатеричное значение 0xFFC00 или FFC00), которое эквивалентно двоичному значению 1111 1111 1100 0000 0000.</span><span class="sxs-lookup"><span data-stu-id="439be-204">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="439be-205">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="439be-205">Setting name</span></span> | <span data-ttu-id="439be-206">Значения</span><span class="sxs-lookup"><span data-stu-id="439be-206">Values</span></span> | <span data-ttu-id="439be-207">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="439be-207">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="439be-208">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="439be-208">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="439be-209">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="439be-209">*decimal value*</span></span> | <span data-ttu-id="439be-210">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="439be-210">.NET Core 3.0</span></span> |
| <span data-ttu-id="439be-211">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="439be-211">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="439be-212">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="439be-212">*hexadecimal value*</span></span> | <span data-ttu-id="439be-213">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="439be-213">.NET Core 3.0</span></span> |
| <span data-ttu-id="439be-214">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="439be-214">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="439be-215">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="439be-215">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="439be-216">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="439be-216">*decimal value*</span></span> | <span data-ttu-id="439be-217">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="439be-217">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="439be-218">Пример.</span><span class="sxs-lookup"><span data-stu-id="439be-218">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="439be-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="439be-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="439be-220">Указывает список процессоров, используемых для потоков сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="439be-220">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="439be-221">Этот параметр аналогичен `System.GC.HeapAffinitizeMask`, за исключением того, что он позволяет указать больше 64 процессоров.</span><span class="sxs-lookup"><span data-stu-id="439be-221">This setting is similar to `System.GC.HeapAffinitizeMask`, except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="439be-222">Для операционных систем Windows добавьте к номеру или диапазону процессоров префикс в виде соответствующей [группы ЦП](/windows/win32/procthread/processor-groups), например "0:1-10,0:12,1:50-52,1:70".</span><span class="sxs-lookup"><span data-stu-id="439be-222">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="439be-223">Если сходство процессоров отключено посредством задания значения `true` для `System.GC.NoAffinitize`, этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="439be-223">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="439be-224">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="439be-224">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="439be-225">Дополнительные сведения см. в записи об [улучшении конфигурации ЦП для сборки мусора на компьютерах, имеющих более 64 ЦП](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/), в блоге Майони Стивенс (Maoni Stephens).</span><span class="sxs-lookup"><span data-stu-id="439be-225">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="439be-226">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="439be-226">Setting name</span></span> | <span data-ttu-id="439be-227">Значения</span><span class="sxs-lookup"><span data-stu-id="439be-227">Values</span></span> | <span data-ttu-id="439be-228">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="439be-228">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="439be-229">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="439be-229">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="439be-230">Разделенный запятыми список номеров процессоров или диапазонов номеров процессоров.</span><span class="sxs-lookup"><span data-stu-id="439be-230">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="439be-231">Пример для Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="439be-231">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="439be-232">Пример для Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="439be-232">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="439be-233">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="439be-233">.NET Core 3.0</span></span> |
| <span data-ttu-id="439be-234">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="439be-234">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="439be-235">Разделенный запятыми список номеров процессоров или диапазонов номеров процессоров.</span><span class="sxs-lookup"><span data-stu-id="439be-235">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="439be-236">Пример для Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="439be-236">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="439be-237">Пример для Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="439be-237">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="439be-238">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="439be-238">.NET Core 3.0</span></span> |

<span data-ttu-id="439be-239">Пример.</span><span class="sxs-lookup"><span data-stu-id="439be-239">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="439be-240">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="439be-240">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="439be-241">Указывает, использует ли сборщик мусора [группы ЦП](/windows/win32/procthread/processor-groups).</span><span class="sxs-lookup"><span data-stu-id="439be-241">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="439be-242">Когда 64-разрядный компьютер с Windows имеет несколько групп ЦП, то есть доступно более 64 процессоров, включение этого элемента расширяет действие сборки мусора на все группы ЦП.</span><span class="sxs-lookup"><span data-stu-id="439be-242">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="439be-243">Сборщик мусора использует все ядра для создания и балансировки куч.</span><span class="sxs-lookup"><span data-stu-id="439be-243">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="439be-244">Применяется только к сборке мусора сервера в 64-разрядных операционных системах Windows.</span><span class="sxs-lookup"><span data-stu-id="439be-244">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="439be-245">По умолчанию: отключено (`0`).</span><span class="sxs-lookup"><span data-stu-id="439be-245">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="439be-246">Дополнительные сведения см. в записи об [улучшении конфигурации ЦП для сборки мусора на компьютерах, имеющих более 64 ЦП](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/), в блоге Майони Стивенс (Maoni Stephens).</span><span class="sxs-lookup"><span data-stu-id="439be-246">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="439be-247">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="439be-247">Setting name</span></span> | <span data-ttu-id="439be-248">Значения</span><span class="sxs-lookup"><span data-stu-id="439be-248">Values</span></span> | <span data-ttu-id="439be-249">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="439be-249">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="439be-250">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="439be-250">**runtimeconfig.json**</span></span> | <span data-ttu-id="439be-251">Н/Д</span><span class="sxs-lookup"><span data-stu-id="439be-251">N/A</span></span> | <span data-ttu-id="439be-252">Н/Д</span><span class="sxs-lookup"><span data-stu-id="439be-252">N/A</span></span> | <span data-ttu-id="439be-253">Н/Д</span><span class="sxs-lookup"><span data-stu-id="439be-253">N/A</span></span> |
| <span data-ttu-id="439be-254">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="439be-254">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="439be-255">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="439be-255">`0` - disabled</span></span><br/><span data-ttu-id="439be-256">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="439be-256">`1` - enabled</span></span> | <span data-ttu-id="439be-257">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="439be-257">.NET Core 1.0</span></span> |
| <span data-ttu-id="439be-258">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="439be-258">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="439be-259">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="439be-259">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="439be-260">`false` — отключено</span><span class="sxs-lookup"><span data-stu-id="439be-260">`false` - disabled</span></span><br/><span data-ttu-id="439be-261">`true` — включено</span><span class="sxs-lookup"><span data-stu-id="439be-261">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="439be-262">Чтобы настроить среду CLR для распределения потоков из пула потоков по всем группам ЦП, включите параметр [Элемент Thread_UseAllCpuGroups](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md).</span><span class="sxs-lookup"><span data-stu-id="439be-262">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="439be-263">Для приложений .NET Core этот параметр можно включить, задав для переменной среды `COMPlus_Thread_UseAllCpuGroups` значение `1`.</span><span class="sxs-lookup"><span data-stu-id="439be-263">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="439be-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="439be-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="439be-265">Указывает, следует ли *реализовать сходство* потоков сборки мусора с процессорами.</span><span class="sxs-lookup"><span data-stu-id="439be-265">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="439be-266">Реализация сходства потока сборки мусора означает, что он может выполняться только на определенном ЦП.</span><span class="sxs-lookup"><span data-stu-id="439be-266">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="439be-267">Куча создается для каждого потока сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="439be-267">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="439be-268">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="439be-268">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="439be-269">По умолчанию: реализация сходства потоков сборки мусора с процессорами (`false`).</span><span class="sxs-lookup"><span data-stu-id="439be-269">Default: Affinitize garbage collection threads with processors (`false`).</span></span>

| | <span data-ttu-id="439be-270">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="439be-270">Setting name</span></span> | <span data-ttu-id="439be-271">Значения</span><span class="sxs-lookup"><span data-stu-id="439be-271">Values</span></span> | <span data-ttu-id="439be-272">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="439be-272">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="439be-273">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="439be-273">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="439be-274">`false` — реализовать сходство</span><span class="sxs-lookup"><span data-stu-id="439be-274">`false` - affinitize</span></span><br/><span data-ttu-id="439be-275">`true` — не реализовывать сходство</span><span class="sxs-lookup"><span data-stu-id="439be-275">`true` - don't affinitize</span></span> | <span data-ttu-id="439be-276">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="439be-276">.NET Core 3.0</span></span> |
| <span data-ttu-id="439be-277">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="439be-277">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="439be-278">`0` — реализовать сходство</span><span class="sxs-lookup"><span data-stu-id="439be-278">`0` - affinitize</span></span><br/><span data-ttu-id="439be-279">`1` — не реализовывать сходство</span><span class="sxs-lookup"><span data-stu-id="439be-279">`1` - don't affinitize</span></span> | <span data-ttu-id="439be-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="439be-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="439be-281">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="439be-281">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="439be-282">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="439be-282">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="439be-283">`false` — реализовать сходство</span><span class="sxs-lookup"><span data-stu-id="439be-283">`false` - affinitize</span></span><br/><span data-ttu-id="439be-284">`true` — не реализовывать сходство</span><span class="sxs-lookup"><span data-stu-id="439be-284">`true` - don't affinitize</span></span> | <span data-ttu-id="439be-285">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="439be-285">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="439be-286">Пример.</span><span class="sxs-lookup"><span data-stu-id="439be-286">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="439be-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="439be-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="439be-288">Указывает максимальный размер фиксации в байтах для кучи сборки мусора и учета сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="439be-288">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>

| | <span data-ttu-id="439be-289">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="439be-289">Setting name</span></span> | <span data-ttu-id="439be-290">Значения</span><span class="sxs-lookup"><span data-stu-id="439be-290">Values</span></span> | <span data-ttu-id="439be-291">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="439be-291">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="439be-292">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="439be-292">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="439be-293">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="439be-293">*decimal value*</span></span> | <span data-ttu-id="439be-294">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="439be-294">.NET Core 3.0</span></span> |
| <span data-ttu-id="439be-295">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="439be-295">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="439be-296">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="439be-296">*hexadecimal value*</span></span> | <span data-ttu-id="439be-297">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="439be-297">.NET Core 3.0</span></span> |

<span data-ttu-id="439be-298">Пример.</span><span class="sxs-lookup"><span data-stu-id="439be-298">Example:</span></span>

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
> <span data-ttu-id="439be-299">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="439be-299">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="439be-300">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="439be-300">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="439be-301">Например, чтобы задать для куч жесткое ограничение в 200 мебибайт (Миб), для JSON-файла нужно указать значение 209715200, а для переменной среды — значение 0xC800000 или C800000.</span><span class="sxs-lookup"><span data-stu-id="439be-301">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="439be-302">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="439be-302">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="439be-303">Указывает использование кучи сборки мусора в процентах от общего объема памяти.</span><span class="sxs-lookup"><span data-stu-id="439be-303">Specifies the GC heap usage as a percentage of the total memory.</span></span>

| | <span data-ttu-id="439be-304">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="439be-304">Setting name</span></span> | <span data-ttu-id="439be-305">Значения</span><span class="sxs-lookup"><span data-stu-id="439be-305">Values</span></span> | <span data-ttu-id="439be-306">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="439be-306">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="439be-307">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="439be-307">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="439be-308">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="439be-308">*decimal value*</span></span> | <span data-ttu-id="439be-309">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="439be-309">.NET Core 3.0</span></span> |
| <span data-ttu-id="439be-310">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="439be-310">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="439be-311">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="439be-311">*hexadecimal value*</span></span> | <span data-ttu-id="439be-312">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="439be-312">.NET Core 3.0</span></span> |

<span data-ttu-id="439be-313">Пример.</span><span class="sxs-lookup"><span data-stu-id="439be-313">Example:</span></span>

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
> <span data-ttu-id="439be-314">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="439be-314">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="439be-315">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="439be-315">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="439be-316">Например, чтобы ограничить использование кучи значением 30 %, для JSON-файла нужно указать 30, а для переменной среды — 0x1E или 1E.</span><span class="sxs-lookup"><span data-stu-id="439be-316">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="439be-317">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="439be-317">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="439be-318">Настраивает, будут ли удаляемые сегменты помещаться в список ожидания для будущего использования или возвращаться операционной системе (ОС).</span><span class="sxs-lookup"><span data-stu-id="439be-318">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="439be-319">По умолчанию: возвращение сегментов операционной системе (`false`).</span><span class="sxs-lookup"><span data-stu-id="439be-319">Default: Release segments back to the operating system (`false`).</span></span>

| | <span data-ttu-id="439be-320">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="439be-320">Setting name</span></span> | <span data-ttu-id="439be-321">Значения</span><span class="sxs-lookup"><span data-stu-id="439be-321">Values</span></span> | <span data-ttu-id="439be-322">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="439be-322">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="439be-323">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="439be-323">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="439be-324">`false` — возвращение операционной системе</span><span class="sxs-lookup"><span data-stu-id="439be-324">`false` - release to OS</span></span><br/><span data-ttu-id="439be-325">`true` — помещение в режим ожидания</span><span class="sxs-lookup"><span data-stu-id="439be-325">`true` - put on standby</span></span> | <span data-ttu-id="439be-326">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="439be-326">.NET Core 1.0</span></span> |
| <span data-ttu-id="439be-327">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="439be-327">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="439be-328">`false` — возвращение операционной системе</span><span class="sxs-lookup"><span data-stu-id="439be-328">`false` - release to OS</span></span><br/><span data-ttu-id="439be-329">`true` — помещение в режим ожидания</span><span class="sxs-lookup"><span data-stu-id="439be-329">`true` - put on standby</span></span> | <span data-ttu-id="439be-330">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="439be-330">.NET Core 1.0</span></span> |
| <span data-ttu-id="439be-331">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="439be-331">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="439be-332">`0` — возвращение операционной системе</span><span class="sxs-lookup"><span data-stu-id="439be-332">`0` - release to OS</span></span><br/><span data-ttu-id="439be-333">`1` — помещение в режим ожидания</span><span class="sxs-lookup"><span data-stu-id="439be-333">`1` - put on standby</span></span> | <span data-ttu-id="439be-334">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="439be-334">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="439be-335">Примеры</span><span class="sxs-lookup"><span data-stu-id="439be-335">Examples</span></span>

<span data-ttu-id="439be-336">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="439be-336">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="439be-337">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="439be-337">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="439be-338">Большие страницы</span><span class="sxs-lookup"><span data-stu-id="439be-338">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="439be-339">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="439be-339">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="439be-340">Указывает, следует ли использовать большие страницы, когда задано жесткое ограничение куч.</span><span class="sxs-lookup"><span data-stu-id="439be-340">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="439be-341">По умолчанию: отключено (`0`).</span><span class="sxs-lookup"><span data-stu-id="439be-341">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="439be-342">Это экспериментальный параметр.</span><span class="sxs-lookup"><span data-stu-id="439be-342">This is an experimental setting.</span></span>

| | <span data-ttu-id="439be-343">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="439be-343">Setting name</span></span> | <span data-ttu-id="439be-344">Значения</span><span class="sxs-lookup"><span data-stu-id="439be-344">Values</span></span> | <span data-ttu-id="439be-345">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="439be-345">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="439be-346">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="439be-346">**runtimeconfig.json**</span></span> | <span data-ttu-id="439be-347">Н/Д</span><span class="sxs-lookup"><span data-stu-id="439be-347">N/A</span></span> | <span data-ttu-id="439be-348">Н/Д</span><span class="sxs-lookup"><span data-stu-id="439be-348">N/A</span></span> | <span data-ttu-id="439be-349">Н/Д</span><span class="sxs-lookup"><span data-stu-id="439be-349">N/A</span></span> |
| <span data-ttu-id="439be-350">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="439be-350">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="439be-351">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="439be-351">`0` - disabled</span></span><br/><span data-ttu-id="439be-352">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="439be-352">`1` - enabled</span></span> | <span data-ttu-id="439be-353">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="439be-353">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="439be-354">Большие объекты</span><span class="sxs-lookup"><span data-stu-id="439be-354">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="439be-355">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="439be-355">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="439be-356">Настраивает для сборщика мусора на 64-разрядных платформах поддержку массивов, размер которых превышает 2 гигабайта (ГБ).</span><span class="sxs-lookup"><span data-stu-id="439be-356">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="439be-357">По умолчанию: включено (`1`).</span><span class="sxs-lookup"><span data-stu-id="439be-357">Default: Enabled (`1`).</span></span>
- <span data-ttu-id="439be-358">В будущей версии .NET этот параметр может быть объявлен устаревшим.</span><span class="sxs-lookup"><span data-stu-id="439be-358">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="439be-359">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="439be-359">Setting name</span></span> | <span data-ttu-id="439be-360">Значения</span><span class="sxs-lookup"><span data-stu-id="439be-360">Values</span></span> | <span data-ttu-id="439be-361">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="439be-361">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="439be-362">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="439be-362">**runtimeconfig.json**</span></span> | <span data-ttu-id="439be-363">Н/Д</span><span class="sxs-lookup"><span data-stu-id="439be-363">N/A</span></span> | <span data-ttu-id="439be-364">Н/Д</span><span class="sxs-lookup"><span data-stu-id="439be-364">N/A</span></span> | <span data-ttu-id="439be-365">Н/Д</span><span class="sxs-lookup"><span data-stu-id="439be-365">N/A</span></span> |
| <span data-ttu-id="439be-366">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="439be-366">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="439be-367">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="439be-367">`1` - enabled</span></span><br/> <span data-ttu-id="439be-368">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="439be-368">`0` - disabled</span></span> | <span data-ttu-id="439be-369">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="439be-369">.NET Core 1.0</span></span> |
| <span data-ttu-id="439be-370">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="439be-370">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="439be-371">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="439be-371">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="439be-372">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="439be-372">`1` - enabled</span></span><br/> <span data-ttu-id="439be-373">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="439be-373">`0` - disabled</span></span> | <span data-ttu-id="439be-374">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="439be-374">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="439be-375">Пороговое значение кучи больших объектов</span><span class="sxs-lookup"><span data-stu-id="439be-375">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="439be-376">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="439be-376">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="439be-377">Указывает пороговый размер (в байтах), при котором объекты попадают в кучу больших объектов (LOH).</span><span class="sxs-lookup"><span data-stu-id="439be-377">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="439be-378">Пороговое значение по умолчанию — 85 000 байт.</span><span class="sxs-lookup"><span data-stu-id="439be-378">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="439be-379">Указанное значение должно быть больше порогового значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="439be-379">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="439be-380">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="439be-380">Setting name</span></span> | <span data-ttu-id="439be-381">Значения</span><span class="sxs-lookup"><span data-stu-id="439be-381">Values</span></span> | <span data-ttu-id="439be-382">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="439be-382">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="439be-383">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="439be-383">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="439be-384">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="439be-384">*decimal value*</span></span> | <span data-ttu-id="439be-385">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="439be-385">.NET Core 1.0</span></span> |
| <span data-ttu-id="439be-386">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="439be-386">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="439be-387">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="439be-387">*hexadecimal value*</span></span> | <span data-ttu-id="439be-388">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="439be-388">.NET Core 1.0</span></span> |
| <span data-ttu-id="439be-389">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="439be-389">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="439be-390">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="439be-390">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="439be-391">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="439be-391">*decimal value*</span></span> | <span data-ttu-id="439be-392">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="439be-392">.NET Framework 4.8</span></span> |

<span data-ttu-id="439be-393">Пример.</span><span class="sxs-lookup"><span data-stu-id="439be-393">Example:</span></span>

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
> <span data-ttu-id="439be-394">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="439be-394">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="439be-395">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="439be-395">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="439be-396">Например, чтобы задать порог размера в 120 000 байт, для JSON-файла нужно указать значение 120000, а для переменной среды — значение 0x1D4C0 или 1D4C0.</span><span class="sxs-lookup"><span data-stu-id="439be-396">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="439be-397">Автономный сборщик мусора</span><span class="sxs-lookup"><span data-stu-id="439be-397">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="439be-398">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="439be-398">COMPlus_GCName</span></span>

- <span data-ttu-id="439be-399">Указывает путь к библиотеке, содержащей сборщик мусора, который среда выполнения намеревается загрузить.</span><span class="sxs-lookup"><span data-stu-id="439be-399">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="439be-400">Дополнительные сведения см. в статье [Проектирования загрузчика автономного сборщика мусора](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span><span class="sxs-lookup"><span data-stu-id="439be-400">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="439be-401">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="439be-401">Setting name</span></span> | <span data-ttu-id="439be-402">Значения</span><span class="sxs-lookup"><span data-stu-id="439be-402">Values</span></span> | <span data-ttu-id="439be-403">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="439be-403">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="439be-404">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="439be-404">**runtimeconfig.json**</span></span> | <span data-ttu-id="439be-405">Н/Д</span><span class="sxs-lookup"><span data-stu-id="439be-405">N/A</span></span> | <span data-ttu-id="439be-406">Н/Д</span><span class="sxs-lookup"><span data-stu-id="439be-406">N/A</span></span> | <span data-ttu-id="439be-407">Н/Д</span><span class="sxs-lookup"><span data-stu-id="439be-407">N/A</span></span> |
| <span data-ttu-id="439be-408">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="439be-408">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="439be-409">*string_path*</span><span class="sxs-lookup"><span data-stu-id="439be-409">*string_path*</span></span> | <span data-ttu-id="439be-410">.NET Core 2.0;</span><span class="sxs-lookup"><span data-stu-id="439be-410">.NET Core 2.0</span></span> |
