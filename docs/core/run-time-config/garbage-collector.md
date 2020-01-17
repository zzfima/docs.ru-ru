---
title: Параметры конфигурации сборщика мусора
description: Сведения о параметрах времени выполнения, определяющих, как сборщик мусора управляет памятью для приложений .NET Core.
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: 24e5c47de781e7eed5f76d2c551cac2dce1e8f05
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900098"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="49e3d-103">Параметры конфигурации времени выполнения для сборки мусора</span><span class="sxs-lookup"><span data-stu-id="49e3d-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="49e3d-104">Эта страница содержит сведения о параметрах сборщика мусора (GC), которые можно изменить во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="49e3d-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="49e3d-105">Если вы пытаетесь добиться пиковой производительности запущенных приложений, рекомендуется использовать эти параметры.</span><span class="sxs-lookup"><span data-stu-id="49e3d-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="49e3d-106">Однако значения по умолчанию обеспечивают оптимальную производительность для большинства приложений в типичных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="49e3d-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="49e3d-107">На этой странице параметры упорядочены по группам.</span><span class="sxs-lookup"><span data-stu-id="49e3d-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="49e3d-108">Параметры в каждой группе обычно используются совместно друг с другом для достижения определенного результата.</span><span class="sxs-lookup"><span data-stu-id="49e3d-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="49e3d-109">Эти параметры также могут динамически изменяться приложением во время его выполнения, поэтому любые заданные параметры времени выполнения могут быть переопределены.</span><span class="sxs-lookup"><span data-stu-id="49e3d-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="49e3d-110">Некоторые параметры, такие как [уровень задержки](../../standard/garbage-collection/latency.md), обычно задаются только через API во время разработки.</span><span class="sxs-lookup"><span data-stu-id="49e3d-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="49e3d-111">Такие параметры будут пропущены на этой странице.</span><span class="sxs-lookup"><span data-stu-id="49e3d-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="49e3d-112">Для числовых значений используйте десятичную нотацию для параметров в файле *runtimeconfig.json* и шестнадцатеричную нотацию для параметров переменных среды.</span><span class="sxs-lookup"><span data-stu-id="49e3d-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="49e3d-113">Шестнадцатеричные значения можно указать с помощью префикса "0x" или без него.</span><span class="sxs-lookup"><span data-stu-id="49e3d-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="49e3d-114">Варианты сборки мусора</span><span class="sxs-lookup"><span data-stu-id="49e3d-114">Flavors of garbage collection</span></span>

<span data-ttu-id="49e3d-115">Два основных варианта сборки мусора — это сборка мусора рабочей станции и сборка мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="49e3d-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="49e3d-116">Дополнительные сведения о различиях между этими двумя вариантами см. в статье [Основы сборки мусора](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span><span class="sxs-lookup"><span data-stu-id="49e3d-116">For more information about differences between the two, see [Fundamentals of garbage collection](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span></span>

<span data-ttu-id="49e3d-117">Подвиды сборки мусора представлены фоновым и непараллельным выполнением.</span><span class="sxs-lookup"><span data-stu-id="49e3d-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="49e3d-118">Чтобы выбрать варианты сборки мусора, используйте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="49e3d-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="49e3d-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="49e3d-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="49e3d-120">Указывает, использует ли приложение сборку мусора рабочей станции или сборку мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="49e3d-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="49e3d-121">По умолчанию: сборка мусора рабочей станции (`false`).</span><span class="sxs-lookup"><span data-stu-id="49e3d-121">Default: Workstation garbage collection (`false`).</span></span>

| | <span data-ttu-id="49e3d-122">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="49e3d-122">Setting name</span></span> | <span data-ttu-id="49e3d-123">Значения</span><span class="sxs-lookup"><span data-stu-id="49e3d-123">Values</span></span> | <span data-ttu-id="49e3d-124">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="49e3d-124">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49e3d-125">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="49e3d-125">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="49e3d-126">`false` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="49e3d-126">`false` - workstation</span></span><br/><span data-ttu-id="49e3d-127">`true` — сервер</span><span class="sxs-lookup"><span data-stu-id="49e3d-127">`true` - server</span></span> | <span data-ttu-id="49e3d-128">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="49e3d-128">.NET Core 1.0</span></span> |
| <span data-ttu-id="49e3d-129">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="49e3d-129">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="49e3d-130">`0` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="49e3d-130">`0` - workstation</span></span><br/><span data-ttu-id="49e3d-131">`1` — сервер</span><span class="sxs-lookup"><span data-stu-id="49e3d-131">`1` - server</span></span> | <span data-ttu-id="49e3d-132">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="49e3d-132">.NET Core 1.0</span></span> |
| <span data-ttu-id="49e3d-133">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="49e3d-133">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="49e3d-134">GCServer</span><span class="sxs-lookup"><span data-stu-id="49e3d-134">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="49e3d-135">`false` — рабочая станция</span><span class="sxs-lookup"><span data-stu-id="49e3d-135">`false` - workstation</span></span><br/><span data-ttu-id="49e3d-136">`true` — сервер</span><span class="sxs-lookup"><span data-stu-id="49e3d-136">`true` - server</span></span> |  |

<span data-ttu-id="49e3d-137">Пример.</span><span class="sxs-lookup"><span data-stu-id="49e3d-137">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="49e3d-138">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="49e3d-138">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="49e3d-139">Указывает, включена ли фоновая (параллельная) сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="49e3d-139">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="49e3d-140">По умолчанию: включено (`true`).</span><span class="sxs-lookup"><span data-stu-id="49e3d-140">Default: Enabled (`true`).</span></span>
- <span data-ttu-id="49e3d-141">Дополнительные сведения см. в статьях [Фоновая сборка мусора](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) и [Фоновая сборка мусора сервера](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span><span class="sxs-lookup"><span data-stu-id="49e3d-141">For more information, see [Background garbage collection](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) and [Background server garbage collection](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span></span>

| | <span data-ttu-id="49e3d-142">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="49e3d-142">Setting name</span></span> | <span data-ttu-id="49e3d-143">Значения</span><span class="sxs-lookup"><span data-stu-id="49e3d-143">Values</span></span> | <span data-ttu-id="49e3d-144">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="49e3d-144">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49e3d-145">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="49e3d-145">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="49e3d-146">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="49e3d-146">`true` - background GC</span></span><br/><span data-ttu-id="49e3d-147">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="49e3d-147">`false` - non-concurrent GC</span></span> | <span data-ttu-id="49e3d-148">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="49e3d-148">.NET Core 1.0</span></span> |
| <span data-ttu-id="49e3d-149">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="49e3d-149">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="49e3d-150">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="49e3d-150">`true` - background GC</span></span><br/><span data-ttu-id="49e3d-151">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="49e3d-151">`false` - non-concurrent GC</span></span> | <span data-ttu-id="49e3d-152">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="49e3d-152">.NET Core 1.0</span></span> |
| <span data-ttu-id="49e3d-153">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="49e3d-153">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="49e3d-154">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="49e3d-154">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="49e3d-155">`true` —фоновая сборка мусора</span><span class="sxs-lookup"><span data-stu-id="49e3d-155">`true` - background GC</span></span><br/><span data-ttu-id="49e3d-156">`false` — непараллельная сборка мусора</span><span class="sxs-lookup"><span data-stu-id="49e3d-156">`false` - non-concurrent GC</span></span> |  |

<span data-ttu-id="49e3d-157">Пример.</span><span class="sxs-lookup"><span data-stu-id="49e3d-157">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

## <a name="manage-resource-usage"></a><span data-ttu-id="49e3d-158">Управление использованием ресурсов</span><span class="sxs-lookup"><span data-stu-id="49e3d-158">Manage resource usage</span></span>

<span data-ttu-id="49e3d-159">Используйте параметры, описанные в этом разделе, для управления использованием памяти и ЦП в сборщике мусора.</span><span class="sxs-lookup"><span data-stu-id="49e3d-159">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="49e3d-160">Дополнительные сведения о некоторых из этих параметров см. в записи блога о [компромиссе между сборкой мусора рабочей станции и сервера](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/).</span><span class="sxs-lookup"><span data-stu-id="49e3d-160">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="49e3d-161">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="49e3d-161">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="49e3d-162">Ограничивает число куч, создаваемых сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="49e3d-162">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="49e3d-163">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="49e3d-163">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="49e3d-164">Если включено сходство процессоров сборки мусора, что используется по умолчанию, параметр счетчика куч реализует сходство `n` куч/потоков сборки мусора с первыми `n` процессорами.</span><span class="sxs-lookup"><span data-stu-id="49e3d-164">If GC processor affinity is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="49e3d-165">(Используйте параметры сходства маски или сходства диапазонов, чтобы указать, для каких именно процессоров следует реализовать сходство.)</span><span class="sxs-lookup"><span data-stu-id="49e3d-165">(Use the affinitize mask or affinitize ranges settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="49e3d-166">Если сходство процессоров сборки мусора отключено, этот параметр будет ограничивать количество куч сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="49e3d-166">If GC processor affinity is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="49e3d-167">Дополнительные сведения см. в [примечаниях по GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="49e3d-167">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="49e3d-168">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="49e3d-168">Setting name</span></span> | <span data-ttu-id="49e3d-169">Значения</span><span class="sxs-lookup"><span data-stu-id="49e3d-169">Values</span></span> | <span data-ttu-id="49e3d-170">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="49e3d-170">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49e3d-171">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="49e3d-171">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="49e3d-172">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="49e3d-172">*decimal value*</span></span> | <span data-ttu-id="49e3d-173">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49e3d-173">.NET Core 3.0</span></span> |
| <span data-ttu-id="49e3d-174">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="49e3d-174">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="49e3d-175">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="49e3d-175">*hexadecimal value*</span></span> | <span data-ttu-id="49e3d-176">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49e3d-176">.NET Core 3.0</span></span> |
| <span data-ttu-id="49e3d-177">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="49e3d-177">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="49e3d-178">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="49e3d-178">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="49e3d-179">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="49e3d-179">*decimal value*</span></span> | <span data-ttu-id="49e3d-180">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="49e3d-180">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="49e3d-181">Пример.</span><span class="sxs-lookup"><span data-stu-id="49e3d-181">Example:</span></span>

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
> <span data-ttu-id="49e3d-182">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="49e3d-182">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="49e3d-183">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="49e3d-183">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="49e3d-184">Например, чтобы ограничить число куч значением 16, для JSON-файла нужно указать 16, а для переменной среды — 0x10 или 10.</span><span class="sxs-lookup"><span data-stu-id="49e3d-184">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="49e3d-185">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="49e3d-185">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="49e3d-186">Указывает конкретные процессоры, которые должны использоваться потоками сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="49e3d-186">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="49e3d-187">Если сходство процессоров отключено посредством задания значения `true` для `System.GC.NoAffinitize`, этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="49e3d-187">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="49e3d-188">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="49e3d-188">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="49e3d-189">Это значение представляет собой битовую маску, которая определяет доступные процессу процессоры.</span><span class="sxs-lookup"><span data-stu-id="49e3d-189">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="49e3d-190">Например, десятичное значение 1023 (или шестнадцатеричное значение 0x3FF или 3FF, если вы используете переменную среды), равно 0011 1111 1111 в двоичной нотации.</span><span class="sxs-lookup"><span data-stu-id="49e3d-190">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="49e3d-191">При этом будут использоваться первые 10 процессоров.</span><span class="sxs-lookup"><span data-stu-id="49e3d-191">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="49e3d-192">Чтобы указать следующие 10 процессоров, то есть процессоры 10–19, задайте десятичное значение 1047552 (или шестнадцатеричное значение 0xFFC00 или FFC00), которое эквивалентно двоичному значению 1111 1111 1100 0000 0000.</span><span class="sxs-lookup"><span data-stu-id="49e3d-192">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="49e3d-193">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="49e3d-193">Setting name</span></span> | <span data-ttu-id="49e3d-194">Значения</span><span class="sxs-lookup"><span data-stu-id="49e3d-194">Values</span></span> | <span data-ttu-id="49e3d-195">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="49e3d-195">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49e3d-196">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="49e3d-196">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="49e3d-197">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="49e3d-197">*decimal value*</span></span> | <span data-ttu-id="49e3d-198">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49e3d-198">.NET Core 3.0</span></span> |
| <span data-ttu-id="49e3d-199">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="49e3d-199">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="49e3d-200">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="49e3d-200">*hexadecimal value*</span></span> | <span data-ttu-id="49e3d-201">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49e3d-201">.NET Core 3.0</span></span> |
| <span data-ttu-id="49e3d-202">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="49e3d-202">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="49e3d-203">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="49e3d-203">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="49e3d-204">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="49e3d-204">*decimal value*</span></span> | <span data-ttu-id="49e3d-205">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="49e3d-205">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="49e3d-206">Пример.</span><span class="sxs-lookup"><span data-stu-id="49e3d-206">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="49e3d-207">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="49e3d-207">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="49e3d-208">Указывает список процессоров, используемых для потоков сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="49e3d-208">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="49e3d-209">Этот параметр аналогичен `System.GC.HeapAffinitizeMask`, за исключением того, что он позволяет указать больше 64 процессоров.</span><span class="sxs-lookup"><span data-stu-id="49e3d-209">This setting is similar to `System.GC.HeapAffinitizeMask`, except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="49e3d-210">Для операционных систем Windows добавьте к номеру или диапазону процессоров префикс в виде соответствующей [группы ЦП](/windows/win32/procthread/processor-groups), например "0:1-10,0:12,1:50-52,1:70".</span><span class="sxs-lookup"><span data-stu-id="49e3d-210">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="49e3d-211">Если сходство процессоров отключено посредством задания значения `true` для `System.GC.NoAffinitize`, этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="49e3d-211">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="49e3d-212">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="49e3d-212">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="49e3d-213">Дополнительные сведения см. в записи об [улучшении конфигурации ЦП для сборки мусора на компьютерах, имеющих более 64 ЦП](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/), в блоге Майони Стивенс (Maoni Stephens).</span><span class="sxs-lookup"><span data-stu-id="49e3d-213">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="49e3d-214">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="49e3d-214">Setting name</span></span> | <span data-ttu-id="49e3d-215">Значения</span><span class="sxs-lookup"><span data-stu-id="49e3d-215">Values</span></span> | <span data-ttu-id="49e3d-216">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="49e3d-216">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49e3d-217">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="49e3d-217">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="49e3d-218">Разделенный запятыми список номеров процессоров или диапазонов номеров процессоров.</span><span class="sxs-lookup"><span data-stu-id="49e3d-218">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="49e3d-219">Пример для Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="49e3d-219">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="49e3d-220">Пример для Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="49e3d-220">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="49e3d-221">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49e3d-221">.NET Core 3.0</span></span> |
| <span data-ttu-id="49e3d-222">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="49e3d-222">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="49e3d-223">Разделенный запятыми список номеров процессоров или диапазонов номеров процессоров.</span><span class="sxs-lookup"><span data-stu-id="49e3d-223">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="49e3d-224">Пример для Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="49e3d-224">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="49e3d-225">Пример для Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="49e3d-225">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="49e3d-226">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49e3d-226">.NET Core 3.0</span></span> |

<span data-ttu-id="49e3d-227">Пример.</span><span class="sxs-lookup"><span data-stu-id="49e3d-227">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="49e3d-228">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="49e3d-228">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="49e3d-229">Указывает, использует ли сборщик мусора [группы ЦП](/windows/win32/procthread/processor-groups).</span><span class="sxs-lookup"><span data-stu-id="49e3d-229">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="49e3d-230">Когда 64-разрядный компьютер с Windows имеет несколько групп ЦП, то есть доступно более 64 процессоров, включение этого элемента расширяет действие сборки мусора на все группы ЦП.</span><span class="sxs-lookup"><span data-stu-id="49e3d-230">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="49e3d-231">Сборщик мусора использует все ядра для создания и балансировки куч.</span><span class="sxs-lookup"><span data-stu-id="49e3d-231">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="49e3d-232">Применяется только к сборке мусора сервера в 64-разрядных операционных системах Windows.</span><span class="sxs-lookup"><span data-stu-id="49e3d-232">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="49e3d-233">По умолчанию: отключено (`0`).</span><span class="sxs-lookup"><span data-stu-id="49e3d-233">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="49e3d-234">Дополнительные сведения см. в записи об [улучшении конфигурации ЦП для сборки мусора на компьютерах, имеющих более 64 ЦП](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/), в блоге Майони Стивенс (Maoni Stephens).</span><span class="sxs-lookup"><span data-stu-id="49e3d-234">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="49e3d-235">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="49e3d-235">Setting name</span></span> | <span data-ttu-id="49e3d-236">Значения</span><span class="sxs-lookup"><span data-stu-id="49e3d-236">Values</span></span> | <span data-ttu-id="49e3d-237">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="49e3d-237">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49e3d-238">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="49e3d-238">**runtimeconfig.json**</span></span> | <span data-ttu-id="49e3d-239">Н/Д</span><span class="sxs-lookup"><span data-stu-id="49e3d-239">N/A</span></span> | <span data-ttu-id="49e3d-240">Н/Д</span><span class="sxs-lookup"><span data-stu-id="49e3d-240">N/A</span></span> | <span data-ttu-id="49e3d-241">Н/Д</span><span class="sxs-lookup"><span data-stu-id="49e3d-241">N/A</span></span> |
| <span data-ttu-id="49e3d-242">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="49e3d-242">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="49e3d-243">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="49e3d-243">`0` - disabled</span></span><br/><span data-ttu-id="49e3d-244">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="49e3d-244">`1` - enabled</span></span> | <span data-ttu-id="49e3d-245">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="49e3d-245">.NET Core 1.0</span></span> |
| <span data-ttu-id="49e3d-246">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="49e3d-246">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="49e3d-247">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="49e3d-247">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="49e3d-248">`false` — отключено</span><span class="sxs-lookup"><span data-stu-id="49e3d-248">`false` - disabled</span></span><br/><span data-ttu-id="49e3d-249">`true` — включено</span><span class="sxs-lookup"><span data-stu-id="49e3d-249">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="49e3d-250">Чтобы настроить среду CLR для распределения потоков из пула потоков по всем группам ЦП, включите параметр [Элемент Thread_UseAllCpuGroups](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md).</span><span class="sxs-lookup"><span data-stu-id="49e3d-250">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="49e3d-251">Для приложений .NET Core этот параметр можно включить, задав для переменной среды `COMPlus_Thread_UseAllCpuGroups` значение `1`.</span><span class="sxs-lookup"><span data-stu-id="49e3d-251">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="49e3d-252">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="49e3d-252">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="49e3d-253">Указывает, следует ли *реализовать сходство* потоков сборки мусора с процессорами.</span><span class="sxs-lookup"><span data-stu-id="49e3d-253">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="49e3d-254">Реализация сходства потока сборки мусора означает, что он может выполняться только на определенном ЦП.</span><span class="sxs-lookup"><span data-stu-id="49e3d-254">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="49e3d-255">Куча создается для каждого потока сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="49e3d-255">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="49e3d-256">Применяется только к сборке мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="49e3d-256">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="49e3d-257">По умолчанию: реализация сходства потоков сборки мусора с процессорами (`false`).</span><span class="sxs-lookup"><span data-stu-id="49e3d-257">Default: Affinitize garbage collection threads with processors (`false`).</span></span>

| | <span data-ttu-id="49e3d-258">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="49e3d-258">Setting name</span></span> | <span data-ttu-id="49e3d-259">Значения</span><span class="sxs-lookup"><span data-stu-id="49e3d-259">Values</span></span> | <span data-ttu-id="49e3d-260">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="49e3d-260">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49e3d-261">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="49e3d-261">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="49e3d-262">`false` — реализовать сходство</span><span class="sxs-lookup"><span data-stu-id="49e3d-262">`false` - affinitize</span></span><br/><span data-ttu-id="49e3d-263">`true` — не реализовывать сходство</span><span class="sxs-lookup"><span data-stu-id="49e3d-263">`true` - don't affinitize</span></span> | <span data-ttu-id="49e3d-264">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49e3d-264">.NET Core 3.0</span></span> |
| <span data-ttu-id="49e3d-265">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="49e3d-265">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="49e3d-266">`0` — реализовать сходство</span><span class="sxs-lookup"><span data-stu-id="49e3d-266">`0` - affinitize</span></span><br/><span data-ttu-id="49e3d-267">`1` — не реализовывать сходство</span><span class="sxs-lookup"><span data-stu-id="49e3d-267">`1` - don't affinitize</span></span> | <span data-ttu-id="49e3d-268">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49e3d-268">.NET Core 3.0</span></span> |
| <span data-ttu-id="49e3d-269">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="49e3d-269">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="49e3d-270">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="49e3d-270">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="49e3d-271">`false` — реализовать сходство</span><span class="sxs-lookup"><span data-stu-id="49e3d-271">`false` - affinitize</span></span><br/><span data-ttu-id="49e3d-272">`true` — не реализовывать сходство</span><span class="sxs-lookup"><span data-stu-id="49e3d-272">`true` - don't affinitize</span></span> | <span data-ttu-id="49e3d-273">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="49e3d-273">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="49e3d-274">Пример.</span><span class="sxs-lookup"><span data-stu-id="49e3d-274">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="49e3d-275">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="49e3d-275">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="49e3d-276">Указывает максимальный размер фиксации в байтах для кучи сборки мусора и учета сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="49e3d-276">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>

| | <span data-ttu-id="49e3d-277">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="49e3d-277">Setting name</span></span> | <span data-ttu-id="49e3d-278">Значения</span><span class="sxs-lookup"><span data-stu-id="49e3d-278">Values</span></span> | <span data-ttu-id="49e3d-279">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="49e3d-279">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49e3d-280">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="49e3d-280">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="49e3d-281">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="49e3d-281">*decimal value*</span></span> | <span data-ttu-id="49e3d-282">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49e3d-282">.NET Core 3.0</span></span> |
| <span data-ttu-id="49e3d-283">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="49e3d-283">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="49e3d-284">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="49e3d-284">*hexadecimal value*</span></span> | <span data-ttu-id="49e3d-285">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49e3d-285">.NET Core 3.0</span></span> |

<span data-ttu-id="49e3d-286">Пример.</span><span class="sxs-lookup"><span data-stu-id="49e3d-286">Example:</span></span>

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
> <span data-ttu-id="49e3d-287">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="49e3d-287">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="49e3d-288">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="49e3d-288">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="49e3d-289">Например, чтобы задать для куч жесткое ограничение в 200 мебибайт (Миб), для JSON-файла нужно указать значение 209715200, а для переменной среды — значение 0xC800000 или C800000.</span><span class="sxs-lookup"><span data-stu-id="49e3d-289">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="49e3d-290">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="49e3d-290">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="49e3d-291">Указывает использование кучи сборки мусора в процентах от общего объема памяти.</span><span class="sxs-lookup"><span data-stu-id="49e3d-291">Specifies the GC heap usage as a percentage of the total memory.</span></span>

| | <span data-ttu-id="49e3d-292">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="49e3d-292">Setting name</span></span> | <span data-ttu-id="49e3d-293">Значения</span><span class="sxs-lookup"><span data-stu-id="49e3d-293">Values</span></span> | <span data-ttu-id="49e3d-294">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="49e3d-294">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49e3d-295">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="49e3d-295">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="49e3d-296">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="49e3d-296">*decimal value*</span></span> | <span data-ttu-id="49e3d-297">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49e3d-297">.NET Core 3.0</span></span> |
| <span data-ttu-id="49e3d-298">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="49e3d-298">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="49e3d-299">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="49e3d-299">*hexadecimal value*</span></span> | <span data-ttu-id="49e3d-300">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49e3d-300">.NET Core 3.0</span></span> |

<span data-ttu-id="49e3d-301">Пример.</span><span class="sxs-lookup"><span data-stu-id="49e3d-301">Example:</span></span>

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
> <span data-ttu-id="49e3d-302">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="49e3d-302">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="49e3d-303">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="49e3d-303">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="49e3d-304">Например, чтобы ограничить использование кучи значением 30 %, для JSON-файла нужно указать 30, а для переменной среды — 0x1E или 1E.</span><span class="sxs-lookup"><span data-stu-id="49e3d-304">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="49e3d-305">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="49e3d-305">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="49e3d-306">Настраивает, будут ли удаляемые сегменты помещаться в список ожидания для будущего использования или возвращаться операционной системе (ОС).</span><span class="sxs-lookup"><span data-stu-id="49e3d-306">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="49e3d-307">По умолчанию: возвращение сегментов операционной системе (`false`).</span><span class="sxs-lookup"><span data-stu-id="49e3d-307">Default: Release segments back to the operating system (`false`).</span></span>

| | <span data-ttu-id="49e3d-308">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="49e3d-308">Setting name</span></span> | <span data-ttu-id="49e3d-309">Значения</span><span class="sxs-lookup"><span data-stu-id="49e3d-309">Values</span></span> | <span data-ttu-id="49e3d-310">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="49e3d-310">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49e3d-311">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="49e3d-311">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="49e3d-312">`false` — возвращение операционной системе</span><span class="sxs-lookup"><span data-stu-id="49e3d-312">`false` - release to OS</span></span><br/><span data-ttu-id="49e3d-313">`true` — помещение в режим ожидания</span><span class="sxs-lookup"><span data-stu-id="49e3d-313">`true` - put on standby</span></span>| <span data-ttu-id="49e3d-314">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="49e3d-314">.NET Core 1.0</span></span> |
| <span data-ttu-id="49e3d-315">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="49e3d-315">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="49e3d-316">`0` — возвращение операционной системе</span><span class="sxs-lookup"><span data-stu-id="49e3d-316">`0` - release to OS</span></span><br/><span data-ttu-id="49e3d-317">`1` — помещение в режим ожидания</span><span class="sxs-lookup"><span data-stu-id="49e3d-317">`1` - put on standby</span></span> | <span data-ttu-id="49e3d-318">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="49e3d-318">.NET Core 1.0</span></span> |

<span data-ttu-id="49e3d-319">Пример.</span><span class="sxs-lookup"><span data-stu-id="49e3d-319">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

## <a name="large-pages"></a><span data-ttu-id="49e3d-320">Большие страницы</span><span class="sxs-lookup"><span data-stu-id="49e3d-320">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="49e3d-321">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="49e3d-321">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="49e3d-322">Указывает, следует ли использовать большие страницы, когда задано жесткое ограничение куч.</span><span class="sxs-lookup"><span data-stu-id="49e3d-322">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="49e3d-323">По умолчанию: отключено (`0`).</span><span class="sxs-lookup"><span data-stu-id="49e3d-323">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="49e3d-324">Это экспериментальный параметр.</span><span class="sxs-lookup"><span data-stu-id="49e3d-324">This is an experimental setting.</span></span>

| | <span data-ttu-id="49e3d-325">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="49e3d-325">Setting name</span></span> | <span data-ttu-id="49e3d-326">Значения</span><span class="sxs-lookup"><span data-stu-id="49e3d-326">Values</span></span> | <span data-ttu-id="49e3d-327">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="49e3d-327">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49e3d-328">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="49e3d-328">**runtimeconfig.json**</span></span> | <span data-ttu-id="49e3d-329">Н/Д</span><span class="sxs-lookup"><span data-stu-id="49e3d-329">N/A</span></span> | <span data-ttu-id="49e3d-330">Н/Д</span><span class="sxs-lookup"><span data-stu-id="49e3d-330">N/A</span></span> | <span data-ttu-id="49e3d-331">Н/Д</span><span class="sxs-lookup"><span data-stu-id="49e3d-331">N/A</span></span> |
| <span data-ttu-id="49e3d-332">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="49e3d-332">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="49e3d-333">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="49e3d-333">`0` - disabled</span></span><br/><span data-ttu-id="49e3d-334">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="49e3d-334">`1` - enabled</span></span> | <span data-ttu-id="49e3d-335">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49e3d-335">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="49e3d-336">Большие объекты</span><span class="sxs-lookup"><span data-stu-id="49e3d-336">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="49e3d-337">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="49e3d-337">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="49e3d-338">Настраивает для сборщика мусора на 64-разрядных платформах поддержку массивов, размер которых превышает 2 гигабайта (ГБ).</span><span class="sxs-lookup"><span data-stu-id="49e3d-338">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="49e3d-339">По умолчанию: включено (`1`).</span><span class="sxs-lookup"><span data-stu-id="49e3d-339">Default: Enabled (`1`).</span></span>
- <span data-ttu-id="49e3d-340">В будущей версии .NET этот параметр может быть объявлен устаревшим.</span><span class="sxs-lookup"><span data-stu-id="49e3d-340">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="49e3d-341">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="49e3d-341">Setting name</span></span> | <span data-ttu-id="49e3d-342">Значения</span><span class="sxs-lookup"><span data-stu-id="49e3d-342">Values</span></span> | <span data-ttu-id="49e3d-343">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="49e3d-343">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49e3d-344">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="49e3d-344">**runtimeconfig.json**</span></span> | <span data-ttu-id="49e3d-345">Н/Д</span><span class="sxs-lookup"><span data-stu-id="49e3d-345">N/A</span></span> | <span data-ttu-id="49e3d-346">Н/Д</span><span class="sxs-lookup"><span data-stu-id="49e3d-346">N/A</span></span> | <span data-ttu-id="49e3d-347">Н/Д</span><span class="sxs-lookup"><span data-stu-id="49e3d-347">N/A</span></span> |
| <span data-ttu-id="49e3d-348">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="49e3d-348">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="49e3d-349">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="49e3d-349">`1` - enabled</span></span><br/> <span data-ttu-id="49e3d-350">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="49e3d-350">`0` - disabled</span></span> | <span data-ttu-id="49e3d-351">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="49e3d-351">.NET Core 1.0</span></span> |
| <span data-ttu-id="49e3d-352">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="49e3d-352">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="49e3d-353">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="49e3d-353">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="49e3d-354">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="49e3d-354">`1` - enabled</span></span><br/> <span data-ttu-id="49e3d-355">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="49e3d-355">`0` - disabled</span></span> | <span data-ttu-id="49e3d-356">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="49e3d-356">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="49e3d-357">Пороговое значение кучи больших объектов</span><span class="sxs-lookup"><span data-stu-id="49e3d-357">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="49e3d-358">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="49e3d-358">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="49e3d-359">Указывает пороговый размер (в байтах), при котором объекты попадают в кучу больших объектов (LOH).</span><span class="sxs-lookup"><span data-stu-id="49e3d-359">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="49e3d-360">Пороговое значение по умолчанию — 85 000 байт.</span><span class="sxs-lookup"><span data-stu-id="49e3d-360">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="49e3d-361">Указанное значение должно быть больше порогового значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="49e3d-361">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="49e3d-362">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="49e3d-362">Setting name</span></span> | <span data-ttu-id="49e3d-363">Значения</span><span class="sxs-lookup"><span data-stu-id="49e3d-363">Values</span></span> | <span data-ttu-id="49e3d-364">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="49e3d-364">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49e3d-365">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="49e3d-365">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="49e3d-366">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="49e3d-366">*decimal value*</span></span> | <span data-ttu-id="49e3d-367">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="49e3d-367">.NET Core 1.0</span></span> |
| <span data-ttu-id="49e3d-368">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="49e3d-368">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="49e3d-369">*Шестнадцатеричное значение*</span><span class="sxs-lookup"><span data-stu-id="49e3d-369">*hexadecimal value*</span></span> | <span data-ttu-id="49e3d-370">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="49e3d-370">.NET Core 1.0</span></span> |
| <span data-ttu-id="49e3d-371">**app.config для .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="49e3d-371">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="49e3d-372">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="49e3d-372">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="49e3d-373">*Десятичное значение*</span><span class="sxs-lookup"><span data-stu-id="49e3d-373">*decimal value*</span></span> | <span data-ttu-id="49e3d-374">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="49e3d-374">.NET Framework 4.8</span></span> |

<span data-ttu-id="49e3d-375">Пример.</span><span class="sxs-lookup"><span data-stu-id="49e3d-375">Example:</span></span>

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
> <span data-ttu-id="49e3d-376">Если вы задаете параметр в *runtimeconfig.json*, укажите десятичное значение.</span><span class="sxs-lookup"><span data-stu-id="49e3d-376">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="49e3d-377">Если вы задаете параметр в виде переменной среды, укажите шестнадцатеричное значение.</span><span class="sxs-lookup"><span data-stu-id="49e3d-377">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="49e3d-378">Например, чтобы задать порог размера в 120 000 байт, для JSON-файла нужно указать значение 120000, а для переменной среды — значение 0x1D4C0 или 1D4C0.</span><span class="sxs-lookup"><span data-stu-id="49e3d-378">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="49e3d-379">Автономный сборщик мусора</span><span class="sxs-lookup"><span data-stu-id="49e3d-379">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="49e3d-380">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="49e3d-380">COMPlus_GCName</span></span>

- <span data-ttu-id="49e3d-381">Указывает путь к библиотеке, содержащей сборщик мусора, который среда выполнения намеревается загрузить.</span><span class="sxs-lookup"><span data-stu-id="49e3d-381">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="49e3d-382">Дополнительные сведения см. в статье [Проектирования загрузчика автономного сборщика мусора](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span><span class="sxs-lookup"><span data-stu-id="49e3d-382">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="49e3d-383">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="49e3d-383">Setting name</span></span> | <span data-ttu-id="49e3d-384">Значения</span><span class="sxs-lookup"><span data-stu-id="49e3d-384">Values</span></span> | <span data-ttu-id="49e3d-385">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="49e3d-385">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49e3d-386">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="49e3d-386">**runtimeconfig.json**</span></span> | <span data-ttu-id="49e3d-387">Н/Д</span><span class="sxs-lookup"><span data-stu-id="49e3d-387">N/A</span></span> | <span data-ttu-id="49e3d-388">Н/Д</span><span class="sxs-lookup"><span data-stu-id="49e3d-388">N/A</span></span> | <span data-ttu-id="49e3d-389">Н/Д</span><span class="sxs-lookup"><span data-stu-id="49e3d-389">N/A</span></span> |
| <span data-ttu-id="49e3d-390">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="49e3d-390">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="49e3d-391">*string_path*</span><span class="sxs-lookup"><span data-stu-id="49e3d-391">*string_path*</span></span> | <span data-ttu-id="49e3d-392">.NET Core 2.0;</span><span class="sxs-lookup"><span data-stu-id="49e3d-392">.NET Core 2.0</span></span> |
