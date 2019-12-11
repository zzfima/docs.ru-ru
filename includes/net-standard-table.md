---
ms.openlocfilehash: 9e95db8a1530fabd30b5344c87728b9210c0ad69
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802831"
---
| .NET Standard              | [1.0]  | [1.1]  | [1.2] | [1.3] | [1.4] | [1.5]              | [1.6]              | [2.0]               | [2.1] |
|----------------------------|--------|--------|-------|-------|-------|--------------------|--------------------|---------------------|---------------------
| .NET Core                  | 1.0    | 1.0    | 1.0   | 1.0   | 1.0   | 1.0                | 1.0                | 2.0                 | 3.0 |
| .NET Framework <sup>1</sup>| 4.5    | 4.5    | 4.5.1 | 4.6   | 4.6.1 | 4.6.1<sup>2</sup> | 4.6.1<sup>2</sup> | 4.6.1<sup>2</sup>  | N/A<sup>3</sup> |
| Mono                       | 4.6    | 4.6    | 4.6   | 4.6   | 4.6   | 4.6                | 4.6                | 5,4                 | 6.4 |
| Xamarin.iOS                | 10.0   | 10.0   | 10.0  | 10.0  | 10.0  | 10.0               | 10.0               | 10.14               | 12.16 |
| Xamarin.Mac                | 3.0    | 3.0    | 3.0   | 3.0   | 3.0   | 3.0                | 3.0                | 3.8                 | 5.16 |
| Xamarin.Android            | 7.0    | 7.0    | 7.0   | 7.0   | 7.0   | 7.0                | 7.0                | 8.0                 | 10.0 |
| Универсальная платформа Windows | 10.0   | 10.0   | 10.0  | 10.0  | 10.0  | 10.0.16299         | 10.0.16299         | 10.0.16299          | TBD |
| Unity                      | 2018.1 | 2018.1 | 2018.1| 2018.1| 2018.1| 2018.1             |  2018.1            | 2018.1              | TBD |

<sup>1 Перечисленные версии для .NET Framework применимы к пакету SDK для .NET Core 2.0 и инструментарию более поздних версий. В предыдущих версиях использовалось другое сопоставление для .NET Standard 1.5 и более поздних версий. Если вы не можете обновить Visual Studio до версии 2017 и выше, можно [скачать инструментарий для средств .NET Core для Visual Studio 2015](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md).</sup>

<sup>2. Перечисленные здесь версии соответствуют правилам, которые NuGet использует для определения применимости указанной библиотеки .NET Standard. Хотя NuGet считает, что .NET Framework 4.6.1 поддерживает .NET Standard с версии 1.5 до 2.0, существует ряд проблем с использованием библиотек .NET Standard, созданных для этих версий из проектов .NET Framework 4.6.1. Для проектов .NET Framework, которым нужно использовать такие библиотеки, рекомендуем обновить проект и использовать в качестве целевой версию .NET Framework 4.7.2 или выше.</sup>

<sup>3 .NET Framework не поддерживает .NET Standard 2.1 или более поздних версий. Дополнительные сведения см. в [объявлении .NET Standard 2.1](https://devblogs.microsoft.com/dotnet/announcing-net-standard-2-1/).</sup>

- Столбцы представляют версии .NET Standard. Каждая ячейка заголовка содержит ссылку на документ, который показывает, какие интерфейсы API добавлены в соответствующей версии .NET Standard.
- Строки представляют различные реализации .NET.
- Номер версии в каждой ячейке обозначает *минимальную* версию реализации, которая потребуется для работы с соответствующей версией .NET Standard.
- На сайте [Версии .NET Standard](https://dotnet.microsoft.com/platform/dotnet-standard#versions) доступна интерактивная таблица.

[1.0]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.0.md
[1.1]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.1.md
[1.2]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.2.md
[1.3]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.3.md
[1.4]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.4.md
[1.5]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.5.md
[1.6]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.6.md
[2.0]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard2.0.md
[2.1]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard2.1.md
