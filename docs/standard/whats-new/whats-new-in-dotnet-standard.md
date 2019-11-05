---
title: Новые возможности .NET Standard
description: В этой статье перечислены новые возможности и улучшения в каждой новой версии платформы .NET Standard.
ms.custom: updateeachrelease
ms.date: 04/12/2018
ms.technology: dotnet-standard
ms.openlocfilehash: ebf656c4a5499fff54cb5a70a93c4e8cc9c82d0a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73101759"
---
# <a name="whats-new-in-the-net-standard"></a>Новые возможности .NET Standard

.NET Standard — это формальная спецификация, определяющая ряд версий с набором интерфейсов API, которые должны быть доступны во всех реализациях .NET, соответствующих определенной версии стандарта. Решение .NET Standard ориентировано на разработчиков библиотек. Библиотека, которая предназначена для некоторой версии .NET Standard, может использоваться в любой реализации .NET Framework, .NET Core или Xamarin, совместимой с той же версией стандарта.

Сейчас последней версией является .NET Standard 2.0. Она входит в пакет SDK для .NET Core 2.0, а также в Visual Studio 2017 версии 15.3 при установленной рабочей нагрузке .NET Core.

## <a name="supported-net-implementations"></a>Поддерживаемые реализации .NET

.NET Standard 2.0 поддерживается следующими реализациями .NET:

- .NET Core 2.0 или более поздней версии
- .NET Framework 4.6.1 или более поздней версии
- Mono 5.4 или более поздней версии
- Xamarin.iOS 10.14 или более поздней версии
- Xamarin.Mac 3.8 или более поздней версии
- Xamarin.Android 8.0 или более поздней версии
- Универсальная платформа Windows 10.0.16299 или более поздней версии

## <a name="whats-new-in-the-net-standard-20"></a>Новые возможности .NET Standard 2.0

.NET Standard 2.0 содержит следующие новые функции и компоненты.

### <a name="a-vastly-expanded-set-of-apis"></a>Значительно расширенный набор интерфейсов API

Вплоть до версии 1.6 спецификация .NET Standard содержала сравнительно небольшой набор API-интерфейсов. Среди прочего, в их числе не было многих API, которые часто используются на платформах .NET Framework и Xamarin. Это усложняет разработку, так как разработчикам приходится искать подходящие средства для замены знакомых API при разработке приложений и библиотек для нескольких реализаций .NET. В .NET Standard 2.0 это ограничение устранено: в стандарт добавлены более 20 000 интерфейсов API, недоступных в предыдущей версии .NET Standard 1.6. Список интерфейсов API, добавленных в .NET Standard 2.0 см. в [документе сравнения возможностей .NET Standard 2.0 и 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).

Вот лишь некоторые возможности, добавленные в пространство имен <xref:System> .NET Standard 2.0:

- поддержка класса <xref:System.AppDomain>;
- улучшенная поддержка работы с массивами из дополнительных элементов класса <xref:System.Array>;
- улучшенная поддержка работы с атрибутами из дополнительных элементов класса <xref:System.Attribute>;
- улучшенная поддержка календаря и дополнительных параметров форматирования для значений <xref:System.DateTime>;
- дополнительные возможности округления <xref:System.Decimal>;
- дополнительные функциональные возможности для класса <xref:System.Environment>;
- расширенный контроль над сборщиком мусора через класс <xref:System.GC>;
- улучшенная поддержка сравнения строк, перечисления и нормализации в классе <xref:System.String>;
- поддержка перехода на летнее время в классах <xref:System.TimeZoneInfo.AdjustmentRule> и <xref:System.TimeZoneInfo.TransitionTime>;
- значительно улучшенная функциональность класса <xref:System.Type>;
- улучшенная поддержка десериализации объектов исключений благодаря новому конструктору исключений с параметрами <xref:System.Runtime.Serialization.SerializationInfo> и <xref:System.Runtime.Serialization.StreamingContext>.

### <a name="support-for-net-framework-libraries"></a>Поддержка библиотек .NET Framework

Практически все библиотеки предназначены для .NET Framework, а не .NET Standard. Но при этом большая часть вызовов в этих библиотеках направлена к интерфейсам API .NET Standard 2.0. Начиная с .NET Standard 2.0 библиотеки .NET Framework доступны из библиотек .NET Standard через [оболочку совместимости](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#assembly-unification). Этот уровень совместимости прозрачен для разработчиков, то есть от них не требуется никаких действий, чтобы пользоваться библиотеками .NET Framework.

Действует только одно требование: API, вызываемые библиотекой классов .NET Framework, должны быть включены в .NET Standard 2.0.

### <a name="support-for-visual-basic"></a>Поддержка Visual Basic

Теперь вы можете разрабатывать библиотеки .NET Standard на Visual Basic. Разработчики Visual Basic, использующие Visual Studio 2017 версии 15.3 или более поздней версии с установленной рабочей нагрузкой .NET Core, теперь получают в Visual Studio шаблон библиотеки классов .NET Standard. Разработчики Visual Basic, которые используют другие средства и среды разработки, могут создать проект библиотеки .NET Standard с помощью команды [dotnet new](../../core/tools/dotnet-new.md). Дополнительные сведения см. в разделе [Поддержка средств для библиотек .NET Standard](#tooling-support-for-net-standard-libraries).

### <a name="tooling-support-for-net-standard-libraries"></a>Поддержка средств для библиотек .NET Standard

С момента выхода .NET Core 2.0 и .NET Standard 2.0 поддержка средств для создания библиотек .NET Standard включена в Visual Studio 2017 и в [.NET Core CLI](../../core/tools/index.md).

Если у вас установлен Visual Studio с рабочей нагрузкой **для кроссплатформенной разработки .NET Core**, вы можете создать проект библиотеки .NET Standard 2.0 с помощью шаблона проекта, как показано на рисунке ниже.

<!-- markdownlint-disable MD025 -->

# <a name="ctabcsharp"></a>[C#](#tab/csharp)

![Добавление нового проекта библиотеки .NET Standard](./media/std-project-cs.png)

Если вы используете .NET Core CLI, указанная ниже команда [dotnet new](../../core/tools/dotnet-new.md) создает проект библиотеки классов, предназначенный для .NET Standard 2.0.

```dotnetcli
dotnet new classlib
```

# <a name="visual-basictabvb"></a>[Visual Basic](#tab/vb)

![Добавление нового проекта библиотеки .NET Standard](./media/std-project-vb.png)

Если вы используете .NET Core CLI, указанная ниже команда [dotnet new](../../core/tools/dotnet-new.md) создает проект библиотеки классов, предназначенный для .NET Standard 2.0.

```dotnetcli
dotnet new classlib -lang vb
```

---

## <a name="see-also"></a>См. также

- [.NET Standard](../net-standard.md)
- [Введение в .NET Standard](https://devblogs.microsoft.com/dotnet/introducing-net-standard/)
