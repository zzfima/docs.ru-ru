---
title: Параметры конфигурации потоков
description: Сведения о параметрах времени выполнения, определяющих использование потоков для приложений .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 68b8e93ca6ec3f708a7a627307655ada1955500a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "76789852"
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
| **Свойство MSBuild** | `ThreadPoolMinThreads` | Целочисленное значение, представляющее минимальное число потоков. |
| **Переменная среды** | Н/Д | Н/Д |

### <a name="examples"></a>Примеры

Файл *runtimeconfig.json*

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MinThreads": 4
      }
   }
}
```

Файл проекта:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>

</Project>
```

## <a name="maximum-threads"></a>Максимальное число потоков

- Указывает максимальное число потоков для рабочего пула потоков.
- Соответствует методу <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType>.

| | Имя параметра | Значения |
| - | - | - |
| **runtimeconfig.json** | `System.Threading.ThreadPool.MaxThreads` | Целочисленное значение, представляющее максимальное число потоков. |
| **Свойство MSBuild** | `ThreadPoolMaxThreads` | Целочисленное значение, представляющее максимальное число потоков. |
| **Переменная среды** | Н/Д | Н/Д |

### <a name="examples"></a>Примеры

Файл *runtimeconfig.json*

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MaxThreads": 20
      }
   }
}
```

Файл проекта:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```
