---
title: Сведения о .NET Core
description: Дополнительные сведения о .NET Core.
author: richlander
ms.author: mairaw
ms.date: 08/01/2018
ms.openlocfilehash: d9943246b683c8fd892e7bc5fd09a10b72e31a5f
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2018
ms.locfileid: "48252228"
---
# <a name="about-net-core"></a>Сведения о .NET Core

.NET Core обладает следующими характеристиками:

- **Кроссплатформенность.** Поддержка [операционных систем](https://github.com/dotnet/core/blob/master/os-lifecycle-policy.md) Windows, macOS и Linux.
- **Согласованность между архитектурами.** Одинаковое выполнение кода на различных архитектурах, включая x64, x86 и ARM.
- **Программы командной строки.** Удобные инструменты для локальной разработки и сценариев непрерывной интеграции.
- **Гибкая разработка.** Может включаться в приложение или устанавливаться параллельно на уровне пользователя или компьютера. Возможность использования с [контейнерами Docker](docker/index.md).
- **Совместимость.** Платформа .NET Core совместима с .NET Framework, Xamarin и Mono благодаря [.NET Standard](../standard/net-standard.md).
- **Открытый исходный код**: платформа .NET Core имеет открытый исходный код и распространяется по лицензиям MIT и Apache 2. .NET Core является проектом [.NET Foundation](https://dotnetfoundation.org/).
- **Поддержка от Майкрософт.** Корпорация Майкрософт предоставляет [поддержку .NET Core](https://www.microsoft.com/net/core/support/).

## <a name="languages"></a>Языки

.NET Core позволяет создавать приложения и библиотеки на языках C#, Visual Basic и F#. Эти языки уже интегрированы или могут быть интегрированы в ваши любимые текстовые редакторы и интегрированные среды разработки, такие как [Visual Studio](https://visualstudio.microsoft.com/vs/), [Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp), Sublime Text и Vim. Интеграция возможна во многом благодаря участникам проектов [OmniSharp](http://www.omnisharp.net/) и [Ionide](http://ionide.io).

## <a name="apis"></a>API - интерфейсы

.NET Core предоставляет API-интерфейсы для множества сценариев, в некоторых из которых используются:

- Примитивные типы, такие как [bool][bool] и [int][int].
- Коллекции, такие как <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> и <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>.
- Служебные типы, такие как <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> и <xref:System.IO.FileStream?displayProperty=nameWithType>.
- Типы данных, такие как <xref:System.Data.DataSet?displayProperty=nameWithType> и [DbSet][dbset].
- Высокопроизводительные типы, такие как <xref:System.Numerics.Vector?displayProperty=nameWithType> и [Pipelines][pipelines].

Благодаря поддержке спецификации [.NET Standard](../standard/net-standard.md) платформа .NET Core совместима с .NET Framework и API-интерфейсами Mono.

[bool]: https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/bool
[int]: https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/int
[pipelines]: https://blogs.msdn.microsoft.com/dotnet/2018/07/09/system-io-pipelines-high-performance-io-in-net/
[dbset]: https://www.nuget.org/packages/Microsoft.EntityFrameworkCore/

## <a name="frameworks"></a>Платформы

На основе .NET Core было создано множество платформ:

- [ASP.NET Core](/aspnet/core/)
- [Универсальная платформа Windows (UWP) для Windows 10](https://developer.microsoft.com/windows)
- [Tizen](https://developer.tizen.org/development/training/.net-application)

## <a name="composition"></a>Композиция

.NET Core состоит из перечисленных ниже компонентов:

- [Среда выполнения .NET Core](https://github.com/dotnet/coreclr) предоставляет систему типов, функции загрузки сборок, сборщик мусора, собственные функции взаимодействия и другие базовые службы. [Библиотеки платформы .NET Core](https://github.com/dotnet/corefx) предоставляют примитивные типы данных, типы компоновки приложений и базовые служебные программы.
- [Среда выполнения ASP.NET](https://github.com/aspnet/home) предоставляет платформу для создания современных облачных приложений, подключенных к Интернету: веб-приложений, приложений Интернета вещей, серверной части мобильных решений и многого другого.
- [Средства .NET Core CLI](https://github.com/dotnet/cli) и компиляторы языков ([Roslyn](https://github.com/dotnet/roslyn) и [F#](https://github.com/microsoft/visualfsharp)) реализуют возможности разработки .NET Core.
- [Средство dotnet](https://github.com/dotnet/core-setup) используется для запуска приложений .NET Core и инструментов командной строки. Оно выбирает среду выполнения, размещает ее, предоставляет политику загрузки сборок и запускает приложения и инструменты.

Эти компоненты распределены следующим образом:

- [Среда выполнения .NET Core](https://www.microsoft.com/net/download/dotnet-core/2.1) — включает среду выполнения .NET Core и библиотеки платформы.
- [Среда выполнения ASP.NET Core](https://www.microsoft.com/net/download/dotnet-core/2.1) — включает среды выполнения ASP.NET Core и .NET Core, а также библиотеки платформы.
- [Пакет SDK для .NET Core](https://www.microsoft.com/net/download/dotnet-core/2.1) — включает средства CLI .NET, среду выполнения ASP.NET Core, а также платформу и среду выполнения .NET Core.

### <a name="open-source"></a>Открытый исходный код

Платформа [.NET Core](https://github.com/dotnet/core) имеет открытый исходный код ([по лицензии MIT](https://github.com/dotnet/core/blob/master/LICENSE.TXT)) и была передана корпорацией Майкрософт в фонд [.NET Foundation](https://dotnetfoundation.org) в 2014 году. Теперь это один из самых активно развивающихся проектов .NET Foundation. Частные лица и организации могут свободно использовать платформу в личных, образовательных или коммерческих целях. Многие компании используют .NET Core в составе своих приложений, средств, новых платформ и услуг размещения. Некоторые из них вносят существенный вклад в проект .NET Core на портале GitHub и участвуют в управлении его развитием в рамках [Координационного совета .NET Foundation](https://dotnetfoundation.org/blog/tsg-welcome).

### <a name="designed-for-adaptability"></a>Поддержка адаптируемости

.NET Core — это очень похожая на другие продукты .NET, но в то же время уникальная платформа. При ее разработке ставилась цель обеспечить максимальную адаптируемость к новым платформам и рабочим нагрузкам. У нее есть порты на несколько ОС и ЦП, и она поддерживает перенос на многие другие платформы.

Продукт состоит из нескольких компонентов, каждый из которых может быть адаптирован к новым платформам отдельно и в разное время. Среда выполнения и основные библиотеки, связанные с платформой, должны переноситься как единое целое. Не зависящие от платформы библиотеки должны работать "как есть" на любой платформе. В рамках проекта имеется тенденция к ограничению реализаций, предназначенных для конкретных платформ, с целью повышения эффективности разработки: если алгоритм или интерфейс API можно полностью или частично реализовать с помощью независимого от платформы кода C#, предпочтение отдается именно такому варианту.

Люди часто спрашивают, как реализована поддержка нескольких операционных систем в .NET Core. Часто задают вопрос, имеются ли отдельные реализации или используется [условная компиляция](https://en.wikipedia.org/wiki/Conditional_compilation). Используются оба подхода, но с явным уклоном в сторону условной компиляции.

На приведенной ниже диаграмме видно, что [CoreFX](https://github.com/dotnet/corefx) по больше части представляет собой независимый от платформы код, который используется на всех платформах. Независимый от платформы код можно реализовать в виде одной переносимой сборки для всех платформ.

![CoreFX: строки кода для каждой платформы](../images/corefx-platforms-loc.png)

Реализации для Windows и Unix имеют сходный размер. Размер реализации для Windows больше, так как CoreFX реализует некоторые возможности, относящиеся только к Windows, такие как [Microsoft.Win32.Registry](https://github.com/dotnet/corefx/tree/master/src/Microsoft.Win32.Registry), но пока не реализует многие функции, характерные только для Unix. Также видно, что реализации для Linux и Mac OS используются в реализации для Unix, в то время как сами они имеют примерно одинаковый размер.

Платформа .NET Core состоит из сочетания зависимых и независимых от платформы библиотек. Это можно проследить на ряде примеров.

- Библиотека [CoreCLR](https://github.com/dotnet/coreclr) зависит от платформы. Она построена на основе подсистем ОС, таких как диспетчер памяти и планировщик потоков.
- Библиотеки [System.IO](https://github.com/dotnet/corefx/tree/master/src/System.IO) и [System.Security.Cryptography.Algorithms](https://github.com/dotnet/corefx/tree/master/src/System.Security.Cryptography.Algorithms) зависят от платформ, так как API-интерфейсы хранения и шифрования данных различаются в каждой ОС.
- Библиотеки [System.Collections](https://github.com/dotnet/corefx/tree/master/src/System.Collections) и [System.Linq](https://github.com/dotnet/corefx/tree/master/src/System.Linq) не зависят от платформы, так как они создают структуры данных и работают с ними.

## <a name="comparisons-to-other-net-implementations"></a>Сравнение с другими реализациями .NET

Масштаб и значение .NET Core проще всего понять в сравнении с существующими реализациями .NET.

### <a name="comparison-with-net-framework"></a>Сравнение с .NET Framework

Платформа .NET была представлена корпорацией Майкрософт в 2000 году и с тех пор прошла долгий путь развития. .NET Framework была основной реализацией .NET, которую корпорация Майкрософт предлагала почти два десятилетия.

Основные различия между .NET Core и .NET Framework

- **Модели приложений** — .NET Core поддерживает не все модели приложений платформы .NET Framework. В частности, она не поддерживает веб-формы ASP.NET и MVC. Было объявлено, что [.NET Core 3 будет поддерживать WPF и Windows Forms](https://blogs.msdn.microsoft.com/dotnet/2018/05/07/net-core-3-and-support-for-windows-desktop-applications/).
- **API-интерфейсы** — .NET Core включает обширное подмножество библиотеки базовых классов .NET Framework с отличающейся организацией кода (другие имена сборок и ключевые отличия в членах, предоставляемых для типов). Из-за этих различий в некоторых случаях необходимы изменения при портировании исходного кода на .NET Core (см. [microsoft/dotnet-apiport](https://github.com/microsoft/dotnet-apiport)). .NET Core реализует спецификацию API [.NET Standard](../standard/net-standard.md).
- **Подсистемы**. Платформа .NET Core реализует подмножество подсистем .NET Framework с целью упрощения реализации и модели программирования. Например, управление доступом для кода (CAS) не поддерживается, а отражение поддерживается.
- **Платформы**. Платформа .NET Framework поддерживает Windows и Windows Server, в то время как .NET Core также поддерживает Mac OS и Linux.
- **Открытый исходный код**. Платформа .NET Core имеет открытый исходный код. В случае с .NET Framework открытый исходный код имеет только [подмножество библиотек, доступных только для чтения](https://github.com/microsoft/referencesource).

Хотя платформа .NET Core является уникальной и существенно отличается от .NET Framework и других реализаций .NET, вы можете легко использовать один и тот же код в разных реализациях как в формате исходного кода, так и в виде двоичных файлов.

### <a name="comparison-with-mono"></a>Сравнение с Mono

[Mono](http://www.mono-project.com/) — это первая кроссплатформенная реализация .NET с [открытым исходным кодом](https://github.com/mono/mono), которая была представлена в 2004 году. Ее можно считать аналогом .NET Framework, предоставляемым сообществом. Команда проекта Mono использовала открытые [стандарты .NET](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/dotnet-standards.md) (в частности, ECMA 335), опубликованные корпорацией Майкрософт, для предоставления совместимой реализации.

Основные различия между .NET Core и Mono

- **Модели приложений**. Mono поддерживает подмножество моделей приложений .NET Framework (например, Windows Forms), а также ряд дополнительных моделей (например, [Xamarin.iOS](https://www.xamarin.com/platform)) посредством продукта Xamarin. Платформа .NET Core не поддерживает их.
- **Интерфейсы API**. Mono поддерживает [большое подмножество](http://docs.go-mono.com/?link=root%3a%2fclasslib) интерфейсов API .NET Framework с использованием тех же имен сборок и факторинга.
- **Платформы**. Mono поддерживает множество платформ и ЦП.
- **Открытый исходный код**. Как Mono, так и .NET Core распространяются по лицензии MIT и являются проектами .NET Foundation.
- **Концентрация**. В последние годы платформа Mono в первую очередь нацелена на мобильные платформы, в то время как платформа .NET Core ориентирована на рабочие нагрузки для облака и настольных компьютеров.
