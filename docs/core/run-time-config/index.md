---
title: Конфигурация во время выполнения
description: Узнайте, как настроить приложения .NET Core с помощью параметров конфигурации среды выполнения.
ms.date: 11/13/2019
ms.openlocfilehash: f7074b07bdd5aca23b6caae78952d630d905c489
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283966"
---
# <a name="net-core-run-time-configuration-settings"></a>Параметры конфигурации среды выполнения .NET Core

.NET Core поддерживает использование файлов конфигурации и переменных среды для настройки поведения приложений .NET Core во время выполнения. Конфигурация среды выполнения является удобным вариантом в следующих случаях:

- Вы не владеете исходным кодом приложения или не можете управлять им, поэтому вы не можете задать соответствующие настройки программным способом.

- Вы одновременно запускаете несколько экземпляров приложения в одной системе и хотите настроить оптимальную производительность для каждого экземпляра.

> [!NOTE]
> Работа над этой документацией продолжается. Если вы заметили, что приведенные здесь сведения являются неполными или неточными, [создайте сообщение о проблеме](https://github.com/dotnet/docs/issues), чтобы оповестить нас об этом, или [отправьте запрос на вытягивание](https://github.com/dotnet/docs/pulls) для этой проблемы. Сведения о том, как отправлять запросы на вытягивание для репозитория dotnet/docs, см. в [руководстве участника](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).

.NET Core предоставляет следующие механизмы для настройки приложений во время выполнения:

- [Файл runtimeconfig.json](#runtimeconfigjson)

- [Переменные среды](#environment-variables)

Статьи в этом разделе документации упорядочены по категориям, например, "отладка" и "сборка мусора". Приведены доступные параметры конфигурации для файла *runtimeconfig.json* (только .NET Core), для файла *app.config* (только .NET Framework) и для переменных среды.

## <a name="runtimeconfigjson"></a>runtimeconfig.json

Укажите параметры конфигурации среды выполнения в разделе **configProperties** файла *runtimeconfig.json*. Этот раздел имеет следующий вид:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "config-property-name1": "config-value1",
         "config-property-name2": "config-value2"
      }
   }
}
```

Ниже приведен пример файла:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": true,
         "System.GC.RetainVM": true,
         "System.Threading.ThreadPool.MinThreads": "4",
         "System.Threading.ThreadPool.MaxThreads": "25"
      }
   }
}
```

Файл *runtimeconfig.json* автоматически создается в каталоге сборки командой [dotnet build](../tools/dotnet-build.md). Он также создается при выборе пункта меню **Сборка** в Visual Studio. После создания файла его можно изменить.

Значения некоторых параметров конфигурации также можно задать программным способом, вызвав метод <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.

## <a name="environment-variables"></a>Переменные среды

Переменные среды можно использовать для предоставления некоторых сведений о конфигурации среды выполнения. Элементы конфигурации, указанные в качестве переменных среды, обычно имеют префикс **COMPlus_** .

Переменные среды можно определить с помощью панели управления Windows, в командной строке или программным способом, вызвав метод <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> в Windows и системах на основе Unix.

В следующих примерах показано, как задать переменную среды в командной строке:

```shell
# Windows
set COMPlus_GCRetainVM=1

# Powershell
$env:COMPlus_GCRetainVM="1"

# Unix
export COMPlus_GCRetainVM=1
```
