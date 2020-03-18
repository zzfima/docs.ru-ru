---
title: Команда dotnet add package
description: Команду dotnet list package удобно использовать для получения списка ссылок на пакеты для проекта или решения.
ms.date: 02/14/2020
ms.openlocfilehash: 1cb52b8de10b2eef2ef7465f04316e9446318763
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78157236"
---
# <a name="dotnet-list-package"></a>dotnet list package

**Эта статья относится к следующему** ✔️ SDK для .NET Core 2.2 и более поздних версий

## <a name="name"></a>Имя

`dotnet list package` — перечисляет ссылки на пакет для проекта или решения.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet list [<PROJECT>|<SOLUTION>] package [--config] [--framework] [--highest-minor] [--highest-patch]
   [--include-prerelease] [--include-transitive] [--interactive] [--outdated] [--source]
dotnet list package [-h|--help]
```

## <a name="description"></a>Описание:

Команду `dotnet list package` удобно использовать для получения списка всех ссылок на пакеты NuGet для определенного проекта или решения. Сначала нужно создать проект, чтобы получить ресурсы, необходимые для обработки этой командой. В следующем примере показаны выходные данные команды `dotnet list package` для проекта [SentimentAnalysis](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis):

```output
Project 'SentimentAnalysis' has the following package references
   [netcoreapp2.1]:
   Top-level Package               Requested   Resolved
   > Microsoft.ML                  1.4.0       1.4.0
   > Microsoft.NETCore.App   (A)   [2.1.0, )   2.1.0

(A) : Auto-referenced package.
```

В столбце **Requested** приводится ссылка на версию пакета, указанную в файле проекта. Это может быть и диапазон версий. В столбце **Resolved** указана версия, которая сейчас используется в проекте. Это значение всегда является одиночным. Символ `(A)`, отображающийся рядом с именами пакетов, обозначает [неявные ссылки на пакеты](csproj.md#implicit-package-references). Такие ссылки получены из параметров проекта (тип `Sdk`, свойство `<TargetFramework>` или `<TargetFrameworks>` и т. д.)

Используйте параметр `--outdated`, чтобы узнать, доступны ли новые версии пакетов, которые вы используете в проектах. По умолчанию параметр `--outdated` выводит список последних стабильных версий пакетов, если разрешенная версия не является предварительной версией. Чтобы при отображении списка новых версий отображались и предварительные версии, укажите параметр `--include-prerelease`. Ниже приведены выходные данные команды `dotnet list package --outdated --include-prerelease` для тоже же проекта, как и в предыдущем примере:

```output
The following sources were used:
   https://api.nuget.org/v3/index.json
   C:\Program Files (x86)\Microsoft SDKs\NuGetPackages\

Project `SentimentAnalysis` has the following updates to its packages
   [netcoreapp2.1]:
   Top-level Package      Requested   Resolved   Latest
   > Microsoft.ML         1.4.0       1.4.0      1.5.0-preview
```

Чтобы узнать, есть ли у проекта транзитивные зависимости, воспользуйтесь параметром `--include-transitive`. Транзитивные зависимости возникают при добавлении пакета в проект, который в свою очередь зависит от другого пакета. В следующем примере показаны выходные данные выполнения команды `dotnet list package --include-transitive` для проекта [HelloPlugin](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin/HelloPlugin), в которых отображаются пакеты верхнего уровня и пакеты, от которых они зависят:

```output
Project 'HelloPlugin' has the following package references
   [netcoreapp3.0]:
   Transitive Package      Resolved
   > PluginBase            1.0.0
```

## <a name="arguments"></a>Аргументы

`PROJECT | SOLUTION`

Файл проекта или решения для выполнения операции. Если он не указан, команда ищет текущий каталог для него. Если найдено несколько решений или проектов, появится сообщение об ошибке.

## <a name="options"></a>Параметры

- **`--config <SOURCE>`**

  Источники NuGet, используемые при поиске более новых версий пакетов. Требует указать параметр `--outdated`.

- **`--framework <FRAMEWORK>`**

  Отображает только пакеты для указанной [целевой платформы](../../standard/frameworks.md). Чтобы указать несколько платформ, задайте параметр несколько раз. Пример: `--framework netcoreapp2.2 --framework netstandard2.0`.

- **`-h|--help`**

  Выводит краткую справку по команде.

- **`--highest-minor`**

  Учитывает только пакеты с соответствующим номером основной версии при поиске более новых версий пакетов. Требует указать параметр `--outdated`.

- **`--highest-patch`**

  Учитывает только пакеты с соответствующими номерами основной и дополнительной версий при поиске более новых версий пакетов. Требует указать параметр `--outdated`.

- **`--include-prerelease`**

  Учитывает пакеты с предварительными версиями при поиске более новых версий пакетов. Требует указать параметр `--outdated`.

- **`--include-transitive`**

  Выводит список транзитивных пакетов, кроме пакетов верхнего уровня. Указав этот параметр, вы получите список пакетов, от которых зависят пакеты верхнего уровня.

- **`--interactive`**

  Позволяет команде остановиться и дождаться, пока пользователь выполнит действие или введет данные. Например, чтобы завершить проверку подлинности. Доступно, начиная с пакета SDK для .NET Core 3.0.

- **`--outdated`**

  Позволяет получить список пакетов, для которых доступны более новые версии.

- **`-s|--source <SOURCE>`**

  Источники NuGet, используемые при поиске более новых версий пакетов. Требует указать параметр `--outdated`.

## <a name="examples"></a>Примеры

- Вывод списка ссылок на пакеты определенного проекта:

  ```dotnetcli
  dotnet list SentimentAnalysis.csproj package
  ```

- Вывод списка ссылок на пакеты, для которых доступны более новые версии, включая предварительные версии:

  ```dotnetcli
  dotnet list package --outdated --include-prerelease
  ```

- Вывод списка ссылок на пакеты для определенной целевой платформы:

  ```dotnetcli
  dotnet list package --framework netcoreapp3.0
  ```
