---
title: Параметры конфигурации потоков
description: Сведения о параметрах времени выполнения, определяющих использование потоков для приложений .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 68b8e93ca6ec3f708a7a627307655ada1955500a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789852"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="5c5d7-103">Параметры конфигурации времени выполнения для потоков</span><span class="sxs-lookup"><span data-stu-id="5c5d7-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="5c5d7-104">Группы ЦП</span><span class="sxs-lookup"><span data-stu-id="5c5d7-104">CPU groups</span></span>

- <span data-ttu-id="5c5d7-105">Определяет, выполняется ли автоматическое распределение потоков между группами ЦП.</span><span class="sxs-lookup"><span data-stu-id="5c5d7-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="5c5d7-106">По умолчанию: отключено (`0`).</span><span class="sxs-lookup"><span data-stu-id="5c5d7-106">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="5c5d7-107">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="5c5d7-107">Setting name</span></span> | <span data-ttu-id="5c5d7-108">Значения</span><span class="sxs-lookup"><span data-stu-id="5c5d7-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="5c5d7-109">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="5c5d7-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="5c5d7-110">Н/Д</span><span class="sxs-lookup"><span data-stu-id="5c5d7-110">N/A</span></span> | <span data-ttu-id="5c5d7-111">Н/Д</span><span class="sxs-lookup"><span data-stu-id="5c5d7-111">N/A</span></span> |
| <span data-ttu-id="5c5d7-112">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="5c5d7-112">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="5c5d7-113">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="5c5d7-113">`0` - disabled</span></span><br/><span data-ttu-id="5c5d7-114">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="5c5d7-114">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="5c5d7-115">Минимальное число потоков</span><span class="sxs-lookup"><span data-stu-id="5c5d7-115">Minimum threads</span></span>

- <span data-ttu-id="5c5d7-116">Указывает минимальное число потоков для рабочего пула потоков.</span><span class="sxs-lookup"><span data-stu-id="5c5d7-116">Specifies the minimum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="5c5d7-117">Соответствует методу <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5c5d7-117">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="5c5d7-118">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="5c5d7-118">Setting name</span></span> | <span data-ttu-id="5c5d7-119">Значения</span><span class="sxs-lookup"><span data-stu-id="5c5d7-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="5c5d7-120">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="5c5d7-120">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="5c5d7-121">Целочисленное значение, представляющее минимальное число потоков.</span><span class="sxs-lookup"><span data-stu-id="5c5d7-121">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="5c5d7-122">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="5c5d7-122">**MSBuild property**</span></span> | `ThreadPoolMinThreads` | <span data-ttu-id="5c5d7-123">Целочисленное значение, представляющее минимальное число потоков.</span><span class="sxs-lookup"><span data-stu-id="5c5d7-123">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="5c5d7-124">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="5c5d7-124">**Environment variable**</span></span> | <span data-ttu-id="5c5d7-125">Н/Д</span><span class="sxs-lookup"><span data-stu-id="5c5d7-125">N/A</span></span> | <span data-ttu-id="5c5d7-126">Н/Д</span><span class="sxs-lookup"><span data-stu-id="5c5d7-126">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="5c5d7-127">Примеры</span><span class="sxs-lookup"><span data-stu-id="5c5d7-127">Examples</span></span>

<span data-ttu-id="5c5d7-128">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="5c5d7-128">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MinThreads": 4
      }
   }
}
```

<span data-ttu-id="5c5d7-129">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="5c5d7-129">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>

</Project>
```

## <a name="maximum-threads"></a><span data-ttu-id="5c5d7-130">Максимальное число потоков</span><span class="sxs-lookup"><span data-stu-id="5c5d7-130">Maximum threads</span></span>

- <span data-ttu-id="5c5d7-131">Указывает максимальное число потоков для рабочего пула потоков.</span><span class="sxs-lookup"><span data-stu-id="5c5d7-131">Specifies the maximum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="5c5d7-132">Соответствует методу <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5c5d7-132">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="5c5d7-133">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="5c5d7-133">Setting name</span></span> | <span data-ttu-id="5c5d7-134">Значения</span><span class="sxs-lookup"><span data-stu-id="5c5d7-134">Values</span></span> |
| - | - | - |
| <span data-ttu-id="5c5d7-135">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="5c5d7-135">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="5c5d7-136">Целочисленное значение, представляющее максимальное число потоков.</span><span class="sxs-lookup"><span data-stu-id="5c5d7-136">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="5c5d7-137">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="5c5d7-137">**MSBuild property**</span></span> | `ThreadPoolMaxThreads` | <span data-ttu-id="5c5d7-138">Целочисленное значение, представляющее максимальное число потоков.</span><span class="sxs-lookup"><span data-stu-id="5c5d7-138">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="5c5d7-139">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="5c5d7-139">**Environment variable**</span></span> | <span data-ttu-id="5c5d7-140">Н/Д</span><span class="sxs-lookup"><span data-stu-id="5c5d7-140">N/A</span></span> | <span data-ttu-id="5c5d7-141">Н/Д</span><span class="sxs-lookup"><span data-stu-id="5c5d7-141">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="5c5d7-142">Примеры</span><span class="sxs-lookup"><span data-stu-id="5c5d7-142">Examples</span></span>

<span data-ttu-id="5c5d7-143">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="5c5d7-143">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MaxThreads": 20
      }
   }
}
```

<span data-ttu-id="5c5d7-144">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="5c5d7-144">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```
