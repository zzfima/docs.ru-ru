---
title: Анализ зависимостей для переноса кода в .NET Core
description: Научитесь анализировать внешние зависимости, чтобы перенести свой проект из .NET Framework в .NET Core.
author: cartermp
ms.date: 12/07/2018
ms.custom: seodec18
ms.openlocfilehash: 36d1c1d2090a0fb9e6f48fe519d15897579df2d5
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72521474"
---
# <a name="analyze-your-dependencies-to-port-code-to-net-core"></a>Анализ зависимостей для переноса кода в .NET Core

Для переноса кода в .NET Core или .NET Standard требуется понимать свои зависимости. Внешние зависимости — это несобираемые вами [пакеты NuGet](#analyze-referenced-nuget-packages-in-your-projects) или [библиотеки DLL](#analyze-dependencies-that-arent-nuget-packages), на которые вы ссылаетесь в своем проекте. Оцените каждую зависимость и составьте план на непредвиденные случаи в отношении тех зависимостей, которые не совместимы с .NET Core. В этой статье показано, как определить совместимость зависимости с .NET Core.

## <a name="analyze-referenced-nuget-packages-in-your-projects"></a>Анализ упоминаемых посредством ссылки пакетов NuGet в вашем проекте

Если в своем проекте вы ссылаетесь на пакеты NuGet, необходимо проверить, совместимы ли они с .NET Core.
Этого можно добиться двумя способами:

- [С помощью приложения обозревателя пакетов NuGet](#analyze-nuget-packages-using-nuget-package-explorer).
- [С помощью сайта nuget.org](#analyze-nuget-packages-using-nugetorg).

Если анализ пакетов покажет, что они не совместимы с .NET Core и предназначены только для использования с .NET Framework, можно проверить, поможет ли выполнить перенос [режим совместимости .NET Framework](#net-framework-compatibility-mode).

### <a name="analyze-nuget-packages-using-nuget-package-explorer"></a>Анализ пакетов NuGet с помощью обозревателя пакетов NuGet

Пакет NuGet представляет собой набор папок со сборками для конкретных платформ. Поэтому необходимо проверить, существует ли папка, которая содержит совместимую сборку внутри пакета.

Проще всего просматривать папки пакета NuGet с помощью инструмента [Обозреватель пакетов NuGet](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer). После установки выполните следующие действия, чтобы увидеть имена папок:

1. Откройте обозреватель пакетов NuGet.
2. Щелкните **Открыть пакет из веб-канала**.
3. Выполните поиск по имени пакета.
4. Выберите имя пакета в результатах поиска и нажмите кнопку **Открыть**.
5. Разверните папку *lib* в правой части окна и просмотрите имена папок.

Найдите папку с любым из следующих имен:

```
netstandard1.0
netstandard1.1
netstandard1.2
netstandard1.3
netstandard1.4
netstandard1.5
netstandard1.6
netstandard2.0
netcoreapp1.0
netcoreapp1.1
netcoreapp2.0
netcoreapp2.1
netcoreapp2.2
portable-net45-win8
portable-win8-wpa8
portable-net451-win81
portable-net45-win8-wpa8-wpa81
```

Эти значения — [моникеры целевых платформ (TFM)](../../standard/frameworks.md), которые соответствуют версиям [.NET Standard](../../standard/net-standard.md), .NET Core и традиционным профилям переносимой библиотеки классов (PCL), совместимым с .NET Core.

> [!IMPORTANT]
> При просмотре поддерживаемых пакетом моникеров TFM обратите внимание, что, несмотря на совместимость, `netcoreapp*` предназначен только для проектов .NET Core, но не для проектов .NET Standard.
> Библиотека, предназначенная только для `netcoreapp*`, но не для `netstandard*`, может использоваться только другими приложениями .NET Core.

### <a name="analyze-nuget-packages-using-nugetorg"></a>Анализ пакетов NuGet с помощью сайта nuget.org

Кроме того, поддерживаемые каждым пакетом TFM можно просмотреть на сайте [nuget.org](https://www.nuget.org/) в разделе **Зависимости** страницы пакета.

С помощью этого сайта легко проверить совместимость, однако информация о **зависимостях** доступна не для всех пакетов.

### <a name="net-framework-compatibility-mode"></a>Режим совместимости .NET Framework

Анализ пакетов NuGet может показать, что они предназначены только для платформы .NET Framework, как и большинство пакетов NuGet.

Начиная с .NET Standard 2.0, доступен режим совместимости .NET Framework. Этот режим совместимости позволяет проектам .NET Standard и .NET Core ссылаться на библиотеки .NET Framework. Создание ссылок на библиотеки .NET Framework не работает для всех проектов, например, если библиотека использует API WPF, то делает возможным разблокировку множества сценариев переноса.

Ссылаясь в своем проекте на пакеты NuGet, предназначенные для .NET Framework, например [Huitian.PowerCollections](https://www.nuget.org/packages/Huitian.PowerCollections), вы получаете предупреждение об откате пакета ([NU1701](/nuget/reference/errors-and-warnings/nu1701)), как в следующем примере:

`NU1701: Package ‘Huitian.PowerCollections 1.0.0’ was restored using ‘.NETFramework,Version=v4.6.1’ instead of the project target framework ‘.NETStandard,Version=v2.0’. This package may not be fully compatible with your project.`

Это предупреждение отображается при добавлении пакета и каждый раз при выполнении сборки, чтобы вы обязательно протестировали этот пакет в своем проекте. Если проект работает надлежащим образом, можно отключить это предупреждение, изменив свойства пакета в Visual Studio или путем редактирования файла проекта в привычном редакторе кода вручную.

Чтобы отключить это предупреждение путем редактирования файла проекта, найдите запись `PackageReference` для пакета, предупреждение для которого требуется отключить, и добавьте атрибут `NoWarn`. Атрибут `NoWarn` принимает разделенный запятыми список всех идентификаторов предупреждений. В следующем примере показано отключение предупреждения `NU1701` для пакета `Huitian.PowerCollections` путем редактирования файла проекта вручную:

```xml
<ItemGroup>
  <PackageReference Include="Huitian.PowerCollections" Version="1.0.0" NoWarn="NU1701" />
</ItemGroup>
```

Дополнительные сведения о том, как отключить предупреждения компилятора в Visual Studio, см. в разделе [Подавление предупреждений для пакетов NuGet](/visualstudio/ide/how-to-suppress-compiler-warnings#suppress-warnings-for-nuget-packages).

## <a name="port-your-packages-to-packagereference"></a>Перенос собственных пакетов в `PackageReference`

[PackageReference](/nuget/consume-packages/package-references-in-project-files) используется в .NET Core для указания зависимостей пакета. Если вы указываете пакеты с помощью файла [packages.config](/nuget/reference/packages-config), вам нужно будет преобразовать его в `PackageReference`.

Дополнительные сведения см. в статье [Перенос из packages.config в PackageReference](/nuget/reference/migrate-packages-config-to-package-reference).

## <a name="what-to-do-when-your-nuget-package-dependency-doesnt-run-on-net-core"></a>Что делать, если зависимость пакета NuGet не работает в .NET Core

Если пакет NuGet, от которого зависит ваш проект, не работает в .NET Core, можно предпринять ряд мер:

1. Если проект имеет открытый исходный код и размещается на каком либо ресурсе, наподобие GitHub, вы можете обратиться к разработчикам напрямую.
2. Вы можете обратитесь к автору непосредственно на [nuget.org](https://www.nuget.org/). Найдите пакет и нажмите кнопку **Связаться с владельцами** в левой стороне страницы пакета.
3. Можно найти другой пакет, который будет выполнять те же функции и работать в .NET Core.
4. Вы можете попытаться создать пакет с аналогичным кодом самостоятельно.
5. Вы можете устранить зависимость от пакета, изменив функциональность приложения, по крайней мере до тех пор пока не станет доступна совместимая версия пакета.

Помните, что обслуживанием проектов с открытым исходным кодом и выпуском пакетов NuGet часто занимаются волонтеры. Они делают эту работу, потому что им важна соответствующая область деятельности, причем безвозмездно, часто в свободное от основной занятости время. Помните об этом, обращаясь к ним за поддержкой при использовании пакетов .NET Core.

Если ни один из описанных выше способов не помог решить проблему, возможно, придется отложить перенос кода в .NET Core на более позднюю дату.

Команда разработчиков .NET хотела бы узнать, поддержку каких библиотек в .NET Core следует реализовать в первую очередь. Сообщить о нужных вам библиотеках можно в электронном сообщении по адресу dotnet@microsoft.com.

## <a name="analyze-dependencies-that-arent-nuget-packages"></a>Анализ зависимостей, которые не являются пакетами NuGet

Возможно, вы используете зависимость, которая не является пакетом NuGet, например библиотеку DLL в файловой системе. Единственный способ определить переносимость такой зависимости — запустить [средство .NET Portability Analyzer](https://github.com/Microsoft/dotnet-apiport). Это средство может анализировать сборки, предназначенные для .NET Framework, и идентифицировать API, которые невозможно перенести на другие платформы .NET, например .NET Core. Можно запустить средство в качестве консольного приложения или [расширения Visual Studio](../../standard/analyzers/portability-analyzer.md).

>[!div class="step-by-step"]
>[Вперед](libraries.md)
