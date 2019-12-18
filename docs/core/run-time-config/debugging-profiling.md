---
title: Параметры конфигурации отладки и профилирования
description: Сведения о параметрах времени выполнения, определяющих использование отладки и профилирования для приложений .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: c57cfa7233f48def890ded3c9d589b7f268147df
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998861"
---
# <a name="run-time-configuration-options-for-debugging-and-profiling"></a><span data-ttu-id="cb900-103">Параметры конфигурации времени выполнения для отладки и профилирования</span><span class="sxs-lookup"><span data-stu-id="cb900-103">Run-time configuration options for debugging and profiling</span></span>

## <a name="enable-diagnostics"></a><span data-ttu-id="cb900-104">Включение диагностики</span><span class="sxs-lookup"><span data-stu-id="cb900-104">Enable diagnostics</span></span>

- <span data-ttu-id="cb900-105">Указывает, включены или нет отладчик, профилировщик и диагностика EventPipe.</span><span class="sxs-lookup"><span data-stu-id="cb900-105">Configures whether the debugger, the profiler, and EventPipe diagnostics are enabled or disabled.</span></span>
- <span data-ttu-id="cb900-106">По умолчанию: включено (`1`).</span><span class="sxs-lookup"><span data-stu-id="cb900-106">Default: Enabled (`1`).</span></span>

| | <span data-ttu-id="cb900-107">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="cb900-107">Setting name</span></span> | <span data-ttu-id="cb900-108">Значения</span><span class="sxs-lookup"><span data-stu-id="cb900-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="cb900-109">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="cb900-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="cb900-110">Н/Д</span><span class="sxs-lookup"><span data-stu-id="cb900-110">N/A</span></span> | <span data-ttu-id="cb900-111">Н/Д</span><span class="sxs-lookup"><span data-stu-id="cb900-111">N/A</span></span> |
| <span data-ttu-id="cb900-112">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="cb900-112">**Environment variable**</span></span> | `COMPlus_EnableDiagnostics` | <span data-ttu-id="cb900-113">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="cb900-113">`1` - enabled</span></span><br/><span data-ttu-id="cb900-114">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="cb900-114">`0` - disabled</span></span> |

## <a name="enable-profiling"></a><span data-ttu-id="cb900-115">Включить профилирование</span><span class="sxs-lookup"><span data-stu-id="cb900-115">Enable profiling</span></span>

- <span data-ttu-id="cb900-116">Указывает, включено ли профилирование для текущего выполняющегося процесса.</span><span class="sxs-lookup"><span data-stu-id="cb900-116">Configures whether profiling is enabled for the currently running process.</span></span>
- <span data-ttu-id="cb900-117">По умолчанию: отключено (`0`).</span><span class="sxs-lookup"><span data-stu-id="cb900-117">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="cb900-118">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="cb900-118">Setting name</span></span> | <span data-ttu-id="cb900-119">Значения</span><span class="sxs-lookup"><span data-stu-id="cb900-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="cb900-120">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="cb900-120">**runtimeconfig.json**</span></span> | <span data-ttu-id="cb900-121">Н/Д</span><span class="sxs-lookup"><span data-stu-id="cb900-121">N/A</span></span> | <span data-ttu-id="cb900-122">Н/Д</span><span class="sxs-lookup"><span data-stu-id="cb900-122">N/A</span></span> |
| <span data-ttu-id="cb900-123">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="cb900-123">**Environment variable**</span></span> | `CORECLR_ENABLE_PROFILING` | <span data-ttu-id="cb900-124">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="cb900-124">`0` - disabled</span></span><br/><span data-ttu-id="cb900-125">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="cb900-125">`1` - enabled</span></span> |

## <a name="profiler-guid"></a><span data-ttu-id="cb900-126">Profiler GUID (GUID профилировщика)</span><span class="sxs-lookup"><span data-stu-id="cb900-126">Profiler GUID</span></span>

- <span data-ttu-id="cb900-127">Указывает идентификатор GUID профилировщика, загружаемый в выполняющийся процесс.</span><span class="sxs-lookup"><span data-stu-id="cb900-127">Specifies the GUID of the profiler to load into the currently running process.</span></span>

| | <span data-ttu-id="cb900-128">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="cb900-128">Setting name</span></span> | <span data-ttu-id="cb900-129">Значения</span><span class="sxs-lookup"><span data-stu-id="cb900-129">Values</span></span> |
| - | - | - |
| <span data-ttu-id="cb900-130">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="cb900-130">**runtimeconfig.json**</span></span> | <span data-ttu-id="cb900-131">Н/Д</span><span class="sxs-lookup"><span data-stu-id="cb900-131">N/A</span></span> | <span data-ttu-id="cb900-132">Н/Д</span><span class="sxs-lookup"><span data-stu-id="cb900-132">N/A</span></span> |
| <span data-ttu-id="cb900-133">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="cb900-133">**Environment variable**</span></span> | `CORECLR_PROFILER` | <span data-ttu-id="cb900-134">*string-guid*</span><span class="sxs-lookup"><span data-stu-id="cb900-134">*string-guid*</span></span> |

## <a name="profiler-location"></a><span data-ttu-id="cb900-135">Profiler location (Расположение профилировщика)</span><span class="sxs-lookup"><span data-stu-id="cb900-135">Profiler location</span></span>

- <span data-ttu-id="cb900-136">Указывает путь к библиотеке DLL профилировщика, загружаемой в выполняющийся процесс (либо 32- или 64-разрядный процесс).</span><span class="sxs-lookup"><span data-stu-id="cb900-136">Specifies the path to the profiler DLL to load into the currently running process (or 32-bit or 64-bit process).</span></span>
- <span data-ttu-id="cb900-137">Если задано более одной переменной, приоритет имеют учитывающие разрядность переменные.</span><span class="sxs-lookup"><span data-stu-id="cb900-137">If more than one variable is set, the bitness-specific variables take precedence.</span></span> <span data-ttu-id="cb900-138">Они указывают, какой разрядности профилировщик следует загрузить.</span><span class="sxs-lookup"><span data-stu-id="cb900-138">They specify which bitness of profiler to load.</span></span>
- <span data-ttu-id="cb900-139">Дополнительные сведения см. в разделе [Поиск библиотеки профилировщика](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md).</span><span class="sxs-lookup"><span data-stu-id="cb900-139">For more information, see [Finding the profiler library](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md).</span></span>

| | <span data-ttu-id="cb900-140">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="cb900-140">Setting name</span></span> | <span data-ttu-id="cb900-141">Значения</span><span class="sxs-lookup"><span data-stu-id="cb900-141">Values</span></span> |
| - | - | - |
| <span data-ttu-id="cb900-142">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="cb900-142">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH` | <span data-ttu-id="cb900-143">*string-path*</span><span class="sxs-lookup"><span data-stu-id="cb900-143">*string-path*</span></span> |
| <span data-ttu-id="cb900-144">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="cb900-144">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH_32` | <span data-ttu-id="cb900-145">*string-path*</span><span class="sxs-lookup"><span data-stu-id="cb900-145">*string-path*</span></span> |
| <span data-ttu-id="cb900-146">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="cb900-146">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH_64` | <span data-ttu-id="cb900-147">*string-path*</span><span class="sxs-lookup"><span data-stu-id="cb900-147">*string-path*</span></span> |

## <a name="write-perf-map"></a><span data-ttu-id="cb900-148">Write perf map (Запись карты производительности)</span><span class="sxs-lookup"><span data-stu-id="cb900-148">Write perf map</span></span>

- <span data-ttu-id="cb900-149">Включает или отключает запись */tmp/perf-$pid.map* в системах Linux.</span><span class="sxs-lookup"><span data-stu-id="cb900-149">Enables or disables writing */tmp/perf-$pid.map* on Linux systems.</span></span>
- <span data-ttu-id="cb900-150">По умолчанию: отключено (`0`).</span><span class="sxs-lookup"><span data-stu-id="cb900-150">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="cb900-151">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="cb900-151">Setting name</span></span> | <span data-ttu-id="cb900-152">Значения</span><span class="sxs-lookup"><span data-stu-id="cb900-152">Values</span></span> |
| - | - | - |
| <span data-ttu-id="cb900-153">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="cb900-153">**runtimeconfig.json**</span></span> | <span data-ttu-id="cb900-154">Н/Д</span><span class="sxs-lookup"><span data-stu-id="cb900-154">N/A</span></span> | <span data-ttu-id="cb900-155">Н/Д</span><span class="sxs-lookup"><span data-stu-id="cb900-155">N/A</span></span> |
| <span data-ttu-id="cb900-156">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="cb900-156">**Environment variable**</span></span> | `COMPlus_PerfMapEnabled` | <span data-ttu-id="cb900-157">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="cb900-157">`0` - disabled</span></span><br/><span data-ttu-id="cb900-158">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="cb900-158">`1` - enabled</span></span> |

## <a name="perf-log-markers"></a><span data-ttu-id="cb900-159">Perf log markers (Маркеры журналов производительности)</span><span class="sxs-lookup"><span data-stu-id="cb900-159">Perf log markers</span></span>

- <span data-ttu-id="cb900-160">Когда `COMPlus_PerfMapEnabled` имеет значение `1`, включает или отключает указанный сигнал, который будет принят и проигнорирован в качестве маркера в журналах производительности.</span><span class="sxs-lookup"><span data-stu-id="cb900-160">When `COMPlus_PerfMapEnabled` is set to `1`, enables or disables the specified signal to be accepted and ignored as a marker in the perf logs.</span></span>
- <span data-ttu-id="cb900-161">По умолчанию: отключено (`0`).</span><span class="sxs-lookup"><span data-stu-id="cb900-161">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="cb900-162">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="cb900-162">Setting name</span></span> | <span data-ttu-id="cb900-163">Значения</span><span class="sxs-lookup"><span data-stu-id="cb900-163">Values</span></span> |
| - | - | - |
| <span data-ttu-id="cb900-164">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="cb900-164">**runtimeconfig.json**</span></span> | <span data-ttu-id="cb900-165">Н/Д</span><span class="sxs-lookup"><span data-stu-id="cb900-165">N/A</span></span> | <span data-ttu-id="cb900-166">Н/Д</span><span class="sxs-lookup"><span data-stu-id="cb900-166">N/A</span></span> |
| <span data-ttu-id="cb900-167">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="cb900-167">**Environment variable**</span></span> | `COMPlus_PerfMapIgnoreSignal` | <span data-ttu-id="cb900-168">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="cb900-168">`0` - disabled</span></span><br/><span data-ttu-id="cb900-169">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="cb900-169">`1` - enabled</span></span> |
