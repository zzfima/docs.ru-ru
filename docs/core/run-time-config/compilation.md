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
# <a name="run-time-configuration-options-for-compilation"></a>Параметры конфигурации времени выполнения для компиляции

## <a name="tiered-compilation"></a>Многоуровневая компиляция

- Указывает, использует ли JIT-компилятор [многоуровневую компиляцию](../whats-new/dotnet-core-3-0.md#tiered-compilation).
- В .NET Core 3.0 и более поздних версий многоуровневая компиляция включена по умолчанию.
- В .NET Core 2.1 и 2.2 многоуровневая компиляция отключена по умолчанию.

| | Имя параметра | Значения |
| - | - | - |
| **runtimeconfig.json** | `System.Runtime.TieredCompilation` | `true` — включено<br/>`false` — отключено |
| **Переменная среды** | `COMPlus_TieredCompilation` | `1` — включено<br/>`0` — отключено |
