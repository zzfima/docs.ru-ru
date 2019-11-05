---
title: Новые возможности .NET Core 2.0
description: Дополнительные сведения о новых возможностях .NET Core.
ms.date: 08/13/2017
ms.openlocfilehash: fcac4255e7370f31ea6c26771fdd7d341bafe38b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73100845"
---
# <a name="whats-new-in-net-core-20"></a>Новые возможности .NET Core 2.0

В .NET Core 2.0 представлены следующие улучшения и новые возможности:

- [инструментарий](#tooling);
- [языковая поддержка](#language-support);
- [улучшения платформы](#platform-improvements);
- [изменения API](#api-changes-and-library-support);
- [интеграция Visual Studio](#visual-studio-integration);
- [усовершенствования документации](#documentation-improvements).

## <a name="tooling"></a>Инструментарий

### <a name="dotnet-restore-runs-implicitly"></a>Явное выполнение команды dotnet restore

В предыдущих версиях .NET Core сразу после создания проекта с помощью команды [dotnet new](../tools/dotnet-new.md), а также после добавления новой зависимости в проект требовалось выполнять команду [dotnet restore](../tools/dotnet-restore.md).

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Вы также можете отключить автоматический вызов команды `dotnet restore`. Для этого передайте параметр `--no-restore` команде `new`, `run`, `build`, `publish`, `pack` и `test`.

### <a name="retargeting-to-net-core-20"></a>Изменение целевой платформы на .NET Core 2.0

Если установлен пакет SDK для .NET Core 2.0, для проектов, предназначенных для .NET Core 1.x, можно изменить целевую платформу на .NET Core 2.0.

Чтобы изменить целевую платформу на .NET Core 2.0, измените файл проекта. Для этого измените значение элемента `<TargetFramework>` или `<TargetFrameworks>` (при наличии нескольких целевых платформ в файле проекта) с 1.x на 2.0:

```xml
<PropertyGroup>
    <TargetFramework>netcoreapp2.0</TargetFramework>
 </PropertyGroup>
```

Кроме того, можно также выполнить перенацеливание с библиотек .NET Standard на .NET Standard 2.0:

```xml
<PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
 </PropertyGroup>
```

Дополнительные сведения о переносе проекта в .NET Core 2.0 см. в статье [Migrating from ASP.NET Core 1.x to ASP.NET Core 2.0](/aspnet/core/migration/1x-to-2x/index) (Переход с ASP.NET Core 1.x на ASP.NET Core 2.0).

## <a name="language-support"></a>Языковая поддержка

Помимо поддержки C# и F# .NET Core 2.0 также поддерживает Visual Basic.

### <a name="visual-basic"></a>Visual Basic

.NET Core версии 2.0 теперь поддерживает Visual Basic 2017. С помощью Visual Basic можно создать следующие типы проектов:

- консольные приложения .NET Core;
- библиотеки классов .NET Core;
- библиотеки классов .NET Standard;
- проекты модульных тестов .NET Core;
- тестовые проекты xUnit .NET Core.

Например, для создания приложения Visual Basic Hello World в командной строке сделайте следующее:

1. Откройте окно консоли, создайте каталог для проекта и выберите его в качестве текущего.

1. Введите команду `dotnet new console -lang vb`.

   Команда создает файл проекта с расширением `.vbproj`, а также файл исходного кода Visual Basic *Program.vb*. Этот файл содержит исходный код для записи строки Hello World! в окно консоли.

1. Введите команду `dotnet run`. [.NET Core CLI](../tools/index.md) автоматически компилирует и выполняет приложение, которое выводит сообщение "Hello World!" в окне консоли.

### <a name="support-for-c-71"></a>Поддержка C# 7.1

.NET Core 2.0 поддерживает C# 7.1, в котором реализованы новые возможности, включая следующие:

- Метод `Main`, точку входа приложения можно пометить с помощью ключевого слова [async](../../csharp/language-reference/keywords/async.md).
- Выводимые имена кортежей.
- Стандартные выражения.

<!-- For more information see [link to C# what's new](url). -->

## <a name="platform-improvements"></a>Улучшения платформы

В .NET Core 2.0 представлены возможности, упрощающие установку платформы .NET Core и ее использование в поддерживаемых операционных системах.

### <a name="net-core-for-linux-is-a-single-implementation"></a>Единая реализация .NET Core для Linux

.NET Core 2.0 предлагает единую реализацию Linux, которую можно использовать в нескольких дистрибутивах Linux. Для .NET Core 1.x требовалось, чтобы вы загрузили реализацию Linux для конкретного дистрибутива.

Кроме того, предусмотрена возможность разработки приложений, предназначенных исключительно для ОС Linux. В .NET Core 1.x требовалось выбирать целевую среду для каждого дистрибутива Linux отдельно.

### <a name="support-for-the-apple-cryptographic-libraries"></a>Поддержка библиотек шифрования Apple

В .NET Core 1.x на macOS требовалась библиотека шифрования для набора средств OpenSSL. .NET Core 2.0 использует библиотеки шифрования Apple и не требует OpenSSL, поэтому больше не нужно устанавливать это решение.

## <a name="api-changes-and-library-support"></a>Изменения в API и поддержка библиотек

### <a name="support-for-net-standard-20"></a>Поддержка .NET Standard 2.0

.NET Standard определяет набор интерфейсов API с несколькими версиями, которые должны быть доступны в реализациях .NET, соответствующие версии Standard. Решение .NET Standard ориентировано на разработчиков библиотек. Оно предоставляет функции библиотеки, предназначенной для версии .NET Standard в каждой реализации .NET. .NET Core 1.x поддерживает .NET Standard версии 1.6, .NET Core 2.0 поддерживает последнюю версию, .NET Standard 2.0. Дополнительные сведения см. в статье [.NET Standard](../../standard/net-standard.md).

.NET Standard 2.0 содержит более 20 000 интерфейсов API, доступных в .NET Standard 1.6. Такое разнообразие является результатом включения в .NET Standard интерфейсов API, стандартных для .NET Framework и Xamarin.

Библиотеки классов .NET Standard 2.0 также могут ссылаться на библиотеки классов .NET Framework, при условии, что они вызывают API-интерфейсы, которые есть в .NET Standard 2.0. Повторная компиляция библиотек .NET Framework не требуется.

Список интерфейсов API, добавленных в .NET Standard с момента выхода последней версии, .NET Standard 1.6, см. в сравнительном документе [.NET Standard 2.0 и 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).

### <a name="expanded-surface-area"></a>Увеличение количества компонентов

Общее количество API-интерфейсов, доступных в .NET Core 2.0, удвоилось по сравнению с .NET Core 1.1.

[Пакет обеспечения совместимости Windows](../porting/windows-compat-pack.md) существенно упрощает перенос из .NET Framework.

### <a name="support-for-net-framework-libraries"></a>Поддержка библиотек .NET Framework

Код .NET Core может ссылаться на имеющиеся библиотеки .NET Framework, включая имеющиеся пакеты NuGet. Обратите внимание, что библиотеки должны использовать интерфейсы API из .NET Standard.

## <a name="visual-studio-integration"></a>интеграция Visual Studio

В Visual Studio 2017 версии 15.3 (в некоторых случаях, в Visual Studio для Mac) внесены значительные улучшения для разработчиков .NET Core.

### <a name="retargeting-net-core-apps-and-net-standard-libraries"></a>Изменение целевой платформы приложений .NET Core и библиотек .NET Standard

Если установлен пакет SDK для .NET Core 2.0, можно изменить целевую платформу проектов .NET Core 1.x на .NET Core 2.0, а библиотек .NET Standard 1.x — на .NET Standard 2.0.

Чтобы изменить целевую платформу проекта в Visual Studio, в диалоговом окне свойств проекта откройте вкладку **Приложение** и измените значение **целевой платформы** на **.NET Core 2.0** или **.NET Standard 2.0**. Ее также можно изменить, щелкнув проект правой кнопкой мыши и выбрав пункты **Изменить \*CSPROJ-файл**. Дополнительные сведения см. в разделе [Инструментарий](#tooling) выше.

### <a name="live-unit-testing-support-for-net-core"></a>Поддержка динамического модульного тестирования для .NET Core

При изменении кода функция Live Unit Testing автоматически запускает все затронутые модульные тесты в фоновом режиме и отображает результаты и объем протестированного кода в активном состоянии в среде Visual Studio. Теперь .NET Core 2.0 поддерживает функцию Live Unit Testing. Ранее функция Live Unit Testing была доступна только для приложений .NET Framework.

Дополнительные сведения см. в статье [Функция Live Unit Testing в Visual Studio 2017](/visualstudio/test/live-unit-testing) и [Часто задаваемые вопросы о функции Live Unit Testing](/visualstudio/test/live-unit-testing-faq).

### <a name="better-support-for-multiple-target-frameworks"></a>Улучшенная поддержка нескольких целевых платформ

При создании проекта для различных целевых платформ теперь целевую платформу можно выбрать в меню верхнего уровня. На следующем рисунке показано, что целевой платформой проекта SCD1 является 64-разрядная macOS X 10.11 (`osx.10.11-x64`) и 64-разрядная Windows 10 и Windows Server 2016 (`win10-x64`). Целевую платформу можно выбрать, прежде чем нажать кнопку проекта (в этом случае — для выполнения отладочной сборки).

![Снимок экрана, показывающий выбор целевой платформы при сборке проекта.](./media/dotnet-core-2-0/target-framework-selection.png)

### <a name="side-by-side-support-for-net-core-sdks"></a>Поддержка параллельного выполнения для пакетов SDK для .NET Core

Теперь пакет SDK для .NET Core можно установить отдельно от Visual Studio. Таким образом в одной версии Visual Studio можно создавать проекты, предназначенные для разных версий .NET Core. Ранее Visual Studio и пакет SDK для .NET Core были тесно связаны. Конкретная версия пакета SDK использовалась для конкретной версии Visual Studio.

## <a name="documentation-improvements"></a>Усовершенствования документации

### <a name="net-application-architecture"></a>Архитектура приложений .NET

Благодаря [архитектуре приложений .NET](https://dotnet.microsoft.com/learn/dotnet/architecture-guides) вы получаете доступ к набору электронных книг, в которых представлены инструкции, рекомендации и примеры приложений при использовании .NET для сборки:

- [Микрослужбы и контейнеры Docker](../../architecture/microservices/index.md)
- [Разработка веб-приложений с помощью ASP.NET](../../architecture/modern-web-apps-azure/index.md)
- [Мобильные приложения в Xamarin](/xamarin/xamarin-forms/enterprise-application-patterns/index)
- [Приложения, развертываемые в облаке с помощью Azure](/azure/architecture/reference-architectures/index)

## <a name="see-also"></a>См. также

- [What's new in ASP.NET Core 2.0](/aspnet/core/aspnetcore-2.0) (Новые возможности ASP.NET Core 2.0)
