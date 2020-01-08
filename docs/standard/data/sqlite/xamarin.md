---
title: Ограничения Xamarin
ms.date: 12/13/2019
description: Описание некоторых ограничений, которые будут возникать при использовании Xamarin.
ms.openlocfilehash: 192f25954726919dc66d706e755e0853404b4d85
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450408"
---
# <a name="xamarin-limitations"></a>Ограничения Xamarin

Microsoft. Data. SQLite предназначен для .NET Standard 2,0 и поддерживается в Xamarin. В следующей таблице показано, на каких платформах пакет Склитепклрав по умолчанию предоставляет собственные двоичные файлы SQLite для. Дополнительные сведения об использовании разных наборов или предоставлении собственных двоичных файлов SQLite см. в разделе [пользовательские версии SQLite](custom-versions.md) .

| Platform | Двоичные файлы SQLite |
| --- | --- |
| **Xamarin.Android** | — |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64-v8a` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`armeabi-v7a` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86_64` | ✔ |
| **Xamarin.iOS** | ✔ |
| **Xamarin.Mac** | ✔ |
| **Xamarin. TVOS** | ✔ |
| **UWP** | — |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x64` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | ✔ |

## <a name="ios"></a>iOS

Microsoft. Data. SQLite пытается автоматически инициализировать пакеты Склитепклрав. К сожалению, из-за ограничений для компиляции Xamarin. iOS на момент времени (AOT) попытка завершается неудачей и появляется следующая ошибка.

> Необходимо вызвать `SQLitePCL.raw.SetProvider()`. Если вы используете пакет пакета, это делается путем вызова `SQLitePCL.Batteries.Init()`.

Чтобы инициализировать пакет, добавьте следующую строку кода в приложение перед использованием Microsoft. Data. SQLite.

```csharp
SQLitePCL.Batteries_V2.Init();
```

## <a name="see-also"></a>См. также:

* [Ограничения Async](async.md)
* [Пользовательские версии SQLite](custom-versions.md)
