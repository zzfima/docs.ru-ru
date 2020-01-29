---
title: Параметры конфигурации потоков
description: Сведения о параметрах времени выполнения, определяющих использование потоков для приложений .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: ed7688d4d8f7178440fe59afc6e2f5e0a11b2a5c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733429"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="51bc8-103">Параметры конфигурации времени выполнения для потоков</span><span class="sxs-lookup"><span data-stu-id="51bc8-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="51bc8-104">Группы ЦП</span><span class="sxs-lookup"><span data-stu-id="51bc8-104">CPU groups</span></span>

- <span data-ttu-id="51bc8-105">Определяет, выполняется ли автоматическое распределение потоков между группами ЦП.</span><span class="sxs-lookup"><span data-stu-id="51bc8-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="51bc8-106">По умолчанию: отключено (`0`).</span><span class="sxs-lookup"><span data-stu-id="51bc8-106">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="51bc8-107">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="51bc8-107">Setting name</span></span> | <span data-ttu-id="51bc8-108">Значения</span><span class="sxs-lookup"><span data-stu-id="51bc8-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="51bc8-109">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="51bc8-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="51bc8-110">Н/Д</span><span class="sxs-lookup"><span data-stu-id="51bc8-110">N/A</span></span> | <span data-ttu-id="51bc8-111">Н/Д</span><span class="sxs-lookup"><span data-stu-id="51bc8-111">N/A</span></span> |
| <span data-ttu-id="51bc8-112">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="51bc8-112">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="51bc8-113">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="51bc8-113">`0` - disabled</span></span><br/><span data-ttu-id="51bc8-114">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="51bc8-114">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="51bc8-115">Минимальное число потоков</span><span class="sxs-lookup"><span data-stu-id="51bc8-115">Minimum threads</span></span>

- <span data-ttu-id="51bc8-116">Указывает минимальное число потоков для рабочего пула потоков.</span><span class="sxs-lookup"><span data-stu-id="51bc8-116">Specifies the minimum number of threads for the worker threadpool.</span></span>
- <span data-ttu-id="51bc8-117">Соответствует методу <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="51bc8-117">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="51bc8-118">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="51bc8-118">Setting name</span></span> | <span data-ttu-id="51bc8-119">Значения</span><span class="sxs-lookup"><span data-stu-id="51bc8-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="51bc8-120">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="51bc8-120">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="51bc8-121">Целочисленное значение, представляющее минимальное число потоков.</span><span class="sxs-lookup"><span data-stu-id="51bc8-121">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="51bc8-122">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="51bc8-122">**MSBuild property**</span></span> | `ThreadPoolMinThreads` | <span data-ttu-id="51bc8-123">Целочисленное значение, представляющее минимальное число потоков.</span><span class="sxs-lookup"><span data-stu-id="51bc8-123">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="51bc8-124">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="51bc8-124">**Environment variable**</span></span> | <span data-ttu-id="51bc8-125">Н/Д</span><span class="sxs-lookup"><span data-stu-id="51bc8-125">N/A</span></span> | <span data-ttu-id="51bc8-126">Н/Д</span><span class="sxs-lookup"><span data-stu-id="51bc8-126">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="51bc8-127">Примеры</span><span class="sxs-lookup"><span data-stu-id="51bc8-127">Examples</span></span>

<span data-ttu-id="51bc8-128">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="51bc8-128">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MinThreads": 4
      }
   }
}
```

<span data-ttu-id="51bc8-129">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="51bc8-129">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>

</Project>
```

## <a name="maximum-threads"></a><span data-ttu-id="51bc8-130">Максимальное число потоков</span><span class="sxs-lookup"><span data-stu-id="51bc8-130">Maximum threads</span></span>

- <span data-ttu-id="51bc8-131">Указывает максимальное число потоков для рабочего пула потоков.</span><span class="sxs-lookup"><span data-stu-id="51bc8-131">Specifies the maximum number of threads for the worker threadpool.</span></span>
- <span data-ttu-id="51bc8-132">Соответствует методу <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="51bc8-132">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="51bc8-133">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="51bc8-133">Setting name</span></span> | <span data-ttu-id="51bc8-134">Значения</span><span class="sxs-lookup"><span data-stu-id="51bc8-134">Values</span></span> |
| - | - | - |
| <span data-ttu-id="51bc8-135">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="51bc8-135">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="51bc8-136">Целочисленное значение, представляющее максимальное число потоков.</span><span class="sxs-lookup"><span data-stu-id="51bc8-136">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="51bc8-137">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="51bc8-137">**MSBuild property**</span></span> | `ThreadPoolMaxThreads` | <span data-ttu-id="51bc8-138">Целочисленное значение, представляющее максимальное число потоков.</span><span class="sxs-lookup"><span data-stu-id="51bc8-138">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="51bc8-139">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="51bc8-139">**Environment variable**</span></span> | <span data-ttu-id="51bc8-140">Н/Д</span><span class="sxs-lookup"><span data-stu-id="51bc8-140">N/A</span></span> | <span data-ttu-id="51bc8-141">Н/Д</span><span class="sxs-lookup"><span data-stu-id="51bc8-141">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="51bc8-142">Примеры</span><span class="sxs-lookup"><span data-stu-id="51bc8-142">Examples</span></span>

<span data-ttu-id="51bc8-143">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="51bc8-143">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MaxThreads": 20
      }
   }
}
```

<span data-ttu-id="51bc8-144">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="51bc8-144">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```
