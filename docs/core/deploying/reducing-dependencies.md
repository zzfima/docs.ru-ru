---
title: "Сокращение зависимостей пакетов с помощью файла project.json"
description: "Сокращение зависимостей пакетов с помощью файла project.json"
keywords: .NET, .NET Core
author: cartermp
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 916251e3-87f9-4eee-81ec-94076215e6fa
translationtype: Human Translation
ms.sourcegitcommit: 62fdb3e60b206728d86220076867eb8fd68af82e
ms.openlocfilehash: 77d49a1df361823c3f8f676923960d4bef2eeb08

---

# <a name="reducing-package-dependencies-with-projectjson"></a>Сокращение зависимостей пакетов с помощью файла project.json

В этой статье приводятся необходимые сведения о сокращении зависимостей пакетов при разработке библиотек `project.json`. К концу этой статьи вы научитесь составлять библиотеки так, чтобы в них использовались только необходимые зависимости. 

## <a name="why-its-important"></a>Почему это важно

.NET Core — это продукт, состоящий из пакетов NuGet.  Базовый пакет — это [метапакет библиотеки .NET Standard](https://www.nuget.org/packages/NETStandard.Library). Он представляет собой пакет NuGet, состоящий из других пакетов.  Этот метапакет предоставляет набор пакетов, которые гарантированно работают в различных реализациях .NET, таких как .NET Framework, .NET Core и Xamarin/Mono.

Однако высока вероятность того, что ваша библиотека будет использовать не все входящие в него пакеты.  При разработке библиотеки и ее распространении посредством NuGet рекомендуется "усекать" зависимости, оставляя только действительно необходимые.  Результатом является уменьшение общего размера пакетов NuGet.

## <a name="how-to-do-it"></a>Как это сделать

В настоящее время нет официальной команды `dotnet`, которая усекает ссылки на пакеты.  Вам потребуется сделать это вручную.  Ниже описывается общая процедура:

1. Укажите ссылку на `NETStandard.Library` версии `1.6.0` в разделе `dependencies` файла `project.json`.
2. Восстановите пакеты, выполнив команду `dotnet restore` в командной строке.
3. Просмотрите файл `project.lock.json` и найдите раздел `NETSTandard.Library`.  Он находится ближе к началу файла.
4. Скопируйте все пакеты, перечисленные в разделе `dependencies`.
5. Удалите ссылку на `.NETStandard.Library` и замените ее скопированными пакетами.
6. Удалите ссылки на пакеты, которые вам не нужны.

Узнать, какие пакеты вам не нужны, можно одним из указанных ниже способов:

1. Методом проб и ошибок.  То есть вам нужно удалить пакет, выполнить восстановление, проверить, компилируется ли по-прежнему библиотека, а затем повторить этот процесс.
2. С помощью такого средства, как [ILSpy](http://ilspy.net) или [.NET Reflector](http://www.red-gate.com/products/dotnet-development/reflector), изучить ссылки, чтобы узнать, какие из них действительно используются в коде.  Затем можно удалить пакеты, которые не соответствуют используемым типам.

## <a name="example"></a>Пример 

Представьте, что вы написали библиотеку, расширяющую функциональность универсальных типов коллекций.  Подобная библиотека обязательно будет зависеть от таких пакетов, как `System.Collections`, но может совершенно не использовать такие пакеты, как `System.Net.Http`.  Поэтому было бы неплохо ограничить зависимости пакетов только теми, которые действительно требуются библиотеке.

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

Затем следует восстановить пакеты с помощью команды `dotnet restore`, просмотреть файл `project.lock.json` и найти все пакеты, восстановленные для `NETSTandard.Library`.

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

Получилось весьма много пакетов, многие из которых определенно не требуются для расширения типов коллекций.  Вы можете удалить пакеты вручную или использовать такое средство, как [ILSpy](http://ilspy.net) или [.NET Reflector](http://www.red-gate.com/products/dotnet-development/reflector), для определения пакетов, которые действительно используются в коде.

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



<!--HONumber=Nov16_HO3-->


