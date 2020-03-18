---
title: .NET Standard
description: Сведения о .NET Standard, ее версиях и реализациях .NET, которые ее поддерживают.
ms.date: 02/13/2020
ms.technology: dotnet-standard
ms.custom: updateeachrelease
ms.assetid: c044882c-af15-45f2-96d1-534557a5ee9b
ms.openlocfilehash: 00b40b771a8608bad7e3f992e3c99367ff6bb131
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "77452595"
---
# <a name="net-standard"></a>.NET Standard

[.NET Standard](https://github.com/dotnet/standard) — это официальная спецификация API .NET, которые должны быть доступны во всех реализациях .NET. .NET Standard создана для того, чтобы повысить согласованность в экосистеме .NET. [ECMA 335](https://github.com/dotnet/runtime/blob/master/docs/project/dotnet-standards.md) продолжает обеспечивать единообразие для реализации .NET. Но так как в ECMA 335 определен лишь небольшой набор стандартных библиотек, спецификация .NET Standard охватывает более широкий спектр API-интерфейсов .NET.

.NET Standard предоставляет следующие важные возможности:

- Определяет унифицированный набор API-интерфейсов BCL для реализации всеми реализациями .NET независимо от рабочей нагрузки.
- Позволяет разработчикам создавать переносимые библиотеки, которые могут использоваться в разных реализациях .NET, с помощью одного набора API-интерфейсов.
- Позволяет сократить или даже устранить условную компиляцию общего источника из-за API-интерфейсов .NET (только для API операционной системы).

Различные реализации .NET реализуют конкретные версии .NET Standard. Каждая версия реализации .NET ориентирована на использование максимальной поддерживаемой ею версии .NET Standard. Это также означает, что она поддерживает и предыдущие версии. Например, .NET Framework 4.6 реализует .NET Standard 1.3, то есть предоставляет все API, определенные в стандартах .NET Standard версий 1.0–1.3. Аналогичным образом .NET Framework 4.6.1 реализует .NET Standard 1.4, а .NET Core 1.0 — .NET Standard 1.6.

## <a name="net-implementation-support"></a>Поддержка реализации .NET

В следующей таблице перечислены **минимальные** версии платформы, которые поддерживают каждую версию .NET Standard. Это означает, что более поздние версии перечисленных платформ также поддерживают соответствующую версию .NET Standard. К примеру, .NET Core 2.2 поддерживает .NET Standard 2.0 и более ранних версий.

[!INCLUDE [net-standard-table](../../includes/net-standard-table.md)]

Чтобы найти самую позднюю версию .NET Standard, на которую можно ориентироваться, выполните следующее:

1. Найдите строку, которая соответствует вашей реализации .NET.
2. Двигаясь по этой строке справа налево, найдите столбец, который содержит вашу версию платформы.
3. Заголовок столбца указывает версию .NET Standard, которую поддерживает ваша целевая платформа. Соответственно, поддерживаются и все более ранние версии .NET Standard. Более поздние версии .NET Standard также будет поддерживать текущую реализацию.
4. Повторите эту процедуру для всех платформ, с которыми вы будете работать. Если целевых платформ несколько, выберите из них самую младшую версию. Например, если вы хотите работать с .NET Framework 4.5 и .NET Core 1.0, наивысшей доступной версией .NET Standard будет .NET Standard 1.1.

### <a name="which-net-standard-version-to-target"></a>Какую версию .NET Standard выбрать в качестве целевой

При выборе версии .NET Standard перед вами стоит такая дилемма:

- Чем выше версия, тем больше вам доступно интерфейсов API.
- Чем ниже версия, тем больше платформ ее поддерживают.

В общем случае мы рекомендуем выбирать *наименьшую* из возможных версий .NET Standard. После того, как вы определите номер наибольшей возможной версии .NET Standard, выполните следующие действия.

1. Выберите предыдущую версию .NET Standard, создайте и соберите проект для нее.
2. Если сборка проекта пройдет успешно, повторите шаг 1. В противном случае вернитесь к предыдущей, более высокой, версии, и используйте именно ее.

Но при выборе более ранних версий .NET Standard предоставляются различные возможности для поддержки зависимостей. Если проект предназначен для .NET Standard 1.x, мы рекомендуем вам *также* выбрать .NET Standard 2.0. Это упростит схему зависимостей для пользователей библиотеки, выполняющейся на совместимых платформах с .NET Standard 2.0, и сократит количество пакетов, которые необходимо скачать.

### <a name="net-standard-versioning-rules"></a>Правила управления версиями .NET Standard

Существует два основных правила управления версиями.

- Аддитивность. Все версии .NET Standard логически расширяются, то есть более поздние версии содержат все интерфейсы API предыдущих версий. Отсутствуют критические изменения между версиями.
- Неизменяемость. Версии .NET после выпуска закрепляются в определенном состоянии. Новые интерфейсы API сначала становятся доступными для конкретных реализаций .NET, например .NET Core. Если совет по утверждению .NET Standard решает, что новые интерфейсы API нужно сделать доступными для всех реализаций .NET, их добавляют в новую версию .NET Standard.

## <a name="specification"></a>Спецификация

Спецификация .NET Standard представляет собой стандартизированный набор API. Она поддерживается реализаторами .NET, в частности корпорацией Майкрософт (для платформ .NET Framework, .NET Core и Mono) и Unity. При создании новых версий .NET Standard на [GitHub](https://github.com/dotnet/standard) используется процесс открытой обратной связи.

### <a name="official-artifacts"></a>Официальные артефакты

Официальная спецификация — это набор CS-файлов, которые определяют API, входящие в стандарт. [ref directory](https://github.com/dotnet/standard/tree/master/src/netstandard/ref) в [репозиторий dotnet/standard](https://github.com/dotnet/standard) определяет стандартные API-интерфейсы .NET.

Метапакет [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library) ([источник](https://github.com/dotnet/standard/blob/master/src/netstandard/pkg/NETStandard.Library.dependencies.props)) описывает набор библиотек, определяющих (частично) одну версию .NET Standard.или несколько.

Отдельный компонент, например `System.Runtime`, описывает следующее:

- часть .NET Standard (только область действия);
- несколько версий .NET Standard для данной области.

Доступны производные артефакты, упрощающие чтение и реализующие определенные сценарии для разработчика (например, использование компилятора).

- [Список API с разметкой](https://github.com/dotnet/standard/tree/master/docs/versions)
- Ссылочные сборки, распространяемые в виде [пакетов NuGet](../core/packages.md) и указанные в ссылках метапакета [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library/).

### <a name="package-representation"></a>Представление пакетов

Основным средством распространения ссылочных сборок .NET Standard являются [пакеты NuGet](../core/packages.md). Соответствующие реализации предоставляются различными способами, наиболее уместными для каждой реализации .NET.

Пакеты NuGet нацелены на одну или несколько [платформ](frameworks.md). Пакеты библиотеки .NET Standard нацелены на платформу ".NET Standard". Настроить использование .NET Standard можно с помощью [компактного моникера целевой платформы](frameworks.md) `netstandard` (например, `netstandard1.4`). Библиотеки, предназначенные для различных сред выполнения, должны быть нацелены на эту платформу. Для самого широкого набора API-интерфейсов выберите `netstandard2.0`, так как количество доступных API-интерфейсов увеличилось более чем вдвое между версиями .NET Standard 1.6 и 2.0.

Метапакет [`NETStandard.Library`](https://www.nuget.org/packages/NETStandard.Library/) ссылается на полный набор пакетов NuGet, определяющих библиотеку .NET Standard.  Наиболее распространенным способом нацеливания на `netstandard` является ссылка на этот метапакет. Он описывает и предоставляет доступ примерно к 40 библиотекам .NET и связанным интерфейсам API, которые определяют библиотеку .NET Standard. Вы можете ссылаться на другие пакеты, предназначенные для `netstandard`, чтобы получить доступ к дополнительным интерфейсам API.

### <a name="versioning"></a>Управление версиями

Это не отдельная спецификация, а постепенно расширяемый набор API с линейно возрастающими номерами версий. Первая версия стандарта устанавливает базовый набор API. Последующие версии добавляют API и наследуют API, определенные в предыдущих версиях. Не существует установленных процедур для удаления API из стандарта.

.NET Standard не связывается с какой-либо одной реализацией выполнения .NET и не зависит от схем управления версиями любой из сред выполнения.

API, добавляемые в любую из реализаций (например, .NET Framework, .NET Core и Mono), можно рассматривать как кандидаты для добавления в спецификацию, особенно в том случае, если они носят фундаментальный характер. Новые [версии .NET Standard](https://github.com/dotnet/standard/blob/master/docs/versions.md) создаются на основе выпусков реализаций .NET, что позволяет использовать новые API из библиотеки PCL .NET Standard. Подробнее механизм управления версиями описан в разделе [Управление версиями .NET Core](../core/versions/index.md).

Управление версиями .NET Standard имеет важное значение при использовании. Зная версию .NET Standard, вы можете использовать все библиотеки, предназначенные для этой или более ранней версии. Ниже описан рабочий процесс использования библиотек PCL .NET Standard, ориентированных на конкретную версию .NET Standard.

- Выберите версию .NET Standard для вашей библиотеки PCL.
- Используйте библиотеки, которые зависят от той же или более низкой версии .NET Standard.
- Если вам потребуется библиотека, которая зависит от более поздней версии .NET Standard, нужно перейти на эту версию либо отказаться от использования этой библиотеки.

## <a name="targeting-net-standard"></a>Нацеливание на .NET Standard

Вы можете [создавать библиотеки .NET Standard](../core/tutorials/libraries.md) с помощью сочетания платформы `netstandard` и метапакета NETStandard.Library. Вы можете ознакомиться с примерами [нацеливания на .NET Standard с помощью средств .NET Core](../core/packages.md).

## <a name="net-framework-compatibility-mode"></a>Режим совместимости .NET Framework

Начиная с .NET Standard 2.0, доступен режим совместимости .NET Framework. Этот режим совместимости позволяет проектам .NET Standard ссылаться на библиотеки .NET Framework, как если бы они были скомпилированы для .NET Standard. Создание ссылок на библиотеки .NET Framework не работает для всех проектов, например таких, где библиотека использует API Windows Presentation Foundation (WPF).

Дополнительные сведения см. в разделе [Режим совместимости .NET Framework](../core/porting/third-party-deps.md#net-framework-compatibility-mode).

## <a name="net-standard-libraries-and-visual-studio"></a>Библиотеки .NET Standard и Visual Studio

Чтобы создать библиотеки .NET Standard в Visual Studio, убедитесь, что у вас установлена [Visual Studio 2017 версии 15.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) или более поздней (для Windows) или [Visual Studio для Mac версии 7.1](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) или более поздней (для macOS).

Если вам нужно использовать только библиотеки .NET Standard 2.0 в своих проектах, это также можно сделать в Visual Studio 2015. Но у вас должен быть установлен клиент NuGet версии 3.6 или более поздней. Можно скачать клиент NuGet для Visual Studio 2015 со страницы [загрузок NuGet](https://www.nuget.org/downloads).

## <a name="comparison-to-portable-class-libraries"></a>Сравнение с переносимыми библиотеками классов

.NET Standard заменяет [переносимые библиотеки классов (PCL)](./cross-platform/cross-platform-development-with-the-portable-class-library.md). .NET Standard расширяет возможности создания переносимых библиотек, контролируя стандартную библиотеку BCL и обеспечивая высокую согласованность разных реализаций .NET. Библиотека, нацеленная на библиотеку .NET Standard, именуется библиотекой PCL или "основанной на стандартах библиотекой PCL .NET". Существующие библиотеки PCL представляют собой "PCL на основе профиля".

.NET Standard и профили PCL созданы для схожих целей, однако имеют существенные отличия.

Сходства:

- Определяет API-интерфейсы, которые можно использовать для совместного использования двоичного кода.

Различия:

- .NET Standard является проверенным набором API, а профили PCL определяются пересечениями существующих платформ.
- .NET Standard имеет линейно возрастающие версии, чего нет в профилях PCL.
- Профили PCL относятся к платформам Майкрософт, а .NET Standard не зависит от платформы.

### <a name="pcl-compatibility"></a>Совместимость библиотек PCL

.NET Standard совместима с подмножеством профилей PCL. Каждая из версий .NET Standard 1.0, 1.1 и 1.2 перекрывается с определенным набором профилей PCL. Такое перекрытие было создано по двум причинам:

- Предоставление библиотекам PCL на основе .NET Standard права ссылаться на основанные на профилях PCL.
- Возможность упаковки основанных на профилях PCL в виде PCL на основе .NET Standard.

Совместимость основанных на профилях PCL обеспечивается за счет пакета NuGet [Microsoft.NETCore.Portable.Compatibility](https://www.nuget.org/packages/Microsoft.NETCore.Portable.Compatibility). Такая зависимость требуется при ссылке на пакеты NuGet, содержащие основанные на профилях PCL.

Основанные на профилях PCL, которые упакованы в виде `netstandard`, удобнее использовать, чем обычно упакованные PCL на основе профилей. Упаковка `netstandard` совместима с существующими пользователями.

Можно просмотреть набор профилей PCL, совместимых с .NET Standard:

| Профиль PCL | .NET Standard | Платформы PCL
|:-----------:|:-------------:|------------------------------------------------------------------------------
| Profile7    | 1.1           | .NET Framework 4.5, Windows 8
| Profile31   | 1.0           | Windows 8.1, Windows Phone Silverlight 8.1
| Profile32   | 1.2           | Windows 8.1, Windows Phone 8.1
| Profile44   | 1.2           | .NET Framework 4.5.1, Windows 8.1
| Profile49   | 1.0           | .NET Framework 4.5, Windows Phone Silverlight 8
| Profile78   | 1,0           | .NET Framework 4.5, Windows 8, Windows Phone Silverlight 8
| Profile84   | 1.0           | Windows Phone 8.1, Windows Phone Silverlight 8.1
| Profile111  | 1.1           | .NET Framework 4.5, Windows 8, Windows Phone 8.1
| Profile151  | 1.2           | .NET Framework 4.5.1, Windows 8.1, Windows Phone 8.1
| Profile157  | 1.0           | Windows 8.1, Windows Phone 8.1, Windows Phone Silverlight 8.1
| Profile259  | 1.0           | .NET Framework 4.5, Windows 8, Windows Phone 8.1, Windows Phone Silverlight 8

## <a name="see-also"></a>См. также

- [Версии .NET Standard](https://github.com/dotnet/standard/blob/master/docs/versions.md)
- [Создание библиотеки .NET Standard](../core/tutorials/library-with-visual-studio.md)
- [Разработка для различных платформ](./library-guidance/cross-platform-targeting.md)
