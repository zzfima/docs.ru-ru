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
# <a name="run-time-configuration-options-for-threading"></a>Параметры конфигурации времени выполнения для потоков

## <a name="cpu-groups"></a>Группы ЦП

- Определяет, выполняется ли автоматическое распределение потоков между группами ЦП.
- По умолчанию: отключено (`0`).

| | Имя параметра | Значения |
| - | - | - |
| **runtimeconfig.json** | Н/Д | Н/Д |
| **Переменная среды** | `COMPlus_Thread_UseAllCpuGroups` | `0` — отключено<br/>`1` — включено |

## <a name="minimum-threads"></a>Минимальное число потоков

- Указывает минимальное число потоков для рабочего пула потоков.
- Соответствует методу <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType>.

| | Имя параметра | Значения |
| - | - | - |
| **runtimeconfig.json** | `System.Threading.ThreadPool.MinThreads` | Целочисленное значение, представляющее минимальное число потоков. |
| **Переменная среды** | Н/Д | Н/Д |

## <a name="maximum-threads"></a>Максимальное число потоков

- Указывает максимальное число потоков для рабочего пула потоков.
- Соответствует методу <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType>.

| | Имя параметра | Значения |
| - | - | - |
| **runtimeconfig.json** | `System.Threading.ThreadPool.MaxThreads` | Целочисленное значение, представляющее максимальное число потоков. |
| **Переменная среды** | Н/Д | Н/Д |
