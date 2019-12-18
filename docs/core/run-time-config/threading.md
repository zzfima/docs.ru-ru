---
title: Параметры конфигурации потоков
description: Сведения о параметрах времени выполнения, определяющих использование потоков для приложений .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 6a920dbc301830e3f4c95bf637ff3de6d4f464ff
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998831"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="f441b-103">Параметры конфигурации времени выполнения для потоков</span><span class="sxs-lookup"><span data-stu-id="f441b-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="f441b-104">Группы ЦП</span><span class="sxs-lookup"><span data-stu-id="f441b-104">CPU groups</span></span>

- <span data-ttu-id="f441b-105">Определяет, выполняется ли автоматическое распределение потоков между группами ЦП.</span><span class="sxs-lookup"><span data-stu-id="f441b-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="f441b-106">По умолчанию: отключено (`0`).</span><span class="sxs-lookup"><span data-stu-id="f441b-106">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="f441b-107">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="f441b-107">Setting name</span></span> | <span data-ttu-id="f441b-108">Значения</span><span class="sxs-lookup"><span data-stu-id="f441b-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f441b-109">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f441b-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="f441b-110">Н/Д</span><span class="sxs-lookup"><span data-stu-id="f441b-110">N/A</span></span> | <span data-ttu-id="f441b-111">Н/Д</span><span class="sxs-lookup"><span data-stu-id="f441b-111">N/A</span></span> |
| <span data-ttu-id="f441b-112">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="f441b-112">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="f441b-113">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="f441b-113">`0` - disabled</span></span><br/><span data-ttu-id="f441b-114">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="f441b-114">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="f441b-115">Минимальное число потоков</span><span class="sxs-lookup"><span data-stu-id="f441b-115">Minimum threads</span></span>

- <span data-ttu-id="f441b-116">Указывает минимальное число потоков для рабочего пула потоков.</span><span class="sxs-lookup"><span data-stu-id="f441b-116">Specifies the minimum number of threads for the worker threadpool.</span></span>
- <span data-ttu-id="f441b-117">Соответствует методу <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f441b-117">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="f441b-118">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="f441b-118">Setting name</span></span> | <span data-ttu-id="f441b-119">Значения</span><span class="sxs-lookup"><span data-stu-id="f441b-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f441b-120">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f441b-120">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="f441b-121">Целочисленное значение, представляющее минимальное число потоков.</span><span class="sxs-lookup"><span data-stu-id="f441b-121">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="f441b-122">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="f441b-122">**Environment variable**</span></span> | <span data-ttu-id="f441b-123">Н/Д</span><span class="sxs-lookup"><span data-stu-id="f441b-123">N/A</span></span> | <span data-ttu-id="f441b-124">Н/Д</span><span class="sxs-lookup"><span data-stu-id="f441b-124">N/A</span></span> |

## <a name="maximum-threads"></a><span data-ttu-id="f441b-125">Максимальное число потоков</span><span class="sxs-lookup"><span data-stu-id="f441b-125">Maximum threads</span></span>

- <span data-ttu-id="f441b-126">Указывает максимальное число потоков для рабочего пула потоков.</span><span class="sxs-lookup"><span data-stu-id="f441b-126">Specifies the maximum number of threads for the worker threadpool.</span></span>
- <span data-ttu-id="f441b-127">Соответствует методу <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f441b-127">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="f441b-128">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="f441b-128">Setting name</span></span> | <span data-ttu-id="f441b-129">Значения</span><span class="sxs-lookup"><span data-stu-id="f441b-129">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f441b-130">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f441b-130">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="f441b-131">Целочисленное значение, представляющее максимальное число потоков.</span><span class="sxs-lookup"><span data-stu-id="f441b-131">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="f441b-132">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="f441b-132">**Environment variable**</span></span> | <span data-ttu-id="f441b-133">Н/Д</span><span class="sxs-lookup"><span data-stu-id="f441b-133">N/A</span></span> | <span data-ttu-id="f441b-134">Н/Д</span><span class="sxs-lookup"><span data-stu-id="f441b-134">N/A</span></span> |
