---
title: Параметры конфигурации компиляции
description: Сведения о параметрах времени выполнения, определяющих, как JIT-компилятор работает для приложений .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: bcc445b6edc48d9432ee614b0b19c9c25621f4a0
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998879"
---
# <a name="run-time-configuration-options-for-compilation"></a><span data-ttu-id="acabb-103">Параметры конфигурации времени выполнения для компиляции</span><span class="sxs-lookup"><span data-stu-id="acabb-103">Run-time configuration options for compilation</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="acabb-104">Многоуровневая компиляция</span><span class="sxs-lookup"><span data-stu-id="acabb-104">Tiered compilation</span></span>

- <span data-ttu-id="acabb-105">Указывает, использует ли JIT-компилятор [многоуровневую компиляцию](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="acabb-105">Configures whether the JIT compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span>
- <span data-ttu-id="acabb-106">В .NET Core 3.0 и более поздних версий многоуровневая компиляция включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="acabb-106">In .NET Core 3.0 and later, tiered compilation is enabled by default.</span></span>
- <span data-ttu-id="acabb-107">В .NET Core 2.1 и 2.2 многоуровневая компиляция отключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="acabb-107">In .NET Core 2.1 and 2.2, tiered compilation is disabled by default.</span></span>

| | <span data-ttu-id="acabb-108">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="acabb-108">Setting name</span></span> | <span data-ttu-id="acabb-109">Значения</span><span class="sxs-lookup"><span data-stu-id="acabb-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="acabb-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="acabb-110">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation` | <span data-ttu-id="acabb-111">`true` — включено</span><span class="sxs-lookup"><span data-stu-id="acabb-111">`true` - enabled</span></span><br/><span data-ttu-id="acabb-112">`false` — отключено</span><span class="sxs-lookup"><span data-stu-id="acabb-112">`false` - disabled</span></span> |
| <span data-ttu-id="acabb-113">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="acabb-113">**Environment variable**</span></span> | `COMPlus_TieredCompilation` | <span data-ttu-id="acabb-114">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="acabb-114">`1` - enabled</span></span><br/><span data-ttu-id="acabb-115">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="acabb-115">`0` - disabled</span></span> |
