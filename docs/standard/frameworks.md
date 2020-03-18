---
title: Целевые платформы в проектах в стиле SDK — .NET
description: Сведения о целевых версиях платформы для приложений и библиотек .NET Core.
ms.date: 12/03/2019
ms.custom: updateeachrelease
ms.technology: dotnet-standard
ms.openlocfilehash: 33beb5606cbf857cc41b739f256482b0298f1fb1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "79398799"
---
# <a name="target-frameworks-in-sdk-style-projects"></a>Целевые платформы в проектах в стиле SDK

При выборе целевой платформы для приложения или библиотеки вы указываете набор API-интерфейсов, которые вы хотите сделать доступными для приложения или библиотеки. Целевая платформа указывается в файле проекта с помощью моникеров целевой платформы (TFM).

Приложение или библиотека могут быть предназначены для версии [.NET Standard](net-standard.md). Версии .NET Standard представляют стандартные наборы API-интерфейсов во всех реализациях .NET. Например, библиотека может быть предназначена для .NET Standard 1.6 и получить доступ к API-интерфейсам, которые работают в .NET Core и .NET Framework с одной и той же базой кода.

Приложение или библиотека могут также работать в конкретной реализации .NET. В этом случае они получают доступ к API-интерфейсам конкретной реализации. Например, приложение, предназначенное для Xamarin.iOS (например, `Xamarin.iOS10`), получает доступ к предоставленным Xamarin iOS программам-оболочкам API для iOS 10 или приложение, ориентированное на универсальную платформу Windows (UWP, `uap10.0`) имеет доступ к API-интерфейсам, которые компилируется для устройств под управлением Windows 10.

Для некоторых целевых платформ (например, .NET Framework) API-интерфейсы определяются сборками, устанавливаемыми платформой в системе, в число которых могут входить API-интерфейсы платформы приложений (например, ASP.NET).

Для целевых платформ на основе пакетов (например, .NET Standard и .NET Core) API-интерфейсы определяются пакетами в составе приложения или библиотеки. *Метапакет* — это пакет NuGet, не имеющий собственного содержимого, но имеющий список зависимостей (другие пакеты). В этом случае целевая платформа на основе пакетов NuGet неявно задает метапакет, который ссылается на все пакеты, составляющие платформу.

## <a name="latest-target-framework-versions"></a>Последние версии целевой платформы

В приведенной ниже таблице определены наиболее распространенные целевые платформы, способы их указания и реализованные в них версии [.NET Standard](net-standard.md). Эти версии целевой платформ являются последними стабильными версиями. Предварительные версии здесь не упоминаются. Моникер целевой платформы (TFM) является стандартизированный форматом маркера для указания целевой платформы приложения или библиотеки .NET.

| Требуемая версия .NET Framework      | Последняя версия <br/> Стабильная версия | Моникер целевой платформы (TFM) | Реализовано <br/> Версия .NET Standard |
| :-------------------: | :-------------------------: | :----------------------------: | :-------------------------------------: |
| .NET Standard         | 2.1                         | netstandard2.1                 | Недоступно                                     |
| .NET Core             | 3.1                         | netcoreapp3.1                  | 2.1                                     |
| .NET Framework        | 4.8                         | net48                          | 2.0                                     |

## <a name="supported-target-framework-versions"></a>Поддерживаемые версии целевой платформы

Целевая платформа обычно называется по TFM. В следующей таблице показаны целевые платформы, поддерживаемые пакетом SDK для .NET Core и клиентом NuGet. Эквивалентные обозначения отображаются в скобках. Например, `win81` является эквивалентом TFM для `netcore451`.

| Требуемая версия .NET Framework           | TFM |
| -------------------------- | --- |
| .NET Standard              | netstandard1.0<br>netstandard1.1<br>netstandard1.2<br>netstandard1.3<br>netstandard1.4<br>netstandard1.5<br>netstandard1.6<br>netstandard2.0<br>netstandard2.1 |
| .NET Core                  | netcoreapp1.0<br>netcoreapp1.1<br>netcoreapp2.0<br>netcoreapp2.1<br>netcoreapp2.2<br>netcoreapp3.0<br>netcoreapp3.1 |
| .NET Framework             | net11<br>net20<br>net35<br>net40<br>net403<br>net45<br>net451<br>net452<br>net46<br>net461<br>net462<br>net47<br>net471<br>net472<br>net48 |
| Магазин Windows              | netcore [netcore45]<br>netcore45 [win] [win8]<br>netcore451 [win81] |
| .NET Micro Framework       | netmf |
| Silverlight                | sl4<br>sl5 |
| Windows Phone              | wp [wp7]<br>wp7<br>wp75<br>wp8<br>wp81<br>wpa81 |
| Универсальная платформа Windows | uap [uap10.0]<br>uap10.0 [win10] [netcore50] |

## <a name="how-to-specify-target-frameworks"></a>Как указать целевые платформы

Целевые платформы указываются в файле проекта. Если указана одна целевая платформа, используйте элемент **TargetFramework**. В следующем файле проекта консольного приложения показано, как указать целевую платформу .NET Core 3.0:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

При указании нескольких целевых платформ можно условно ссылаться на сборки для каждой целевой платформы. В коде можно условно компилировать эти сборки с использованием символов препроцессора с логикой *if-then-else*.

Следующий файл проекта библиотеки предназначен для API-интерфейсов .NET Standard (`netstandard1.4`) и API-интерфейсов .NET Framework (`net40` и `net45`). Используйте множественный элемент **TargetFrameworks** с несколькими целевыми платформами. Обратите внимание, каким образом атрибуты `Condition` включают пакеты, связанные с конкретной реализацией, при компиляции библиотеки для двух TFM .NET Framework.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFrameworks>netstandard1.4;net40;net45</TargetFrameworks>
  </PropertyGroup>

  <!-- Conditionally obtain references for the .NET Framework 4.0 target -->
  <ItemGroup Condition=" '$(TargetFramework)' == 'net40' ">
    <Reference Include="System.Net" />
  </ItemGroup>

  <!-- Conditionally obtain references for the .NET Framework 4.5 target -->
  <ItemGroup Condition=" '$(TargetFramework)' == 'net45' ">
    <Reference Include="System.Net.Http" />
    <Reference Include="System.Threading.Tasks" />
  </ItemGroup>

</Project>
```

В библиотеке или приложении следует написать условный код компиляции для каждой целевой платформы.

```csharp
public class MyClass
{
    static void Main()
    {
#if NET40
        Console.WriteLine("Target framework: .NET Framework 4.0");
#elif NET45  
        Console.WriteLine("Target framework: .NET Framework 4.5");
#else
        Console.WriteLine("Target framework: .NET Standard 1.4");
#endif
    }
}
```

Система сборки учитывает символы препроцессора, представляющие целевые платформы, которые приведены в таблице [Поддерживаемые версии целевой платформы](#supported-target-framework-versions), при использовании проектов в стиле SDK. При использовании символа, представляющего TFM .NET Standard или .NET Core, замените точку символом подчеркивания и измените строчные буквы на прописные (например, символ для `netstandard1.4` — `NETSTANDARD1_4`).

Полный список символов препроцессора для целевой платформы .NET Core.

[!INCLUDE [Preprocessor symbols](../../includes/preprocessor-symbols.md)]

## <a name="deprecated-target-frameworks"></a>Неподдерживаемые целевые платформы

Следующие целевые платформы являются устаревшими. Пакеты, предназначенные для этих целевых платформ, следует перевести на предлагаемые для замены.

| Нерекомендуемый TFM                                                                             | Замена |
| ------------------------------------------------------------------------------------------ | ----------- |
| aspnet50<br>aspnetcore50<br>dnxcore50<br>dnx<br>dnx45<br>dnx451<br>dnx452                  | netcoreapp  |
| dotnet<br>dotnet50<br>dotnet51<br>dotnet52<br>dotnet53<br>dotnet54<br>dotnet55<br>dotnet56 | netstandard |
| netcore50                                                                                  | uap10.0     |
| win                                                                                        | netcore45   |
| win8                                                                                       | netcore45   |
| win81                                                                                      | netcore451  |
| win10                                                                                      | uap10.0     |
| winrt                                                                                      | netcore45   |

## <a name="see-also"></a>См. также раздел

- [Пакеты, метапакеты и платформы](../core/packages.md)
- [Разработка библиотек с помощью кроссплатформенных средств](../core/tutorials/libraries.md)
- [.NET Standard](net-standard.md)
- [Управление версиями .NET Core](../core/versions/index.md)
- [Репозиторий GitHub dotnet/standard](https://github.com/dotnet/standard)
- [Инструменты NuGet в репозитории GitHub](https://github.com/joelverhagen/NuGetTools)
- [Профили платформы в .NET](https://blog.stephencleary.com/2012/05/framework-profiles-in-net.html)
