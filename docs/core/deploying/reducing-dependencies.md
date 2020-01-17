---
title: Сокращение зависимостей пакетов с помощью файла project.json
description: Сократите зависимости пакетов при создании библиотек на базе project.json.
author: cartermp
ms.date: 06/20/2016
ms.openlocfilehash: 48ba3ef578388fd98fe7cb830df313512d359483
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740823"
---
# <a name="reducing-package-dependencies-with-projectjson"></a>Сокращение зависимостей пакетов с помощью файла project.json

В этой статье приводятся необходимые сведения о сокращении зависимостей пакетов при разработке библиотек `project.json`. К концу этой статьи вы научитесь составлять библиотеки так, чтобы в них использовались только необходимые зависимости.

## <a name="why-its-important"></a>Почему это важно

.NET Core — это продукт, состоящий из пакетов NuGet.  Базовый пакет — это [метапакет NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library). Он представляет собой пакет NuGet, состоящий из других пакетов. Этот метапакет предоставляет набор пакетов, которые гарантированно работают в разных реализациях .NET, таких как .NET Framework, .NET Core и Xamarin/Mono.

Однако высока вероятность того, что ваша библиотека будет использовать не все входящие в него пакеты.  При разработке библиотеки и ее распространении посредством NuGet рекомендуется "усекать" зависимости, оставляя только действительно необходимые.  Результатом является уменьшение общего размера пакетов NuGet.

## <a name="how-to-do-it"></a>Как это сделать

Сейчас нет официальной команды `dotnet`, которая усекает ссылки на пакеты.  Вам потребуется сделать это вручную.  Ниже описывается общая процедура:

1. Укажите ссылку на `NETStandard.Library` версии `1.6.0` в разделе `dependencies` файла `project.json`.
2. Восстановите пакеты, выполнив команду `dotnet restore` ([см. примечание](#dotnet-restore-note)) в командной строке.
3. Просмотрите файл `project.lock.json` и найдите раздел `NETStandard.Library`.  Он находится ближе к началу файла.
4. Скопируйте все пакеты, перечисленные в разделе `dependencies`.
5. Удалите ссылку на `.NETStandard.Library` и замените ее скопированными пакетами.
6. Удалите ссылки на пакеты, которые вам не нужны.

Узнать, какие пакеты вам не нужны, можно одним из указанных ниже способов:

1. Методом проб и ошибок. То есть вам нужно удалить пакет, выполнить восстановление, проверить, компилируется ли по-прежнему библиотека, а затем повторить этот процесс.
2. С помощью такого средства, как [ILSpy](https://github.com/icsharpcode/ILSpy#ilspy-------) или [.NET Reflector](https://www.red-gate.com/products/dotnet-development/reflector), изучить ссылки, чтобы узнать, какие из них действительно используются в коде. Затем можно удалить пакеты, которые не соответствуют используемым типам.

## <a name="example"></a>Пример

Представьте, что вы написали библиотеку, расширяющую функциональность универсальных типов коллекций. Подобная библиотека обязательно будет зависеть от таких пакетов, как `System.Collections`, но может совершенно не использовать такие пакеты, как `System.Net.Http`. Поэтому было бы неплохо ограничить зависимости пакетов только теми, которые действительно требуются библиотеке.

Чтобы усечь зависимости в этой библиотеке, необходимо начать с файла `project.json` и добавить ссылку на `NETStandard.Library` версии `1.6.0`.

```json
{
    "version":"1.0.0",
    "dependencies":{
        "NETStandard.Library":"1.6.0"
    },
    "frameworks": {
        "netstandard1.0": {}
     }
}
```

Затем следует восстановить пакеты с помощью команды `dotnet restore` ([см. примечание](#dotnet-restore-note)), просмотреть файл `project.lock.json` и найти все пакеты, восстановленные для `NETStandard.Library`.

Вот как выглядит соответствующий раздел в файле `project.lock.json` при нацеливании на `netstandard1.0`.

```json
"NETStandard.Library/1.6.0":{
    "type": "package",
    "dependencies": {
        "Microsoft.NETCore.Platforms": "1.0.1",
        "Microsoft.NETCore.Runtime": "1.0.2",
        "System.Collections": "4.0.11",
        "System.Diagnostics.Debug": "4.0.11",
        "System.Diagnostics.Tools": "4.0.1",
        "System.Globalization": "4.0.11",
        "System.IO": "4.1.0",
        "System.Linq": "4.1.0",
        "System.Net.Primitives": "4.0.11",
        "System.ObjectModel": "4.0.12",
        "System.Reflection": "4.1.0",
        "System.Reflection.Extensions": "4.0.1",
        "System.Reflection.Primitives": "4.0.1",
        "System.Resources.ResourceManager": "4.0.1",
        "System.Runtime": "4.1.0",
        "System.Runtime.Extensions": "4.1.0",
        "System.Text.Encoding": "4.0.11",
        "System.Text.Encoding.Extensions": "4.0.11",
        "System.Text.RegularExpressions": "4.1.0",
        "System.Threading": "4.0.11",
        "System.Threading.Tasks": "4.0.11",
        "System.Xml.ReaderWriter": "4.0.11",
        "System.Xml.XDocument": "4.0.11"
    }
}
```

Далее скопируйте ссылки на пакеты в раздел `dependencies` файла `project.json` библиотеки, заменив ссылку на `NETStandard.Library`:

```json
{
    "version":"1.0.0",
    "dependencies":{
        "Microsoft.NETCore.Platforms": "1.0.1",
        "Microsoft.NETCore.Runtime": "1.0.2",
        "System.Collections": "4.0.11",
        "System.Diagnostics.Debug": "4.0.11",
        "System.Diagnostics.Tools": "4.0.1",
        "System.Globalization": "4.0.11",
        "System.IO": "4.1.0",
        "System.Linq": "4.1.0",
        "System.Net.Primitives": "4.0.11",
        "System.ObjectModel": "4.0.12",
        "System.Reflection": "4.1.0",
        "System.Reflection.Extensions": "4.0.1",
        "System.Reflection.Primitives": "4.0.1",
        "System.Resources.ResourceManager": "4.0.1",
        "System.Runtime": "4.1.0",
        "System.Runtime.Extensions": "4.1.0",
        "System.Text.Encoding": "4.0.11",
        "System.Text.Encoding.Extensions": "4.0.11",
        "System.Text.RegularExpressions": "4.1.0",
        "System.Threading": "4.0.11",
        "System.Threading.Tasks": "4.0.11",
        "System.Xml.ReaderWriter": "4.0.11",
        "System.Xml.XDocument": "4.0.11"
    },
    "frameworks":{
        "netstandard1.0": {}
    }
}
```

Получилось весьма много пакетов, многие из которых определенно не требуются для расширения типов коллекций.  Вы можете удалить пакеты вручную или использовать такое средство, как [ILSpy](https://github.com/icsharpcode/ILSpy#ilspy-------) или [.NET Reflector](https://www.red-gate.com/products/dotnet-development/reflector/), для определения пакетов, которые действительно используются в коде.

Вот как может выглядеть усеченный пакет.

```json
{
    "dependencies":{
        "Microsoft.NETCore.Platforms": "1.0.1",
        "Microsoft.NETCore.Runtime": "1.0.2",
        "System.Collections": "4.0.11",
        "System.Linq": "4.1.0",
        "System.Runtime": "4.1.0",
        "System.Runtime.Extensions": "4.1.0",
        "System.Runtime.Handles": "4.0.1",
        "System.Runtime.InteropServices": "4.1.0",
        "System.Runtime.InteropServices.RuntimeInformation": "4.0.0",
        "System.Threading.Tasks": "4.0.11"
    },
    "frameworks":{
        "netstandard1.0": {}
     }
}
```

Теперь он имеет меньший размер, чем если бы он зависел от метапакета `NETStandard.Library`.

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
